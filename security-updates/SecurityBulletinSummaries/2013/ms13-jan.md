---
TOCTitle: 'MS13-JAN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Gennaio 2013'
ms:assetid: 'ms13-jan'
ms:contentKeyID: 61240082
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-jan(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Gennaio 2013
=================================================================

Data di pubblicazione: martedì 8 gennaio 2013 | Aggiornamento: martedì 12 marzo 2013

**Versione:** 4.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a gennaio 2013.

Con il rilascio dei bollettini sulla sicurezza di gennaio 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 3 gennaio 2013 e la notifica anticipata del bollettino straordinario pubblicata in data 13 gennaio 2013. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 9 gennaio 2013 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di gennaio](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538623&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538623&culture=en-us).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti sul bollettino straordinario il 14 gennaio 2013 alle 13:00 ora del Pacifico (USA e Canada). [Registrarsi ora per il Webcast del bollettino straordinario del 14 gennaio 2013](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032541648&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032541648&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=275222">MS13-008</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento per la protezione per Internet Explorer (2799329)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Internet Explorer. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273848">MS13-001</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilitànei componenti dello spooler di stampa di Windows può consentire l'esecuzione di codice in modalità remota</strong> <strong>(2769369)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un server di stampa riceve un processo di stampa appositamente predisposto. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi direttamente a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=264923">MS13-002</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft XML Core Services possono consentire l'esecuzione di codice in modalità remota (2756145)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Microsoft XML Core Services segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web di questo tipo. L'utente malintenzionato deve invece convincere gli utenti a visitare il sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di messaggistica immediata che li indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft Office,<br />
Strumenti per gli sviluppatori Microsoft,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=261863">MS13-003</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in System Center Operations Manager possono consentire l'acquisizione di privilegi più elevati (2748552)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft System Center Operations Manager. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente visita un sito Web interessato attraverso un URL appositamente predisposto. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web di questo tipo. L'utente malintenzionato deve invece convincere le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268279">MS13-004</a></td>
<td style="border:1px solid black;"><strong>Alcune</strong> <strong>vulnerabilità</strong> <strong>in .NET</strong> <strong>Framework possono consentire l'acquisizione di privilegi più elevati</strong> <strong>(2769324)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve quattro vulnerabilità<strong></strong>in .NET Framework che sono state segnalate privatamente. La più grave di queste vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web che può eseguire applicazioni browser XAML (XBAP). Queste vulnerabilità possono essere anche utilizzate dalle applicazioni Windows .NET per ignorare le restrizioni della protezione dall'accesso di codice (CAS). Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273826">MS13-005</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità nel driver in modalità kernel di Windows può consentire l'acquisizione di privilegi più elevati</strong> <strong>(2778930)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato esegue un'applicazione appositamente predisposta.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273872">MS13-006</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft</strong> <strong>Windowspuò consentire l'elusione della funzione di protezione(2785220)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nell'implementazione di SSL e TLS in Microsoft Windows. La vulnerabilità può consentire l'elusione della funzione di protezione se un utente malintenzionato intercetta handshake di traffico Web crittografati.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Elusione della funzione di protezione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268284">MS13-007</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel protocollo Open Data può consentire un attacco di tipo Denial of Service</strong> <strong>(2769327)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità nel protocollo Open Data (OData) che è stata divulgata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato non autenticato invia richieste HTTP appositamente predisposte a un sito interessato. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273848">MS13-001</a></td>
<td style="border:1px solid black;">Vulnerabilità dei componenti dello spooler di stampa di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0011">CVE-2013-0011</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=264923">MS13-002</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al troncamento dei valori integer MSXML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0006">CVE-2013-0006</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=264923">MS13-002</a></td>
<td style="border:1px solid black;">Vulnerabilità XSLT MSXML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0007">CVE-2013-0007</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=261863">MS13-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al filtro XSS nella console Web System Center Operations Manager</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0009">CVE-2013-0009</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=261863">MS13-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al filtro XSS nella console Web System Center Operations Manager</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0010">CVE-2013-0010</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268279">MS13-004</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer WinForms</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0002">CVE-2013-0002</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268279">MS13-004</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer S.DS.P</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0003">CVE-2013-0003</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268279">MS13-004</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla creazione duplicata</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0004">CVE-2013-0004</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273826">MS13-005</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione non corretta di messaggi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0008">CVE-2013-0008</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=273872">MS13-006</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione della funzione di protezione per il protocollo SSL versione 3 e TLS di Microsoft</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0013">CVE-2013-0013</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268284">MS13-007</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service legata alla funzione di sostituzione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0005">CVE-2013-0005</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=275222">MS13-008</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-4792">CVE-2012-4792</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità attraverso Internet Explorer 8.</td>
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
<th colspan="8">
Windows XP
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
**Nessuno**
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
<td style="border:1px solid black;">
**Nessuno**
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
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=20d8d873-a709-4834-a956-f3d9d82dbb73)  
(KB2799329)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=dcdcf814-e39d-4515-bc5d-12e11f214d08)  
(KB2799329)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4e0d584a-c684-408c-bc47-6bd4ecaa9b8a)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=137cc5ee-abf0-4a10-b1c4-d464331cbcfd)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=155a2984-2cd9-40a4-abaa-c1ea21e76062)  
(KB2742607)  
(solo Media Center Edition 2005 Service Pack 3 e Tablet PC Edition 2005 Service Pack 3)  
(Importante)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e2cc005-08c5-4e47-b05a-5b36fe539610)  
(KB2742596)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=20d07bcd-95cc-44a2-8e3e-f88b22682e21)  
(KB2756918)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=f35f2ea5-d60e-405a-9ed3-248e0d733c2b)  
(KB2799329)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=36c9d6a9-d939-4e19-b9f5-576fee048764)  
(KB2799329)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=396f26bd-8c8b-459d-9467-6ec17a11c9d4)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=d147f865-6a56-4db2-8d78-14f2bee6da18)  
(KB2757638)  
(Critico)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=0b13a83c-1e51-4604-a09d-afb2e25646f9)  
(KB2758696)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e2cc005-08c5-4e47-b05a-5b36fe539610)  
(KB2742596)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=20d07bcd-95cc-44a2-8e3e-f88b22682e21)  
(KB2756918)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
**Nessuno**
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
<td style="border:1px solid black;">
**Nessuno**
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
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=1a7cfc5a-2872-4516-a371-f42d4d3969a6)  
(KB2799329)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4b7c2bcd-a732-46ba-9d09-cc192efd4755)  
(KB2799329)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7f134d1c-670d-4528-b755-22124aa4d8c9)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=6a12de5f-de80-48e4-8276-6c420f5a2948)  
(KB2758696)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f1a2eb6e-0290-4a53-b93c-017a48b19973)  
(KB2742604)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e2cc005-08c5-4e47-b05a-5b36fe539610)  
(KB2742596)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=20d07bcd-95cc-44a2-8e3e-f88b22682e21)  
(KB2756918)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=00304f3b-069f-49dc-a416-b0b5fb97aa4b)  
(KB2799329)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4911899c-863f-4499-9477-340ef8daad29)  
(KB2799329)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b0cf6516-aea6-4879-9a6e-171d4825ae20)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=29985fdc-8aba-44b2-9420-970ca475052e)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=0b13a83c-1e51-4604-a09d-afb2e25646f9)  
(KB2758696)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e2cc005-08c5-4e47-b05a-5b36fe539610)  
(KB2742596)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=20d07bcd-95cc-44a2-8e3e-f88b22682e21)  
(KB2756918)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=b2c635b7-56ad-426b-8bd6-4aee9deadb69)  
(KB2799329)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b33197ab-f489-4c11-a229-044b186d7dda)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=bca95077-a28f-406c-9fe4-51dbcf6adee8)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=4719776a-5ff0-491a-934e-99220d8ac3a3)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=fb834cf7-d1fe-4291-8a0d-c866fdbdf0e6)  
(KB2758696)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e2cc005-08c5-4e47-b05a-5b36fe539610)  
(KB2742596)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=95d603e8-9440-4aa6-9765-20c77a55966a)  
(KB2799329)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=64b498a6-54fc-4b88-bcc3-2cc15a16abb5)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=d477235d-60f4-420d-8161-82194b4e62e7)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=39406634-48ad-4ecf-a6be-f5a47885704b)  
(KB2742601)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8cb7a04-f913-47cc-96c1-27fb7154a791)  
(KB2756919)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b1aef73-cfb2-4998-bca6-35cccfbb2078)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3107fadf-5ba8-48f6-bb23-0c0003b4ba76)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a35ccbff-c476-4ee2-be9c-5b6a4b1664e9)  
(KB2799329)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b427bace-5297-4593-9dd2-66847ae506c6)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=873eba5d-5a8f-410e-bad8-e9d538acf1b3)  
(KB2757638)  
(Critico)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=873eba5d-5a8f-410e-bad8-e9d538acf1b3)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=39406634-48ad-4ecf-a6be-f5a47885704b)  
(KB2742601)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8cb7a04-f913-47cc-96c1-27fb7154a791)  
(KB2756919)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4287381f-6f23-4a36-a7dc-f79c44bac124)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=098958e5-83cd-4ed2-b758-e970cef33325)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
**Nessuno**
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=3ce450f1-f71f-4d5d-bf1c-db4742522d18)  
(KB2799329)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=2d1266fc-f6b0-4062-9799-7b3721c2cf52)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e6439fef-e5e7-479b-8fc4-daacf3a39f3a)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=39406634-48ad-4ecf-a6be-f5a47885704b)  
(KB2742601)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8cb7a04-f913-47cc-96c1-27fb7154a791)  
(KB2756919)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c635ad51-4e15-461c-8927-a86d79f90b45)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b3ed781e-b740-4153-aaf3-daafdeb91004)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0f87dd60-92c2-444c-a9ea-dfeb106c88fa)  
(KB2799329)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=2f71f8e6-309c-4bea-abde-d91040c46611)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=1511377b-0adc-455f-8caa-f3498832c735)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=1511377b-0adc-455f-8caa-f3498832c735)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=39406634-48ad-4ecf-a6be-f5a47885704b)  
(KB2742601)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8cb7a04-f913-47cc-96c1-27fb7154a791)  
(KB2756919)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eff3a82e-f3db-4733-95aa-a68621e27068)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4aa3e3a7-3ebc-4b47-ab62-c22243a4edcc)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e47425e9-f53e-4e20-a7ec-b4c552bd66eb)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=c11ec9cd-1a85-4514-a1b9-9da5cdd0926b)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=4719776a-5ff0-491a-934e-99220d8ac3a3)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=c11ec9cd-1a85-4514-a1b9-9da5cdd0926b)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5091f66f-9b89-496f-95ce-9ac556faa7b5)  
(KB2742597)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=39406634-48ad-4ecf-a6be-f5a47885704b)  
(KB2742601)  
(Importante)  
[Microsoft .NET Framework 3.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8cb7a04-f913-47cc-96c1-27fb7154a791)  
(KB2756919)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d949fde9-31e7-4553-a34c-b41625a8cdc8)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ab117984-c4cb-473b-8c20-2b0d0409d8d6)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b476d44d-8a79-4857-8c3e-9d547e9b9e2d)  
(KB2736416)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d20f50ed-89c3-48cb-a78d-a44470fa1285)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=abbc3f31-e940-4750-acb6-5af477bc8390)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=3a160fc4-1bf0-4db2-aa8d-6ba4f07d196b)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=782fdaa7-7607-4617-97cc-516925e06d8a)  
(KB2742598)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=b8d0c829-ccb8-41a6-86ec-a7afde21c127)  
(KB2756920)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=057726d1-cdb4-4488-8cd8-822dabfc62a6)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=6120322b-7e04-4eeb-a9a4-11fe563a9f27)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=4c77925d-4326-483b-9d20-ad533d91c0f4)  
(KB2736418)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d20f50ed-89c3-48cb-a78d-a44470fa1285)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=abbc3f31-e940-4750-acb6-5af477bc8390)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=3a160fc4-1bf0-4db2-aa8d-6ba4f07d196b)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b23d8db-12d3-4404-b089-0c808eec1bd0)  
(KB2742599)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a41722e4-4b94-4539-a80e-2714269f8ae3)  
(KB2756921)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=057726d1-cdb4-4488-8cd8-822dabfc62a6)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6120322b-7e04-4eeb-a9a4-11fe563a9f27)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=28f51d80-d87e-4a58-9ef2-d650dd84ad97)  
(KB2736422)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c113b67f-42ca-4fea-ba45-aba6f94de154)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=1868c2ca-a184-494e-8eb3-82db45b08e32)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=4b442601-2808-4192-aa7d-b6476668cd23)  
(KB2757638)  
(Critico)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=4b442601-2808-4192-aa7d-b6476668cd23)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=782fdaa7-7607-4617-97cc-516925e06d8a)  
(KB2742598)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=b8d0c829-ccb8-41a6-86ec-a7afde21c127)  
(KB2756920)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=64249562-1fc3-436d-a9e1-4c9378b632d7)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=c9e2a55e-170f-4fe1-a306-eda676fd0fdb)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=4c77925d-4326-483b-9d20-ad533d91c0f4)  
(KB2736418)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c113b67f-42ca-4fea-ba45-aba6f94de154)  
(KB2799329)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1868c2ca-a184-494e-8eb3-82db45b08e32)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=4b442601-2808-4192-aa7d-b6476668cd23)  
(KB2757638)  
(Critico)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=4b442601-2808-4192-aa7d-b6476668cd23)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b23d8db-12d3-4404-b089-0c808eec1bd0)  
(KB2742599)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a41722e4-4b94-4539-a80e-2714269f8ae3)  
(KB2756921)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=64249562-1fc3-436d-a9e1-4c9378b632d7)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c9e2a55e-170f-4fe1-a306-eda676fd0fdb)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=28f51d80-d87e-4a58-9ef2-d650dd84ad97)  
(KB2736422)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d2fffc43-a88f-4fe5-9b24-5677258011b8)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=8de63e96-2822-4e62-af54-bd8d4c6d5c19)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=782fdaa7-7607-4617-97cc-516925e06d8a)  
(KB2742598)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=b8d0c829-ccb8-41a6-86ec-a7afde21c127)  
(KB2756920)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=934a2e78-c88b-4d06-9b8f-1d0b612f3fd5)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7fd8a313-9ee3-4665-b8ba-b129994aae1e)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=4c77925d-4326-483b-9d20-ad533d91c0f4)  
(KB2736418)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d2fffc43-a88f-4fe5-9b24-5677258011b8)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8de63e96-2822-4e62-af54-bd8d4c6d5c19)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b23d8db-12d3-4404-b089-0c808eec1bd0)  
(KB2742599)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a41722e4-4b94-4539-a80e-2714269f8ae3)  
(KB2756921)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=934a2e78-c88b-4d06-9b8f-1d0b612f3fd5)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7fd8a313-9ee3-4665-b8ba-b129994aae1e)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=28f51d80-d87e-4a58-9ef2-d650dd84ad97)  
(KB2736422)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=fbcee22b-9801-4c9e-ba0c-eb4a54526d38)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=18070321-8635-4c2e-b9f9-0fc58c924136)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=e4dfbf88-0e7f-43ca-affe-5d8ddea8657e)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=4719776a-5ff0-491a-934e-99220d8ac3a3)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e4dfbf88-0e7f-43ca-affe-5d8ddea8657e)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=782fdaa7-7607-4617-97cc-516925e06d8a)  
(KB2742598)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=b8d0c829-ccb8-41a6-86ec-a7afde21c127)  
(KB2756920)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=12917b84-1f91-4c19-9197-a7d1e7adcdfc)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=86e5b2fc-f530-4259-af90-259b64fcdd73)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=4c77925d-4326-483b-9d20-ad533d91c0f4)  
(KB2736418)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=fbcee22b-9801-4c9e-ba0c-eb4a54526d38)  
(KB2799329)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=18070321-8635-4c2e-b9f9-0fc58c924136)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=e4dfbf88-0e7f-43ca-affe-5d8ddea8657e)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=4719776a-5ff0-491a-934e-99220d8ac3a3)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e4dfbf88-0e7f-43ca-affe-5d8ddea8657e)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b23d8db-12d3-4404-b089-0c808eec1bd0)  
(KB2742599)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a41722e4-4b94-4539-a80e-2714269f8ae3)  
(KB2756921)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup>
(KB2742595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=12917b84-1f91-4c19-9197-a7d1e7adcdfc)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=86e5b2fc-f530-4259-af90-259b64fcdd73)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=28f51d80-d87e-4a58-9ef2-d650dd84ad97)  
(KB2736422)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup>
(KB2736428)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e19d1373-a3f3-4f60-9142-c2484726aac8)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1251343-b585-4feb-8465-7e775ae47998)  
(KB2742616)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=43bbbc5a-e175-467a-9302-810a2a09eb7e)  
(KB2756923)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=f21e2bdd-b158-45d5-a6cf-a8f32f099a7a)  
(KB2742614)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=1f5441f1-a66d-42c0-bf0e-2f6867d4d43a)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=9f40864f-5347-44ef-bb08-afea45b5351b)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=b0bbe58b-cb41-4b52-9dd2-b8b4bc0076eb)  
(KB2736693)  
(Importante)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=c669190d-964c-42d3-b09d-40a397ae3a9c)  
(KB2757638)  
(Critico)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Critico)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=c669190d-964c-42d3-b09d-40a397ae3a9c)  
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1251343-b585-4feb-8465-7e775ae47998)  
(KB2742616)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=43bbbc5a-e175-467a-9302-810a2a09eb7e)  
(KB2756923)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=f21e2bdd-b158-45d5-a6cf-a8f32f099a7a)  
(KB2742614)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=9d71dc77-9c01-4a1f-b403-8a18ca10979d)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=1b40baad-784a-4eba-a4ef-703250248057)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=b0bbe58b-cb41-4b52-9dd2-b8b4bc0076eb)  
(KB2736693)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7e434e5-1ce8-4754-b9b4-07f3d84e0528)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7e434e5-1ce8-4754-b9b4-07f3d84e0528)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1251343-b585-4feb-8465-7e775ae47998)  
(KB2742616)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=43bbbc5a-e175-467a-9302-810a2a09eb7e)  
(KB2756923)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=f21e2bdd-b158-45d5-a6cf-a8f32f099a7a)  
(KB2742614)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=2ad7872c-a387-41a1-8606-732a6ff0701d)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=4f0b9fb1-f1c4-4773-a956-94c8983c008a)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=b0bbe58b-cb41-4b52-9dd2-b8b4bc0076eb)  
(KB2736693)  
(Importante)  
[Estensione IIS OData gestione](http://www.microsoft.com/downloads/details.aspx?familyid=77b6fb5f-10b8-4bc2-a5c3-97055c92acf1)  
(KB2753596)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Microsoft XML Core Services 4.0<sup>[1]</sup>
(KB2758694)  
(Critico)  
Microsoft XML Core Services 6.0<sup>[1]</sup>
(KB2757638)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5<sup>[3]</sup>
(KB2742614)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT<sup>[1]</sup>
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT<sup>[1]</sup>
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-008**](http://go.microsoft.com/fwlink/?linkid=275222)****
</td>
<td style="border:1px solid black;">
[**MS13-001**](http://go.microsoft.com/fwlink/?linkid=273848)
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-004**](http://go.microsoft.com/fwlink/?linkid=268279)
</td>
<td style="border:1px solid black;">
[**MS13-005**](http://go.microsoft.com/fwlink/?linkid=273826)
</td>
<td style="border:1px solid black;">
[**MS13-006**](http://go.microsoft.com/fwlink/?linkid=273872)
</td>
<td style="border:1px solid black;">
[**MS13-007**](http://go.microsoft.com/fwlink/?linkid=268284)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=1e2738b9-d3c2-4dfe-8a79-335d5feee55b)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e6439fef-e5e7-479b-8fc4-daacf3a39f3a)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c635ad51-4e15-461c-8927-a86d79f90b45) (installazione Server Core)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b3ed781e-b740-4153-aaf3-daafdeb91004) (installazione Server Core)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=1511377b-0adc-455f-8caa-f3498832c735) (installazione Server Core)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04) (installazione Server Core)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=1511377b-0adc-455f-8caa-f3498832c735) (installazione Server Core)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eff3a82e-f3db-4733-95aa-a68621e27068) (installazione Server Core)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4aa3e3a7-3ebc-4b47-ab62-c22243a4edcc) (installazione Server Core)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=8de63e96-2822-4e62-af54-bd8d4c6d5c19) (installazione Server Core)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3) (installazione Server Core)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04) (installazione Server Core)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3) (installazione Server Core)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=782fdaa7-7607-4617-97cc-516925e06d8a) (installazione Server Core)  
(KB2742598)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=b8d0c829-ccb8-41a6-86ec-a7afde21c127) (installazione Server Core)  
(KB2756920)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=934a2e78-c88b-4d06-9b8f-1d0b612f3fd5) (installazione Server Core)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7fd8a313-9ee3-4665-b8ba-b129994aae1e) (installazione Server Core)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=4c77925d-4326-483b-9d20-ad533d91c0f4) (installazione Server Core)  
(KB2736418)  
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
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8de63e96-2822-4e62-af54-bd8d4c6d5c19) (installazione Server Core)  
(KB2769369)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3) (installazione Server Core)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04) (installazione Server Core)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd979acf-ed95-4d86-a046-ca7dc53523a3) (installazione Server Core)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b23d8db-12d3-4404-b089-0c808eec1bd0) (installazione Server Core)  
(KB2742599)  
(Importante)  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a41722e4-4b94-4539-a80e-2714269f8ae3) (installazione Server Core)  
(KB2756921)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=c2d4991c-05f1-48c7-96ea-1389281985e5)<sup>[1]</sup> (installazione Server Core)  
(KB2742595)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=dafc6924-d798-46b4-9fa5-ea7c35f06fa0) (installazione Server Core)  
(KB2742613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=934a2e78-c88b-4d06-9b8f-1d0b612f3fd5) (installazione Server Core)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7fd8a313-9ee3-4665-b8ba-b129994aae1e) (installazione Server Core)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=28f51d80-d87e-4a58-9ef2-d650dd84ad97) (installazione Server Core)  
(KB2736422)  
(Importante)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=1d22f0d5-d87d-4e4a-bbc9-49826cec79a7)<sup>[1]</sup> (installazione Server Core)  
(KB2736428)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 3.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7e434e5-1ce8-4754-b9b4-07f3d84e0528) (installazione Server Core)  
(KB2757638)  
(Moderato)  
[Microsoft XML Core Services 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7dabf372-4b31-4c9e-a660-4e0f4a65db04) (installazione Server Core)  
(KB2758694)  
(Moderato)  
[Microsoft XML Core Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7e434e5-1ce8-4754-b9b4-07f3d84e0528) (installazione Server Core)  
(KB2757638)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1251343-b585-4feb-8465-7e775ae47998) (installazione Server Core)  
(KB2742616)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=43bbbc5a-e175-467a-9302-810a2a09eb7e) (installazione Server Core)  
(KB2756923)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=f21e2bdd-b158-45d5-a6cf-a8f32f099a7a) (installazione Server Core)  
(KB2742614)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=2ad7872c-a387-41a1-8606-732a6ff0701d) (installazione Server Core)  
(KB2778930)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=4f0b9fb1-f1c4-4773-a956-94c8983c008a) (installazione Server Core)  
(KB2785220)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=b0bbe58b-cb41-4b52-9dd2-b8b4bc0076eb) (installazione Server Core)  
(KB2736693)  
(Importante)  
[Estensione IIS OData gestione](http://www.microsoft.com/downloads/details.aspx?familyid=77b6fb5f-10b8-4bc2-a5c3-97055c92acf1) (installazione Server Core)  
(KB2753596)  
(Importante)
</td>
</tr>
</table>
 
**Noteper MS13-002**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

<sup>[1]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

**Note per MS13-004**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

<sup>[2]</sup>I livelli di gravità non sono applicabili a questo aggiornamento per il software specificato perché i vettori di attacco conosciuti per la vulnerabilità trattata in questo bollettino sono bloccati in una configurazione predefinita. Tuttavia, come misura di difesa in profondità, Microsoft consiglia ai clienti di questo software di applicare questo aggiornamento per la protezione.

<sup>[3]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

**Nota** **per MS13-005**

<sup>[1]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

**Nota** **per MS13-006**

<sup>[1]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

**Nota per MS13-007**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

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
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=d108d56c-f9fb-4823-b38e-3d2f838592de)  
(KB2760574)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
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
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
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
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS13-002**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

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
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
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
Microsoft Expression Web Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Expression Web 2
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ba27dc9-4e9c-4ab5-867e-888c01716e11)  
(KB2687499)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS13-002**

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
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-003**](http://go.microsoft.com/fwlink/?linkid=261863)
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
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=31e1e6cc-9617-416b-8c91-5c026502d5f6)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=fb21c3f8-b3fd-42f2-9c34-e5fbd8cad689)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=31e1e6cc-9617-416b-8c91-5c026502d5f6)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=fb21c3f8-b3fd-42f2-9c34-e5fbd8cad689)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Groove Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-003**](http://go.microsoft.com/fwlink/?linkid=261863)
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
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Groove Server 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=fb21c3f8-b3fd-42f2-9c34-e5fbd8cad689)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Groove Server 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft XML Core Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=fb21c3f8-b3fd-42f2-9c34-e5fbd8cad689)  
(KB2687497)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft System Center Operations Manager
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-002**](http://go.microsoft.com/fwlink/?linkid=264923)
</td>
<td style="border:1px solid black;">
[**MS13-003**](http://go.microsoft.com/fwlink/?linkid=261863)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft System Center Operations Manager 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft System Center Operations Manager 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f848d74d-fdae-4a19-a0f5-12d2d4389db9)<sup>[1]</sup>
(KB2809182)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft System Center Operations Manager 2007 R2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft System Center Operations Manager 2007 R2](http://www.microsoft.com/downloads/details.aspx?familyid=4e1ab3bd-af0c-41f8-8ebc-1cdc68a3ee37)<sup>[1]</sup><sup>[2]</sup>
(KB2783850)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-002**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Noteper MS13-003**

<sup>[1]</sup>Questo aggiornamento è disponibile soltanto nell'Area download Microsoft.

<sup>[2]</sup>Questo aggiornamento è cumulativo e sostituisce aggiornamenti cumulativi precedenti per il software specificato.

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

-   Nicolas Gregoire di [Agarri](http://www.agarri.fr/) per aver segnalato un problema descritto nel bollettino MS13-002
-   Andy Yang di BAE Systems Detica per aver segnalato un problema descritto nel bollettino MS13-003
-   Jon Erickson di [iSIGHT Partners Labs](http://www.isightpartners.com/) per aver segnalato un problema descritto nel bollettino MS13-004
-   Vitaliy Toropov, che collabora con [Tipping Point's](http://www.tippingpoint.com/)[Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato due problemi descritti nel bollettino MS13-004
-   James Forshaw di Context Information Security per aver segnalato un problema descritto nel bollettino MS13-004
-   [Kenichiro Katayama](https://twitter.com/pin_ptr) per aver segnalato un problema descritto nel bollettino MS13-006
-   [Exodus Intelligence](https://www.exodusintel.com) per aver collaborato in relazione a un problema riportato in MS13-008

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 gennaio 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (8 gennaio 2013): Per MS13-002, sono state aggiunte le voci di installazione di Server Core al Software interessato per Microsoft XML Core Services 4.0 se installato su Windows Server 2008 per sistemi a 32 bit Service Pack 2 e Microsoft XML Core Services 6.0 in Windows Server 2008 per sistemi a 32 bit Service Pack 2. La modifica è esclusivamente informativa. I clienti che hanno già aggiornato i propri sistemi non devono eseguire ulteriori operazioni.
-   V2.0 (14 gennaio 2013): È stato aggiunto il bollettino sulla sicurezza Microsoft MS13-008, l'aggiornamento per la protezione di Internet Explorer (2799329) e il collegamento al Webcast dei bollettini per questo bollettino straordinario.
-   V3.0 (22 gennaio 2013): Per MS13-004, il bollettino è stato rilasciato per offrire nuovamente l'aggiornamento KB2756920 per Windows 7 e Windows Server 2008 R2 per sistemi con configurazioni specifiche che notoriamente presentano potenziali problemi di compatibilità. Consultare il bollettino per ulteriori informazioni.
-   V4.0 (12 marzo 2013): Per MS13-003, il bollettino è stato rilasciato nuovamente per comunicare la disponibilità di un aggiornamento per Microsoft System Center Operations Manager 2007 Service Pack 1. Il nuovo rilascio interessa solo questo pacchetto di aggiornamento. Consultare il bollettino per ulteriori informazioni.

*Built at 2014-04-18T01:50:00Z-07:00*
