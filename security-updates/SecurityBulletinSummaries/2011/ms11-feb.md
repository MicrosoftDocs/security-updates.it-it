---
TOCTitle: 'MS11-FEB'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - febbraio 2011'
ms:assetid: 'ms11-feb'
ms:contentKeyID: 61240057
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-feb(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - febbraio 2011
==================================================================

Data di pubblicazione: martedì 8 febbraio 2011 | Aggiornamento: venerdì 18 marzo 2011

**Versione:** 4.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a febbraio 2011.

Con il rilascio dei bollettini sulla sicurezza di febbraio 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 3 febbraio 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 9 febbraio 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di febbraio](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032455047&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208304">MS11-003</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2482017)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente e due vulnerabilità divulgate pubblicamente relative a Internet Explorer. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer o se apre un file HTML legittimo che carica un file della libreria appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208146">MS11-006</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità della gestione grafica della shell di Windows può consentire l'esecuzione di codice in modalità remota (2483185)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente del processore grafico della shell di Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un'anteprima appositamente predisposta. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208059">MS11-007</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente nel driver OpenType/CFF (Compact Font Format) può consentire l'esecuzione di codice in modalità remota (2485376)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel driver OpenType/CFF (Compact Font Format) di Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un contenuto reso con un carattere CFF appositamente predisposto. In nessuno di questi casi un utente malintenzionato può obbligare gli utenti a visualizzare il contenuto appositamente predisposto. L'utente malintenzionato deve invece convincere gli utenti a visitare un sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che li indirizzi al sito Web.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208522">MS11-004</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del servizio FTP di Internet Information Services può consentire l'esecuzione di codice in modalità remota (2489256)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata pubblicamente nel servizio FTP di Internet Information Services (IIS). La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un server FTP riceve un comando FTP appositamente predisposto. Il servizio FTP non è installato per impostazione predefinita in IIS.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207843">MS11-005</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Active Directory può consentire un attacco di tipo Denial of Service (2478953)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Active Directory. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia un pacchetto appositamente predisposto ad un server Active Directory interessato. Per riuscire a sfruttare la vulnerabilità, l'utente malintenzionato deve essere in possesso di privilegi di amministratore locale validi sul computer collegato al dominio.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204799">MS11-008</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Visio possono consentire l'esecuzione di codice in modalità remota (2451879)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Visio. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207839">MS11-009</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei motori di script JScript e VBScript può consentire l'intercettazione di informazioni personali (2475792)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità dei motori di script JScript e VBScript che è stata segnalata privatamente. Questa vulnerabilità può consentire l'intercettazione di informazioni personali durante la visualizzazione di un sito Web appositamente predisposto. Poiché non è in alcun modo possibile obbligare gli utenti a visitare questi siti Web, L'utente malintenzionato dovrebbe invece convincere le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207840">MS11-010</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel sottosistema runtime client/server di Windows può consentire l'acquisizione di privilegi più elevati (2476687)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità nel sottosistema runtime client/server di Windows (CSRSS) in Windows XP e Windows Server 2003.<br />
<br />
La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema di un utente e avvia un'applicazione appositamente predisposta che continua ad essere eseguita dopo che l'utente malintenzionato si disconnette per ottenere le credenziali di accesso degli utenti successivi. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208365">MS11-011</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2393802)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso localmente ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2479628)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso localmente ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208523">MS11-013</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Kerberos possono consentire l'acquisizione di privilegi più elevati (2496930)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente e una vulnerabilità divulgata pubblicamente relative a Microsoft Windows. La più grave delle vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato locale ed autenticato installa un servizio dannoso su un computer collegato al dominio.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208395">MS11-014</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Local Security Authority Subsystem Service può consentire l'acquisizione locale di privilegi più elevati (2478960)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Local Security Authority Subsystem Service (LSASS) in Windows XP e Windows Server 2003, che è stata segnalata privatamente.<br />
<br />
La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede ad un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo della vulnerabilità</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability Index</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208146">MS11-006</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico nell'elaborazione grafica della shell di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3970">CVE-2010-3970</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità è stata divulgata pubblicamente e può essere sfruttata</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208304">MS11-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria CSS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3971">CVE-2010-3971</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità è stata divulgata pubblicamente ed è attualmente sfruttata nell'ecosistema di Internet</strong></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208365">MS11-011</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'interazione errata del driver con il kernel di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-4398">CVE-2010-4398</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207840">MS11-010</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione locale di privilegi più elevati in CSRSS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0030">CVE-2011-0030</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208304">MS11-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria non inizializzata</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0035">CVE-2011- 0035</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208304">MS11-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria non inizializzata</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0036">CVE-2011-0036</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208395">MS11-014</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida lunghezza LSASS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0039">CVE-2011-0039</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208523">MS11-013</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al checksum senza chiave in Kerberos</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0043">CVE-2011-0043</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</strong></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208365">MS11-011</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al troncamento dei valori integer del kernel di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0045">CVE-2011- 0045</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida errata dell'input utente in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0086">CVE-2011-0086</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida insufficiente dell'input utente in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0087">CVE-2011-0087</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla confusione dei puntatori delle classi di finestre Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0088">CVE-2011-0088</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida errata dei puntatori delle classi di finestre Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0089">CVE-2011-0089</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208362">MS11-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0090">CVE-2011-0090</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204799">MS11-008</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria degli oggetti Visio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0092">CVE-2011-0092</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204799">MS11-008</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria per determinati tipi di dati Visio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0093">CVE-2011-0093</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - In caso di sfruttamento sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208522">MS11-004</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer basato su heap del servizio FTP per IIS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3972">CVE-2010-3972</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - In caso di sfruttamento non sistematico della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità è stata divulgata pubblicamente e potrebbe essere disponibile codice PoC (&quot;proof-of-concept&quot;)</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208059">MS11-007</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ai valori codificati per i caratteri OpenType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0033">CVE-2011-0033</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - In caso di sfruttamento non sistematico della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207839">MS11-009</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali nei motori di script</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0031">CVE-2011-0031</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207843">MS11-005</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida SPN in Active Directory</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0040">CVE-2011-0040</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</strong><br />
<br />
Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208523">MS11-013</a></td>
<td style="border:1px solid black;">Vulnerabilità legata allo spoofing di Kerberos</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0091">CVE-2011-0091</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata soltanto allo spoofing</td>
</tr>
</tbody>
</table>
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle?**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="12">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=ae343de6-ec61-4891-b136-cfc4234d97d9)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=85bf88b7-2dd9-4204-8492-b2c1d8d2264e)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c72fbb97-2313-45f6-842d-99db373822dd)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=bbea7ead-6c5c-4da8-aa03-a40325fd2de3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f86e9e64-801a-431a-b24e-772011dfa66d)  
(Importante)
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
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cfa10178-9859-4e03-bedc-e3f5297a0251)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a511d33a-9ae0-46ee-a225-9d97390de7d1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=56f4f43e-c313-49dc-a278-e3e8a83a907e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=486d1969-6814-4556-8dc0-5bfbaee528b0)  
(KB2478971)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=541f228f-79b3-402a-8ff9-366c1e595227)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=d431100d-a627-4ea0-b75b-2d4157e38df2)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a795de21-13f4-4035-a4d5-4257ddc92fe7)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=69dfa24b-7c56-4521-850c-1485b062154a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bcb7217e-624a-4d61-86a1-f2440a1afd57)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=074396f0-a68c-4190-8dac-0b883d56e3f1)  
(Importante)
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
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9f0b7b77-5b90-4a4b-97a4-0c1ce6a70126)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7273a85-ce96-464b-8c4f-2710701213e3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e80db313-b470-4d71-bc34-70bfbfb6579f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a210c796-7077-4617-a9a8-9ea99fe11a5e)  
(KB2478971)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=82189bf2-3f34-4949-92da-eea98036d18e)  
(Importante)
</td>
</tr>
<tr>
<th colspan="12">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=5e0f4bf2-f727-483a-af3a-9a2abf0c36bb)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=45e504d4-c17d-4b73-b08e-d9c0cb3f4918)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=74238e08-fae2-4f17-ac72-681226a53a40)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2aa94528-5063-427b-97f7-2a0a55cbb6bf)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a99c2b13-db81-4f18-9cf7-c20614ba0132)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=651c1f4f-4e69-4d17-8aa2-72681dfc5463)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aed08b96-24cc-4e23-8fd5-c7e52f8ef41a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6bf2eeec-8225-477f-a606-263d3ee434d6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=54fe2669-8a63-4d96-8b82-5b10f45b293e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8a1e2675-0bf0-4d94-b48a-6e846dd6d9f5)  
(KB2478971)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4e31e6b1-577e-468e-9c94-67227d2273c2)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=0592b520-88d1-45bc-8b15-d3f0c8fa2181)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=29adcfb5-540f-4980-b2ca-9a22aa7bba13)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ebef4869-9812-46ce-9c01-2fb8c866ec90)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6e740922-6ce4-46ec-a35e-e94201a9e398)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aeed45fb-9395-4c2b-a674-e38b04fe0914)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=ec962b0e-e951-4e70-8d97-8c2afd360c28)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ca7879e1-e295-445d-a658-0a31be1928cc)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ec544894-ee98-4a2b-ac4d-33b0c3754213)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4632e1ce-6ae8-431c-9104-9a8840e5ac63)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e79bbbd4-8d5a-4c4c-8427-21c14400f041)  
(KB2478971)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=76e3c229-d812-433c-ad05-7cbd1f9c6a6d)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=b2298b32-238a-4970-bc1f-2ede51a6c361)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c41a0094-204b-4d05-ab39-a32915201af1)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a4f9ec46-35b2-44c9-abf6-647f7a474b99)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=bc09e42b-2eed-41b3-a03f-cb8cc94adfee)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=4ac66eae-e6d8-4e8b-b4ea-e7a77cc74db0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=50855101-a15c-4c81-ad81-a7fe3f1d2026)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=fcd48499-1bb4-4304-b9cc-27d9d92e11cd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a09c3e6e-c55c-492a-b7ad-3e3d35711643)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=856fbcc2-ead9-4ec1-92dd-988e6d22dae9)  
(KB2478971)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a0cde8d8-7c85-4fcb-bcf7-205064970b41)  
(Importante)
</td>
</tr>
<tr>
<th colspan="12">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b176777e-4897-4cf1-9fc0-dd608930bb4c)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=77971c3c-55ec-4a9c-bcb8-8fb8c61431e3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0c18ecca-afb9-4738-bc7b-76a0e815dfb8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d60a2098-7351-4fce-83b2-2c1c3a24faa0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=c09ccc72-8f94-416b-9a7f-ed16e90342a2)<sup>[1]</sup>
(Importante)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=da9b7982-1c6b-45ac-8dd0-d7101bb83949)<sup>[1]</sup>
(Importante)
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
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=66978514-bb7f-42cc-9360-2fd1c686f4e6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6fb7ebcc-2052-457b-b5bc-1bbcb17696b9)  
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
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=20ad0136-c6df-4c7b-811f-d6b3dd9e2c56)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d3580784-aada-4118-b7f2-3a23aec2ed04)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=62dc454f-4b1e-4ac0-8ffe-6c73112f8d4d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=065ad8fe-1caf-488e-a2e1-96db29f2fa57)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=e88d072f-0f5f-4c85-ad2f-91b9b8bf6b3a)<sup>[1]</sup>
(Importante)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=6e4b9878-b5d2-4025-8839-b41515932cf2)<sup>[1]</sup>
(Importante)
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
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8fdb8c37-1b22-457b-bdc0-21f6a5061dd3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=88d68757-1ab0-4585-9578-52a474b10882)  
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
<th colspan="12">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ee61f0dd-9797-4e11-8281-a05b201d0c0b)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ef1ae382-8835-4f60-83bd-e84a3400d55c)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=253c47a0-69ac-437a-ad3e-778c37fa37cb)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=88ba83b9-c14e-499a-8335-04bac1c49c0c)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=3cc55af7-5cd9-4923-8ec5-462ff201d734)<sup>[1]</sup>\*  
(Importante)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=4dfa0a25-b7e3-4fb6-a351-58ec3f8a8435)<sup>[1]</sup>\*  
(Importante)
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
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b37418a-e044-415e-b566-4507f157934a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80494972-db45-475f-97cd-dac46b9486a1)\*  
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
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=558bc86a-a49d-4d6c-b5e4-f12956f6b61b)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5607df02-93fa-45fe-a928-e5f6329851f3)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ec7101aa-96c2-4931-a3e4-0c55cbc74d9c)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c74d7f4-6372-4809-89b8-c79b05e54cdd)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=f485b30d-dcaf-47c3-ac62-982b14670a1f)<sup>[1]</sup>\*  
(Importante)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=a98a74c1-0c91-446d-b822-fe57ff06d90b)<sup>[1]</sup>\*  
(Importante)
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
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=163d3aca-3703-452e-b1cb-73932e2bcf8c)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5597d449-17e3-440f-8b0e-56a902a96569)\*  
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
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=8c2abba5-0597-4565-9b87-a37e574690e0)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e62493cb-8d25-4975-bbe6-a368e039872b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=91d5d34b-9d7e-4e83-89a4-f1aa388dc4e4)  
(Critico)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=55b07bc0-dff5-4cd7-87c9-c08e5a49197d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d10eda21-b3c3-4d8e-8596-bc45e4165f93)  
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
<th colspan="12">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=07aa7ffc-47c7-4611-b32c-ecb3fbcad32f)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1da57fbc-9ea4-4fc4-911d-d5c7825e012c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=9dabd1d1-3f1e-46d1-b171-aafd3f08d291)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[JScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=54a64215-e407-4b7b-8536-28817ef23bac)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=54a64215-e407-4b7b-8536-28817ef23bac)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=e1224c90-b0bc-4e4b-999a-efae327213b4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=078fe6c0-1b2c-4896-a345-25cc1b1105e2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ffed7c76-0b75-4f57-9b63-3961a8b449f6)  
(KB2425227)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=2b8ffafe-78bb-4fa7-aea2-01208b6a3dfe)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=587adb89-2f6a-4893-9906-b6d6d9ada2bd)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=66fb4efe-bcd3-4e90-8e35-b013e014a952)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[JScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=b854d76e-6891-426d-8c09-0ed8243a3b8d)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=b854d76e-6891-426d-8c09-0ed8243a3b8d)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=ddcf352e-742c-485e-9ed5-19cdba673562)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b42642b3-fb78-4700-bfe8-bfa997b90c16)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c26cebcf-683f-4a51-be75-76535fb979a7)  
(KB2425227)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="12">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-003**](http://go.microsoft.com/fwlink/?linkid=208304)
</td>
<td style="border:1px solid black;">
[**MS11-006**](http://go.microsoft.com/fwlink/?linkid=208146)
</td>
<td style="border:1px solid black;">
[**MS11-007**](http://go.microsoft.com/fwlink/?linkid=208059)
</td>
<td style="border:1px solid black;">
[**MS11-004**](http://go.microsoft.com/fwlink/?linkid=208522)
</td>
<td style="border:1px solid black;">
[**MS11-005**](http://go.microsoft.com/fwlink/?linkid=207843)
</td>
<td style="border:1px solid black;">
[**MS11-009**](http://go.microsoft.com/fwlink/?linkid=207839)
</td>
<td style="border:1px solid black;">
[**MS11-010**](http://go.microsoft.com/fwlink/?linkid=207840)
</td>
<td style="border:1px solid black;">
[**MS11-011**](http://go.microsoft.com/fwlink/?linkid=208365)
</td>
<td style="border:1px solid black;">
[**MS11-012**](http://go.microsoft.com/fwlink/?linkid=208362)
</td>
<td style="border:1px solid black;">
[**MS11-013**](http://go.microsoft.com/fwlink/?linkid=208523)
</td>
<td style="border:1px solid black;">
[**MS11-014**](http://go.microsoft.com/fwlink/?linkid=208395)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=38b67efb-dd4b-4e8c-8460-0f40f0367441)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=638318ed-4000-4b1a-bb4b-65b795f59784)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=1e075f57-1723-4933-9b8e-7bce4a44a1c1)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[JScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=f482bd40-f0b9-4534-a768-45879f1e7285)\*\*  
(Moderato)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=f482bd40-f0b9-4534-a768-45879f1e7285)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=70f5056a-72ad-46ff-a43f-ee151639b9a7)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d2c53f44-12eb-4293-9fa5-2a14075b636e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=46bb3ef1-24c3-41cb-8141-0fdbd85093f7)\*  
(KB2425227)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=0e41cbe5-5e5e-4ece-a71a-71f4b6319f0d)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4688ea0d-a467-4f24-ac52-104d05c8cae8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=bfddd539-c64f-4467-88ee-6bdfe645b478)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[JScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=f05a3de0-381c-4d17-83ee-ca4f6da1bdb0)  
(Moderato)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=f05a3de0-381c-4d17-83ee-ca4f6da1bdb0)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1646b3a5-714f-4ea5-b109-566fa9b933b6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8c6bf720-f544-4f58-9b1c-2399957ec43d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=01737933-e7de-451b-b02f-b7ca24693965)  
(KB2425227)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/en-us/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/en-us/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS11-004**

<sup>[1]</sup>Servizio FTP non predefinito per questo sistema operativo

#### Suite e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Programmi Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-008**](http://go.microsoft.com/fwlink/?linkid=204799)
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
Microsoft Visio 2002 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2002 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=273d8078-0dc7-43d8-bcae-54c811e49e0e)  
(KB2434711)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f1067eaa-d18d-4bff-a02e-1d990c36ca7f)  
(KB2434733)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=097a642b-b786-4724-a907-79f37cded836)  
(KB2434737)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**System Center Configuration Manager 2007**

La Gestione aggiornamenti software di Configuration Manager 2007 semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con Configuration Manager 2007, gli amministratori IT possono consegnare gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in Configuration Manager 2007 rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. La Gestione aggiornamenti software di Configuration Manager 2007 si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare Configuration Manager 2007 per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche la sezione precedente, **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/en-us/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

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

-   Yuki Chen di [Trend Micro](http://www.trendmicro.com) per aver segnalato un problema descritto nel bollettino MS11-003
-   SkyLined di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS11-003
-   Haifei Li di [FortiGuard Labs di Fortinet](http://www.fortiguard.com/) per aver segnalato un problema descritto in MS11-003
-   Kobi Pariente e Yaniv Miron, che collaborano con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS11-006
-   Procyun, che collabora con [Zero Day Initiative](http://www.tippingpoint.com/) di [TippingPoint](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS11-008
-   Xin Ouyang di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato due problemi descritti nel bollettino MS11-008
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS11-009
-   Sihan Qing (professore), Weiping Wen (professore associato), Liang Yin e Husheng Zhou (laureati), [Dipartimento di protezione delle informazioni dell'università di Pechino](http://www.ss.pku.edu.cn/en/), per aver segnalato un problema descritto in MS11-010
-   Zhengwenbin di [360safe](http://www.360.cn) per aver segnalato un problema descritto nel bollettino MS11-011
-   Guo Bojun per aver segnalato un problema descritto nel bollettino MS11-011
-   Wei Zhang per aver segnalato un problema descritto nel bollettino MS11-011
-   Marco Giuliani di [Prevx](http://www.prevx.com/) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS11-011
-   std\_logic, che collabora con [Zero Day Initiative](http://www.tippingpoint.com/) di [TippingPoint](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS11-011
-   Tarjei Mandt di [Norman](http://www.norman.com) per aver segnalato cinque problemi descritti nel bollettino MS11-012
-   [MIT Kerberos Team](http://web.mit.edu/kerberos) per aver segnalato un problema descritto nel bollettino MS11-013
-   Scott Stender di [iSEC Partners](http://www.isecpartners.com/) per aver segnalato un problema descritto nel bollettino MS11-013
-   Il security tester Jorge Moura di Primavera BSS per aver segnalato un problema descritto nel bollettino MS11-014

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 febbraio 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (9 febbraio 2011): Per MS11-013, la valutazione dell'Exploitability Index per CVE-2011-0091 è stata porta a "3 – Scarsa probabilità di sfruttamento della vulnerabilità". La modifica è esclusivamente informativa.
-   V2.0 (8 marzo 2011): È stato chiarito il software interessato per includere Windows 7 per sistemi a 32 bit Service Pack 1, Windows 7 per sistemi x64 Service Pack 1, Windows Server 2008 R2 per sistemi x64 Service Pack 1 e Windows Server 2008 R2 per sistemi Itanium Service Pack 1 per MS11-003, MS11-004, MS11-007 e MS11-009. Vedere la domanda frequente sull'aggiornamento di questi bollettini per ulteriori informazioni.
-   V3.0 (16 marzo 2011): È stato chiarito il software interessato per includere Windows 7 per sistemi a 32 bit Service Pack 1, Windows 7 per sistemi x64 Service Pack 1, Windows Server 2008 R2 per sistemi x64 Service Pack 1 e Windows Server 2008 R2 per sistemi Itanium Service Pack 1 per MS11-013. Vedere la domanda frequente per ulteriori informazioni.
-   V4.0 (18 marzo 2011): È stato chiarito il software interessato per includere Windows 7 per sistemi a 32 bit Service Pack 1, Windows 7 per sistemi x64 Service Pack 1, Windows Server 2008 R2 per sistemi x64 Service Pack 1 e Windows Server 2008 R2 per sistemi Itanium Service Pack 1 per MS11-012. Vedere la domanda frequente per ulteriori informazioni.

*Built at 2014-04-18T01:50:00Z-07:00*
