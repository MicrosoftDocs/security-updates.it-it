---
TOCTitle: 'MS12-AUG'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Agosto 2012'
ms:assetid: 'ms12-aug'
ms:contentKeyID: 61240067
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms12-aug(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Agosto 2012
================================================================

Data di pubblicazione: martedì 14 agosto 2012 | Aggiornamento: martedì 11 dicembre 2012

**Versione:** 3.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati ad agosto 2012.

Con il rilascio dei bollettini sulla sicurezza di agosto 2012, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 agosto 2012. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 15 agosto 2012 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di agosto](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522490&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2722913)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità di Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257906">MS12-053</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del Desktop remoto può consentire l'esecuzione di codice in modalità remota (2723135)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità nel Remote Desktop Protocol che è stata divulgata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente malintenzionato invia una serie di pacchetti RDP appositamente predisposti a un sistema interessato. Per impostazione predefinita, il protocollo RDP (Remote Desktop Protocol) è disabilitato in tutti i sistemi operativi Windows. I sistemi che non hanno il protocollo RDP attivato non sono a rischio.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257914">MS12-054</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità dei componenti di rete di Windows</strong> <strong>possono consentire l'esecuzione di codice in modalità remota (2733594)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia una risposta appositamente predisposta a una richiesta dello spooler di stampa di Windows. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi direttamente a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=254386">MS12-060</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei controlli comuni di Windows può consentire l'esecuzione di codice in modalità remota (2720573)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nei controlli comuni di Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visita un sito Web con contenuto appositamente predisposto per sfruttare la vulnerabilità. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare tale sito Web. L'utente malintenzionato deve invece convincere gli utenti a visitare il sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che li indirizzi al sito. Il file dannoso può anche essere inviato come allegato a un messaggio di posta elettronica, ma l'utente malintenzionato deve convincere l'utente ad aprire l'allegato al fine di sfruttare la vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Microsoft SQL Server,<br />
Software dei server Microsoft,<br />
Strumenti per gli sviluppatori Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=259630">MS12-058</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità</strong> <strong>in Microsoft Exchange Server WebReady Document Viewing possono consentire l'esecuzione di codice in modalità remota (2740358)<br />
</strong>Questo aggiornamento per la protezione risolve alcune vulnerabilità divulgate pubblicamente in Microsoft Exchange Server WebReady Document Viewing. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota nel contesto di protezione del servizio di transcodifica sul server Exchange se un utente visualizza in anteprima un file appositamente predisposto utilizzando Outlook Web App (OWA). Il servizio di transcodifica in Exchange utilizzato per WebReady Document Viewing è in esecuzione nell'account LocalService. L'account LocalService dispone di privilegi minimi sul computer locale e presenta credenziali anonime sulla rete.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Exchange Server</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257907">MS12- 055</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità nei driver in modalità kernel di Windows può consentire l'acquisizione di privilegi più elevati (2731847)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=256487">MS12-056</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei motori JScript e VBScript può consentire l'esecuzione di codice in modalità remota (2706045)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nei motori di script JScript e VBScript sulle versioni a 64 bit di Microsoft Windows. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota durante la visualizzazione di un sito Web appositamente predisposto. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web. L'utente malintenzionato deve invece convincere le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257684">MS12-057</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office può consentire l'esecuzione di codice in modalità remota (2731879)<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre il file appositamente predisposto o incorpora un file Computer Graphics Metafile (CGM) appositamente predisposto in un file di Office. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255002">MS12-059</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Visio può consentire l'esecuzione di codice in modalità remota (2733918)<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria del layout</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1526">CVE-2012-1526</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota di accesso asincrono agli oggetti NULL</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2521">CVE-2012-2521</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota in una tabella delle funzioni virtuali corrotta</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2522">CVE-2012-2522</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota dovuta al sovraccarico di valori integer di JavaScript</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2523">CVE-2012-2523</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=256487">MS12-056</a> risolve anche questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257906">MS12-053</a></td>
<td style="border:1px solid black;">Vulnerabilità nel protocollo RDP (Remote Desktop Protocol)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2526">CVE-2012-2526</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257914">MS12-054</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service del Protocollo di amministrazione remota (RAP)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1850">CVE-2012-1850</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257914">MS12-054</a></td>
<td style="border:1px solid black;">Vulnerabilità della stringa di formato del servizio spooler di stampa</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1851">CVE-2012-1851</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257914">MS12-054</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow degli heap del Protocollo di amministrazione remota</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1852">CVE-2012-1852</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257914">MS12-054</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow dello stack del Protocollo di amministrazione remota</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1853">CVE-2012-1853</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257907">MS12- 055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2527">CVE-2012-2527</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=256487">MS12-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota dovuta al sovraccarico di valori integer di JavaScript</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2523">CVE-2012-2523</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255327">MS12-052</a> risolve anche questa vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257684">MS12-057</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria del formato file CGM</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2524">CVE-2012-2524</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=259630">MS12-058</a></td>
<td style="border:1px solid black;">Oracle Outside In contiene più vulnerabilità sfruttabili</td>
<td style="border:1px solid black;">Multiple*</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">*Vulnerabilità multiple, vedere il bollettino <a href="http://go.microsoft.com/fwlink/?linkid=259630">MS12-058</a> per ulteriori dettagli.<br />
<br />
Queste vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255002">MS12-059</a></td>
<td style="border:1px solid black;">Vulnerabilità di overflow del buffer del formato file DXF di Visio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1888">CVE-2012-1888</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=254386">MS12-060</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota di MSCOMCTL.OCX</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1856">CVE-2012-1856</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di un limitato numero di attacchi che tentano di utilizzare questa vulnerabilità.</td>
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
<th colspan="6">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=e1df425a-a67e-42f8-9eb5-a503f684c201)  
(KB2722913)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5afc85e3-a214-4774-93ab-17f9d199ebde)  
(KB2722913)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=213b3590-381e-437c-9391-ff6d7400f250)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ccc3d8fb-2631-42d0-87ed-5d29d4b1f598)  
(KB2723135)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=5403c78c-6b87-4788-89c3-0140b887ec6f)  
(KB2705219)  
(Critico)  
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c28e01d6-0030-417d-80dd-b34febd22ec1)  
(KB2712808)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=db21a230-0f6b-4d74-9f32-3718a59efd28)  
(KB2731847)  
(Importante)
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
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=2fdbe657-1810-4c5d-9ba8-5da148272756)  
(KB2722913)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ce5e8621-5457-4a27-9816-9ce719fd6937)  
(KB2722913)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=01784bbc-20fc-4d0f-bfcd-a5a25dd603e8)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a8eb0583-071d-4d8e-92fb-937035411b49)  
(KB2705219)  
(Critico)  
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b9e41497-5c49-45fc-8ad0-c853516609df)  
(KB2712808)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a036c343-5c6e-4484-b7f7-c7161c6880fd)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=e1b9a081-0329-4db6-b026-04a332cb0b4d)  
(KB2706045)  
(Importante)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=e5e3e9be-ba36-4fdf-93f6-a30fb087d273)  
(KB2722913)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0bced0f3-9778-4ee3-86fb-7f28b57adbce)  
(KB2722913)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=19393940-2519-4e97-89cd-de993ced31d5)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2847952f-0234-4cf6-820a-1f0a285b2fb7)  
(KB2705219)  
(Importante)  
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c20f475d-5211-4fdc-8a2f-4408f1baaece)  
(KB2712808)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=50090b08-3f82-4680-b871-2b18fc2386d0)  
(KB2731847)  
(Importante)
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
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=eb92185b-405a-4d96-b119-13f234a9c4ac)  
(KB2722913)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=26cda257-6607-4bd8-9152-cbcc2a753915)  
(KB2722913)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=fe7a78fc-f882-4748-a9e3-04b85d136ca2)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3833d768-1dab-4a85-822f-87c7fa3db261)  
(KB2705219)  
(Importante)  
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ad883d42-d8bb-482b-bf36-e2007cf73f84)  
(KB2712808)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7f72ba9a-80b2-459d-acad-da6a8b900d6f)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=81f5d8a5-12e5-4227-ae6f-5aea6ffff2a5)  
(KB2706045)  
(Basso)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=6c5edf14-ecb6-40af-a315-b049457415d6)  
(KB2722913)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c890335b-6ceb-427a-9cc7-95ef8c26d306)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=2fba3a11-3621-464d-ab22-d902195205f4)  
(KB2705219) (Importante)  
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=2857701f-3447-452c-a986-9f2fe42fe64d)  
(KB2712808)  
(Critico)

</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=9e647f22-2e80-4f4a-b648-615243741df2)  
(KB2731847)  
(Importante)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=862bd543-2fc5-4c4c-8d18-4623ccc68166)  
(KB2722913)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=709a85b7-d192-4bba-990a-ea98fdf6e882)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=430a43fa-78b8-4273-81e1-3081767ddcf9)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cbae6606-3721-48b9-ba3e-9d85df7e08b9)  
(KB2705219)  
(Moderato)  
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b4b216dc-533e-4fb4-acc8-ce5eb231320e)  
(KB2712808)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=41362740-876e-4c9e-9729-67dea6830438)  
(KB2731847)  
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=da933584-40ba-42a0-82fc-b84b41c6c5a4)  
(KB2722913)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ec48d017-d9ed-4b0e-b51f-0f04996088b6)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=5341a615-b737-4e48-8dfd-828725d9d513)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e4b4e53b-69d6-4ab6-98bb-3f8871048abe)  
(KB2705219)  
(Moderato)  
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dc966826-83e6-4bdc-bc58-8b6eb8917934)  
(KB2712808)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=007b4d50-b770-4e8f-b8d0-060f7bb58ad5)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=294a7eb4-c47f-449f-8931-262bec7d6ecc)  
(KB2706045)  
(Importante)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=91062e12-401e-472e-a6b6-0eb7216f5264)  
(KB2722913)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=77612ea1-13fb-4c53-bbd2-8796f0d5a9ed)  
(KB2722913)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=f016949d-b931-49f3-867b-f1c64839379e)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=354e502b-3016-4c5e-8611-bc1b35e1a7eb)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=35fb03b1-162a-4552-8bb9-6b564acbd57b)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ec759712-2f38-41a9-8b6d-c6908cc58479)  
(KB2731847)  
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a610d606-ca70-4dbd-9971-b6915dc4dc59)  
(KB2722913)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=defe6c53-66d7-4ea5-93b1-7487ccf19f24)  
(KB2722913)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=e5ab43bb-dbdb-4b2b-bbf2-260297ee5518)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2b8a730c-46ac-49b7-b9ae-73062d5a79f2)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e89024ca-a9e8-4ebf-91eb-cbf8e05398e7)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=caf68d77-3315-4383-a901-ba0385ffe561)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=47b2e47f-30f1-48e8-a857-70df319011ef)  
(KB2706045)  
(Basso)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6564a6a1-c8ba-4275-81b5-6664c8e3d010)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cce9a924-a74c-49e0-869f-6b9c1cd12cba)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=57153478-4837-438a-8487-929a48fd758a)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dee601c7-4ab4-4556-8d83-90864b09d365)  
(KB2731847)  
(Importante)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
Nessuno
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
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=625c45f5-5ad1-4ade-8883-33019587ab49)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=b2760784-6163-4a8d-86fb-72c88ed2b8ef)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=f83f6d97-24f1-4ee0-971d-ab79071fede6)  
(KB2705219)  
(Moderato)  
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=2bcfb574-a7d0-4d7e-b557-41bdcddfde42)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=c709aabf-4b3f-4780-8b82-c6c33a211e31)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=625c45f5-5ad1-4ade-8883-33019587ab49)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=b2760784-6163-4a8d-86fb-72c88ed2b8ef)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f83f6d97-24f1-4ee0-971d-ab79071fede6)  
(KB2705219)  
(Moderato)  
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2bcfb574-a7d0-4d7e-b557-41bdcddfde42)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c709aabf-4b3f-4780-8b82-c6c33a211e31)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f5bc6713-2540-4571-ae1f-04f427b33019)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=cac3b463-fb9c-474e-9e3d-bb96f7b4c14f)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=f49e3f9e-8a96-43e6-8b0a-5c9b78cd819d)  
(KB2705219)  
(Moderato)  
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=655182f9-110b-4b81-b140-0a5986d7343f)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=f62cf24a-8926-4dde-95ac-cc5f62e448be)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=ece661be-4ddf-42cc-a62b-15ce53b9d74b)  
(KB2706045)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f5bc6713-2540-4571-ae1f-04f427b33019)  
(KB2722913)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=cac3b463-fb9c-474e-9e3d-bb96f7b4c14f)  
(KB2722913)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f49e3f9e-8a96-43e6-8b0a-5c9b78cd819d)  
(KB2705219)  
(Moderato)  
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=655182f9-110b-4b81-b140-0a5986d7343f)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f62cf24a-8926-4dde-95ac-cc5f62e448be)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=ece661be-4ddf-42cc-a62b-15ce53b9d74b)  
(KB2706045)  
(Importante)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f6ea664b-575c-4cf0-b479-d1a2653288ee)  
(KB2722913)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=30a43d95-f489-49c2-a48a-a262fa196bbf)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e15d2bae-1511-4d74-93cb-0d614820e175)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=20c9a72f-a8b6-4b4c-a9ea-de93069cff3a)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=fc5b9df9-c836-407a-a1d4-364c1a885242)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=bbb876e6-a6b9-4193-be5e-d84390d30f1e)  
(KB2706045)  
(Basso)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f6ea664b-575c-4cf0-b479-d1a2653288ee)  
(KB2722913)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=30a43d95-f489-49c2-a48a-a262fa196bbf)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e15d2bae-1511-4d74-93cb-0d614820e175)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=20c9a72f-a8b6-4b4c-a9ea-de93069cff3a)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fc5b9df9-c836-407a-a1d4-364c1a885242)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=bbb876e6-a6b9-4193-be5e-d84390d30f1e)  
(KB2706045)  
(Basso)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=05a09f6e-b608-4430-b6d4-bb9d10d8347a)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=be89e6a5-34ef-4c23-8e16-722b9ae92073)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=27b52fb5-ff3c-4dca-9752-1517b873c9cb)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=7f17c057-939e-415d-b56a-01082695ab77)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=97004a96-0c83-421d-91a9-d55be32610c9)  
(KB2706045)  
(Basso)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=05a09f6e-b608-4430-b6d4-bb9d10d8347a)  
(KB2722913)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=be89e6a5-34ef-4c23-8e16-722b9ae92073)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=27b52fb5-ff3c-4dca-9752-1517b873c9cb)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7f17c057-939e-415d-b56a-01082695ab77)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=97004a96-0c83-421d-91a9-d55be32610c9)  
(KB2706045)  
(Basso)
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
[**MS12-052**](http://go.microsoft.com/fwlink/?linkid=255327)
</td>
<td style="border:1px solid black;">
[**MS12-053**](http://go.microsoft.com/fwlink/?linkid=257906)
</td>
<td style="border:1px solid black;">
[**MS12-054**](http://go.microsoft.com/fwlink/?linkid=257914)
</td>
<td style="border:1px solid black;">
[**MS12- 055**](http://go.microsoft.com/fwlink/?linkid=257907)
</td>
<td style="border:1px solid black;">
[**MS12-056**](http://go.microsoft.com/fwlink/?linkid=256487)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=354e502b-3016-4c5e-8611-bc1b35e1a7eb)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=35fb03b1-162a-4552-8bb9-6b564acbd57b)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ec759712-2f38-41a9-8b6d-c6908cc58479)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2b8a730c-46ac-49b7-b9ae-73062d5a79f2)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e89024ca-a9e8-4ebf-91eb-cbf8e05398e7)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=caf68d77-3315-4383-a901-ba0385ffe561)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e15d2bae-1511-4d74-93cb-0d614820e175)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=20c9a72f-a8b6-4b4c-a9ea-de93069cff3a)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=fc5b9df9-c836-407a-a1d4-364c1a885242)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e15d2bae-1511-4d74-93cb-0d614820e175)  
(KB2705219)  
(Moderato)  
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=20c9a72f-a8b6-4b4c-a9ea-de93069cff3a)  
(KB2712808)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fc5b9df9-c836-407a-a1d4-364c1a885242)  
(KB2731847)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Applicazioni e software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;">
[**MS12-057**](http://go.microsoft.com/fwlink/?linkid=257684)
</td>
<td style="border:1px solid black;">
[**MS12-059**](http://go.microsoft.com/fwlink/?linkid=255002)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)  
(controlli comuni di Windows)  
(KB2726929)  
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
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)  
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cc2a0eae-5b7e-465b-ab4c-a93ae7c7c458)  
(KB2596615)  
(Importante)  
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c2b0cb0f-db07-452f-a9a4-886124d3943e)  
(KB2596754)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)  
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cc2a0eae-5b7e-465b-ab4c-a93ae7c7c458)  
(KB2596615)  
(Importante)  
[Microsoft Office 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c2b0cb0f-db07-452f-a9a4-886124d3943e)  
(KB2596754)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=4e08bab7-1408-444d-bad7-a4db76c7f6d3)  
(controlli comuni di Windows)  
(KB2597986)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=953b9b69-2f66-4f71-b342-467cc05030ba)  
(KB2687501)  
(Importante)  
[Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a55a33f9-1eb6-469a-967c-a483764772c3)  
(KB2687510)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=de95d8b9-51a5-43cd-8ba3-8cbb1320d099)  
(KB2687508)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=90b99372-4f13-4f3a-ae52-da6543745248)  
(KB2687501)  
(Importante)  
[Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=da8a4d12-d4fc-4b6e-b65f-096dedddf529)  
(KB2687510)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=af690cd8-cb2c-4743-96f0-ffaec77adf10)  
(KB2687508)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Office Web Components
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;">
[**MS12-057**](http://go.microsoft.com/fwlink/?linkid=257684)
</td>
<td style="border:1px solid black;">
[**MS12-059**](http://go.microsoft.com/fwlink/?linkid=255002)
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
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Web Components Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Web Components Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)  
(controlli comuni di Windows)  
(KB2726929)  
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
<th colspan="4">
Altro software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;">
[**MS12-057**](http://go.microsoft.com/fwlink/?linkid=257684)
</td>
<td style="border:1px solid black;">
[**MS12-059**](http://go.microsoft.com/fwlink/?linkid=255002)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=62e87f7b-f48e-43a7-86d7-cbb8f0603ea3)  
(KB2598287)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64-bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64-bit)](http://www.microsoft.com/downloads/details.aspx?familyid=3889e1b3-69b2-4a8f-a0d9-de8c7dc6f5ec)  
(KB2598287)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS12-060**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="5">
Microsoft SQL Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS12-058**](http://go.microsoft.com/fwlink/?linkid=259630)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[Microsoft SQL Server 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=22be7d30-86f8-4a3b-ba46-b08624581c61)  
(KB983812)  
(Critico)  
Aggiornamento QFE:  
[Microsoft SQL Server 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=09ebb11b-2b82-4891-8ae9-03481c0d7b29)  
(KB983811)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2000 Analysis Services Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2000 Analysis Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=3f5f7d2c-1fd1-437d-a74c-f316c2cd7818)  
(KB983813)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi a 32 bit Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi a 32 bit Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)<sup>[1]</sup>
(controlli comuni di Windows)  
(KB2726929)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi x64 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi x64 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)<sup>[1]</sup>
(controlli comuni di Windows)  
(KB2726929)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi Itanium Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi Itanium Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)<sup>[1]</sup>
(controlli comuni di Windows)  
(KB2726929)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=fd9626f7-4265-48ae-94b2-68243605db6b)<sup>[1]</sup>
(controlli comuni di Windows)  
(KB2726929)  
(Critico)

</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi x64 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)

</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi Itanium Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)

</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)

</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c185e9-5328-4bf7-b175-fd9d7fc64097)<sup>[2]</sup>
(controlli comuni di Windows)  
(KB2687441)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="5">
Microsoft Commerce Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS12-058**](http://go.microsoft.com/fwlink/?linkid=259630)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Commerce Server 2002 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Commerce Server 2002 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=9ad19d40-16ed-47ad-b907-8a48bb64c6d3)  
(KB2716389)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Commerce Server 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Commerce Server 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d972437-f71a-4576-b5c1-a940c0824438)  
(KB2716390)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Commerce Server 2009
</td>
<td style="border:1px solid black;">
[Microsoft Commerce Server 2009](http://www.microsoft.com/downloads/details.aspx?familyid=3879fecd-8360-4c01-b88e-d56e8570cafb)  
(KB2716392)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Commerce Server 2009 R2
</td>
<td style="border:1px solid black;">
[Microsoft Commerce Server 2009 R2](http://www.microsoft.com/downloads/details.aspx?familyid=ce4f9470-e2b2-417e-9015-30355e837fbb)  
(KB2716393)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="5">
Microsoft Host Integration Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Host Integration Server 2004 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2004 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3dde4ef1-d41f-45b0-8660-a546cbe3fc81)  
(KB2711207)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="5">
Microsoft Exchange Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS12-058**](http://go.microsoft.com/fwlink/?linkid=259630)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2007 Service Pack 3
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Microsoft Exchange Server 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=21a26e23-9d83-41b6-95be-4b48f6e76023)  
(KB2756497)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Microsoft Exchange Server 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8646aaca-9829-4d3f-a77b-d24673818da7)  
(KB2756496)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Microsoft Exchange Server 2010 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b24182a-cee9-4ca0-9cc5-c4453475999d)  
(KB2756485)  
(Critico)
</td>
</tr>
</table>
 
**Note** **per** **MS12-060**

<sup>[1]</sup>Questo aggiornamento è identico all'aggiornamento KB2726929 per Microsoft Office 2003

<sup>[2]</sup>Questo aggiornamento è identico all'aggiornamento KB2687441 per Microsoft Office 2007

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Visual FoxPro
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
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
Microsoft Visual FoxPro 8.0 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 8.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0bef712a-b9e0-4ea9-98bf-68db366c8b8b)  
(KB2708940)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual FoxPro 9.0 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 9.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1ee09491-4871-41ca-a39c-8360d5a568d4)  
(KB2708941)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Visual Basic
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-060**](http://go.microsoft.com/fwlink/?linkid=254386)
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
Visual Basic 6.0 Runtime
</td>
<td style="border:1px solid black;">
[Visual Basic 6.0 Runtime](http://www.microsoft.com/downloads/details.aspx?familyid=847ec64b-95be-463b-bdfb-969e91fe3207)  
(KB2708437)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS12-060**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/default.aspx).

**SystemCenter Configuration Manager**

Gestione aggiornamenti software di System Center Configuration Manager semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con System Center Configuration Manager, gli amministratori IT possono distribuire gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in System Center Configuration Manager rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. Gestione aggiornamenti software di System Center Configuration Manager si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare System Center Configuration Manager per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su System Center Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager; vedere anche la sezione precedente, **System Center Configuration Manager**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/it-it/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc749197), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/it-it/windowsserver/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

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

-   GWSlabs, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS12-052
-   Derek Soeder, che collabora con il programma [Beyond Security's SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html), per aver segnalato un problema descritto nel bollettino MS12-052
-   Sung-ting Tsai e Ming-Chieh Pan di [Trend Micro](http://www.trendmicro.com) per aver segnalato un problema descritto nel bollettino MS12-052
-   Cris Neckar di [Google's Chrome Security Team](http://chrome.google.com/) per aver segnalato un problema descritto nel bollettino MS12-052
-   Edward Torkington di NCC Group per aver segnalato un problema descritto nel bollettino MS12-053
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato quattro problemi descritti nel bollettino MS12-054
-   [Mateusz “j00 ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS12-055
-   Cris Neckar di [Google's Chrome Security Team](http://chrome.google.com/) per aver segnalato un problema descritto nel bollettino MS12-056
-   [Andrei Costin](http://www.andreicostin.com) per aver segnalato un problema descritto nel bollettino MS12-057
-   Will Dorman di [CERT/CC](http://www.cert.org/) per aver collaborato con noi a 13 problemi descritti nel bollettino MS12-058
-   Alexander Gavrun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-059

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 agosto 2012): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (9 ottobre 2012): Riepilogo dei bollettini rivisto per coincidere con il nuovo rilascio di pacchetti di aggiornamento in MS12-053, MS12-054, MS12-055 e MS12-058. I clienti devono applicare i pacchetti di aggiornamento rilasciati nuovamente per evitare un problema relativo ai certificati digitali descritto nell'Advisory Microsoft sulla sicurezza 2749655. Vedere i bollettini per ulteriori informazioni.
-   V3.0 (11 dicembre 2012): Per MS12-057, gli aggiornamenti KB2553260 e KB2589322 sono stati sostituiti rispettivamente con gli aggiornamenti KB2687501 e KB2687510 per tutte le edizioni interessate di Microsoft Office 2010. Per MS12-059, l'aggiornamento KB2597171 è stato sostituito con l'aggiornamento KB2687508 per tutte le edizioni interessate di Microsoft Visio 2010. Per MS12-060, l'aggiornamento KB2687323 è stato sostituito con l'aggiornamento KB2726929 per i controlli comuni di Windows su tutte le varianti interessate di Microsoft Office 2003, Microsoft Office 2003 Web Components e Microsoft SQL Server 2005.

*Built at 2014-04-18T01:50:00Z-07:00*
