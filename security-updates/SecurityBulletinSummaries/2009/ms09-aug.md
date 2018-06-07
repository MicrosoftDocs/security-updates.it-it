---
TOCTitle: 'MS09-AUG'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2009'
ms:assetid: 'ms09-aug'
ms:contentKeyID: 61240031
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-aug(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2009
================================================================

Data di pubblicazione: martedì 11 agosto 2009 | Aggiornamento: martedì 27 ottobre 2009

**Versione:** 4.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati nel mese di agosto 2009.

Con il rilascio dei bollettini di agosto 2009, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio dei bollettini, pubblicata originariamente il 6 agosto 2009. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 12 agosto 2009 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di agosto](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032407484&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=128110">MS09-043</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Office Web Components possono consentire l'esecuzione di codice in modalità remota (957638)</strong><br />
<br />
Questo aggiornamento per la protezione risolve numerose vulnerabilità di Microsoft Office Web Components che possono consentire l'esecuzione di codice in modalità remota durante l'apertura di una pagina Web appositamente predisposta. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office, Microsoft Visual Studio, Microsoft ISA Server, Microsoft BizTalk Server</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=157861">MS09-044</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità legate alla connessione desktop remoto possono consentire l'esecuzione di codice in modalità remota (970927)</strong><br />
<br />
Questo aggiornamento per la protezione di livello critico risolve due vulnerabilità legate alla connessione desktop remoto Microsoft. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente malintenzionato riesce ad indurre un utente di Servizi terminal a collegarsi a un server RDP dannoso o se un utente visita un sito Web appositamente predisposto che sfrutta questa vulnerabilità. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Client di connessione desktop remoto per Mac</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=155974">MS09-039</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in WINS possono consentire l'esecuzione di codice in modalità remota (969883)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Windows Internet Name Service (WINS), che sono state segnalate a Microsoft privatamente. Ciascuna vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente riceve un pacchetto di replica WINS appositamente predisposto in un sistema interessato che esegua il servizio WINS. Per impostazione predefinita, WINS non è installato in alcuna versione dei sistemi operativi interessati. Solo i clienti che installano il componente manualmente sono interessati dal problema.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=155975">MS09-038</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nell'elaborazione di file Windows Media possono consentire l'esecuzione di codice in modalità remota (971557)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente che possono essere riscontrate nell'elaborazione di file Windows Media. Ciascuna vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file AVI appositamente predisposto. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=158695">MS09-037</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità di Microsoft Active Template Library (ATL), che sono state segnalate a Microsoft privatamente. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente carica un componente o un controllo appositamente predisposti ospitati su un sito Web dannoso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=155977">MS09-041</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel servizio Workstation può consentire l'acquisizione di privilegi più elevati (971657)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità presente nel servizio Workstation che è stata segnalata a Microsoft privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato crea un messaggio RPC appositamente predisposto e lo invia a un sistema interessato. Un utente malintenzionato che sfrutti questa vulnerabilità potrebbe eseguire codice non autorizzato e acquisire il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. L'utente malintenzionato deve essere in possesso di credenziali di accesso valide per sfruttare la vulnerabilità del sistema. La vulnerabilità non può essere sfruttata da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=155979">MS09-040</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Accodamento messaggi può consentire l'acquisizione di privilegi più elevati (971032)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità del servizio Accodamento messaggi di Windows (MSMQ), che è stata segnalata a Microsoft privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati in caso di ricezione di una richiesta appositamente predisposta inviata a un servizio MSMQ interessato. Per impostazione predefinita, il componente Accodamento messaggi non è installato nell'edizione interessata del sistema operativo e può essere attivato solo da un utente con privilegi amministrativi. Sono pertanto esposti a questa vulnerabilità solo i clienti che installano manualmente il componente Accodamento messaggi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=157296">MS09-036</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del codice ASP.NET in Microsoft Windows può consentire un attacco di tipo Denial of Service (970957)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità ad attacchi di tipo Denial of Service presente nel componente Microsoft .NET Framework di Microsoft Windows, che è stata segnalata a Microsoft privatamente. Tale vulnerabilità può essere sfruttata solamente se è stato installato Internet Information Services (IIS) 7.0 e se ASP.NET è stato configurato in modo da utilizzare la modalità integrata nelle versioni interessate di Microsoft Windows. Un utente malintenzionato può creare delle richieste HTTP anonime appositamente predisposte in grado di causare il blocco del server Web interessato fino a quando non venga riavviato il pool di applicazioni associato. I clienti che eseguono dei pool di applicazioni IIS 7.0 in modalità classica non sono interessati da questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft .NET Framework</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=157140">MS09-042</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Telnet (Server Message Block) può consentire l'esecuzione di codice in modalità remota (960859)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente nel servizio Microsoft Telnet. La vulnerabilità può consentire a un utente malintenzionato di ottenere le credenziali da utilizzare per poi effettuare nuovamente l'accesso ai sistemi interessati. Di conseguenza, l'utente malintenzionato può acquisire i diritti utente su un sistema identici ai diritti dell'utente connesso. Uno scenario di questo tipo può infine comportare l'esecuzione di codice in modalità remota sui sistemi interessati. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
**Come si utilizza questa tabella?**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo del bollettino                                                                                                                 | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                 | Note fondamentali                                                                                                                                                                                                                                                                                                                                    |  
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS09-036](http://go.microsoft.com/fwlink/?linkid=157296) | Una vulnerabilità del codice ASP.NET in Microsoft Windows può consentire un attacco di tipo Denial of Service (970957)                | [CVE-2009-1536](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1536) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | È probabile l'utilizzo di uno strumento per attacchi di tipo "Denial of Service". Tuttavia, la probabilità di sfruttamento della vulnerabilità per l'esecuzione di codice in modalità remota è scarsa.                                                                                                                                               |  
| [MS09-037](http://go.microsoft.com/fwlink/?linkid=158695) | Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908) | [CVE-2008-0015](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-0015) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet.**                                                                                                                                                                                                                                                                        |  
| [MS09-037](http://go.microsoft.com/fwlink/?linkid=158695) | Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908) | [CVE-2008-0020](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-0020) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-037](http://go.microsoft.com/fwlink/?linkid=158695) | Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908) | [CVE-2009-0901](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0901) | Nessuno                                                                                                               | (A questa vulnerabilità è già stata assegnata una valutazione dell'Exploitability Index nel [riepilogo dei bollettini di luglio](http://technet.microsoft.com/security/bulletin/ms09-jul). Questo perché la vulnerabilità è stata affrontata per la prima volta nel bollettino [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035)). |  
| [MS09-037](http://go.microsoft.com/fwlink/?linkid=158695) | Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908) | [CVE-2009-2493](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2493) | Nessuno                                                                                                               | (A questa vulnerabilità è già stata assegnata una valutazione dell'Exploitability Index nel [riepilogo dei bollettini di luglio](http://technet.microsoft.com/security/bulletin/ms09-jul). Questo perché la vulnerabilità è stata affrontata per la prima volta nel bollettino [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035)). |  
| [MS09-037](http://go.microsoft.com/fwlink/?linkid=158695) | Alcune vulnerabilità in Microsoft Active Template Library (ATL) possono consentire l'esecuzione di codice in modalità remota (973908) | [CVE-2009-2494](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2494) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-038](http://go.microsoft.com/fwlink/?linkid=155975) | Alcune vulnerabilità nell'elaborazione di file Windows Media possono consentire l'esecuzione di codice in modalità remota (971557)    | [CVE-2009-1545](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1545) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-038](http://go.microsoft.com/fwlink/?linkid=155975) | Alcune vulnerabilità nell'elaborazione di file Windows Media possono consentire l'esecuzione di codice in modalità remota (971557)    | [CVE-2009-1546](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1546) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-039](http://go.microsoft.com/fwlink/?linkid=155974) | Alcune vulnerabilità in WINS possono consentire l'esecuzione di codice in modalità remota (969883)                                    | [CVE-2009-1923](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1923) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-039](http://go.microsoft.com/fwlink/?linkid=155974) | Alcune vulnerabilità in WINS possono consentire l'esecuzione di codice in modalità remota (969883)                                    | [CVE-2009-1924](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1924) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Lo sfruttamento è più probabile se rivolto a un sistema operativo Windows 2000.                                                                                                                                                                                                                                                                      |  
| [MS09-040](http://go.microsoft.com/fwlink/?linkid=155979) | Una vulnerabilità in Accodamento messaggi può consentire l'acquisizione di privilegi più elevati (971032)                             | [CVE-2009-1922](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1922) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Un attacco remoto non è possibile in questa vulnerabilità.                                                                                                                                                                                                                                                                                           |  
| [MS09-041](http://go.microsoft.com/fwlink/?linkid=155977) | Una vulnerabilità nel servizio Workstation può consentire l'acquisizione di privilegi più elevati (971657)                            | [CVE-2009-1544](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1544) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Un utente malintenzionato richiederebbe l'autenticazione per sfruttare questa vulnerabilità.                                                                                                                                                                                                                                                         |  
| [MS09-042](http://go.microsoft.com/fwlink/?linkid=157140) | Una vulnerabilità in Telnet (Server Message Block) può consentire l'esecuzione di codice in modalità remota (960859)                  | [CVE-2009-1930](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1930) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Questa vulnerabilità è simile alle vulnerabilità precedenti relative alla riflessione di credenziali NTLM per le quali esiste già un codice dannoso.                                                                                                                                                                                                 |  
| [MS09-043](http://go.microsoft.com/fwlink/?linkid=128110) | Alcune vulnerabilità in Microsoft Office Web Components possono consentire l'esecuzione di codice in modalità remota (957638)         | [CVE-2009-0562](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0562) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-043](http://go.microsoft.com/fwlink/?linkid=128110) | Alcune vulnerabilità in Microsoft Office Web Components possono consentire l'esecuzione di codice in modalità remota (957638)         | [CVE-2009-1136](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1136) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Il codice dannoso per questa vulnerabilità è stato reso disponibile pubblicamente.                                                                                                                                                                                                                                                                   |  
| [MS09-043](http://go.microsoft.com/fwlink/?linkid=128110) | Alcune vulnerabilità in Microsoft Office Web Components possono consentire l'esecuzione di codice in modalità remota (957638)         | [CVE-2009-1534](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1534) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-043](http://go.microsoft.com/fwlink/?linkid=128110) | Alcune vulnerabilità in Microsoft Office Web Components possono consentire l'esecuzione di codice in modalità remota (957638)         | [CVE-2009-2496](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2496) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-044](http://go.microsoft.com/fwlink/?linkid=157861) | Alcune vulnerabilità legate alla connessione desktop remoto possono consentire l'esecuzione di codice in modalità remota (970927)     | [CVE-2009-1133](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1133) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |  
| [MS09-044](http://go.microsoft.com/fwlink/?linkid=157861) | Alcune vulnerabilità legate alla connessione desktop remoto possono consentire l'esecuzione di codice in modalità remota (970927)     | [CVE-2009-1929](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1929) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                            |
  
Software interessato e posizioni per il download  
------------------------------------------------
  
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
</tr>
<tr>
<th colspan="9">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
</td>
<td style="border:1px solid black;">
[**MS09-039**](http://go.microsoft.com/fwlink/?linkid=155974)
</td>
<td style="border:1px solid black;">
[**MS09-038**](http://go.microsoft.com/fwlink/?linkid=155975)
</td>
<td style="border:1px solid black;">
[**MS09-037**](http://go.microsoft.com/fwlink/?linkid=158695)
</td>
<td style="border:1px solid black;">
[**MS09-041**](http://go.microsoft.com/fwlink/?linkid=155977)
</td>
<td style="border:1px solid black;">
[**MS09-040**](http://go.microsoft.com/fwlink/?linkid=155979)
</td>
<td style="border:1px solid black;">
[**MS09-036**](http://go.microsoft.com/fwlink/?linkid=157296)
</td>
<td style="border:1px solid black;">
[**MS09-042**](http://go.microsoft.com/fwlink/?linkid=157140)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[RDP versione 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=027e757d-08d5-4932-b8c4-52ee1be1c864)\*\*\*  
(KB958471) e [RDP versione 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=ae72782e-920f-4176-a27b-c3b91d50c7d2) (KB958470)  
(Critico)  
[RDP versione 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=ae72782e-920f-4176-a27b-c3b91d50c7d2)\*\*\*  
(KB958470)  
(Critico)  
[RDP versione 5.2](http://www.microsoft.com/downloads/details.aspx?familyid=ae72782e-920f-4176-a27b-c3b91d50c7d2)\*\*\*  
(KB958470)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=b5b9228a-66c0-49e6-afde-cc2825a6851f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=5f80bf0b-898c-46ca-b20c-21e0e729c332)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 5.5 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6f9fcbe9-8496-4d23-8a16-b334157688c2)  
(KB973354)  
(Critico)  
[Microsoft Outlook Express 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f340af34-b9a0-44fb-b595-dbb346c727bf)  
(KB973354)  
(Critico)  
[Windows Media Player 9](http://www.microsoft.com/downloads/details.aspx?familyid=bd7c9fc4-61cb-4c23-9961-6d63f234731c)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=c773149a-f4fc-486a-b718-6b8ff7a36ae2)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=223e25d2-83d7-4cb7-85c4-46a42b8110e0)  
(KB973869)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=8ed8bad7-2885-452c-9c34-3982cd498be8)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=240977d6-3581-4058-b9f1-7847e4edcf8a)  
(Importante)
</td>
</tr>
<tr>
<th colspan="9">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
</td>
<td style="border:1px solid black;">
[**MS09-039**](http://go.microsoft.com/fwlink/?linkid=155974)
</td>
<td style="border:1px solid black;">
[**MS09-038**](http://go.microsoft.com/fwlink/?linkid=155975)
</td>
<td style="border:1px solid black;">
[**MS09-037**](http://go.microsoft.com/fwlink/?linkid=158695)
</td>
<td style="border:1px solid black;">
[**MS09-041**](http://go.microsoft.com/fwlink/?linkid=155977)
</td>
<td style="border:1px solid black;">
[**MS09-040**](http://go.microsoft.com/fwlink/?linkid=155979)
</td>
<td style="border:1px solid black;">
[**MS09-036**](http://go.microsoft.com/fwlink/?linkid=157296)
</td>
<td style="border:1px solid black;">
[**MS09-042**](http://go.microsoft.com/fwlink/?linkid=157140)
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
Nessuno
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[RDP versione 5.1 in Windows XP Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2a8830dd-8fb3-4556-a6e7-2c237235357f)  
(KB958470)  
(Critico)  
[RDP versione 5.2 per Windows XP Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cf9f9898-10c8-45ab-9df3-85e0b37e6046)\*\*\*\*  
(KB958469)  
(Critico)  
[RDP versione 5.2 su Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cf9f9898-10c8-45ab-9df3-85e0b37e6046)  
(KB958469)  
(Critico)  
[RDP versione 6.0 per Windows XP Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d1f82d76-eeb2-4ff4-9d2c-46882f214719)\*\*\*\*  
(KB956744)  
(Importante)  
[RDP Versione 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=d1f82d76-eeb2-4ff4-9d2c-46882f214719)\*\*\*\*  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2e8a68ee-eb24-424c-b084-450636ccaeec)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=c67b5506-00ea-47cc-a0e8-897057b7380c)  
(KB973354)  
(Critico)  
[Windows Media Player 9, Windows Media Player 10 e Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=34b2b14d-5811-4635-ba83-f837dcb03d04)  
(KB973540)  
(Critico)  
(solo Windows XP Service Pack 2)  
[Windows Media Player 9, Windows Media Player 10 e Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=ec84c98b-6bc7-442f-9280-d6e204280b2f)  
(KB973540)  
(Critico)  
(solo Windows XP Service Pack 3)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=4b4c6fc5-e8e6-4d89-a181-e231240468f9)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=bdfcd0c3-7c18-4e63-91dd-d8f82cd89592)  
(KB973869)  
(Critico)  
[Controllo Microsoft MSWebDVD ActiveX](http://www.microsoft.com/downloads/details.aspx?familyid=8b71bcc9-5146-4afc-8847-0af21d7fad36)  
(KB973815)  
(Critico)  
[Controllo ActiveX dell'oggetto HtmlInput](http://www.microsoft.com/downloads/details.aspx?familyid=46aa443c-4e7b-4bd5-8b4e-0068c3dc0e79)  
(KB973768)  
(Critico)  
(solo Media Center Edition 2005)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9c0e5bff-c248-4e87-a83b-82ba52f5299d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=93490aa7-9985-4658-b0d7-88fb3f27ada0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b3331388-1e52-4924-b512-23275a8fde84)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 5.2 in Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=948da99a-44ed-4390-b1b4-7ed3f15a9cda)  
(KB958469)  
(Critico)  
[RDP versione 6.0 per Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5061615f-fa8f-465f-ac8f-393998b7e91b)\*\*\*\*  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a1ff2ace-b9dc-4cf3-a151-ac6959bcb3a6)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=ede1a73a-e303-435e-a2c7-0281ce2370da)  
(KB973354)  
(Critico)  
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=bb98187a-8db9-47e4-88ac-15544c5268f6)  
(KB973540)  
(Critico)  
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=9e8b9027-4407-4c31-a2ba-9e094557d467)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=2f2b93fc-f977-4f23-af90-c27f744fad0a)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=d04a6959-41a4-4a87-b3ad-7455d8fe8b99)  
(KB973869)  
(Critico)  
[Controllo Microsoft MSWebDVD ActiveX](http://www.microsoft.com/downloads/details.aspx?familyid=85b2dcdb-cea9-4c4a-8ebd-50264e781ade)  
(KB973815)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7b64a454-d383-47e3-b469-b87e2b3c1a9f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=12e6be68-dc87-450e-927b-3c9b6873eb13)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a6ee7af3-3e39-4866-a893-92bf1c786cd4)  
(Importante)
</td>
</tr>
<tr>
<th colspan="9">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
</td>
<td style="border:1px solid black;">
[**MS09-039**](http://go.microsoft.com/fwlink/?linkid=155974)
</td>
<td style="border:1px solid black;">
[**MS09-038**](http://go.microsoft.com/fwlink/?linkid=155975)
</td>
<td style="border:1px solid black;">
[**MS09-037**](http://go.microsoft.com/fwlink/?linkid=158695)
</td>
<td style="border:1px solid black;">
[**MS09-041**](http://go.microsoft.com/fwlink/?linkid=155977)
</td>
<td style="border:1px solid black;">
[**MS09-040**](http://go.microsoft.com/fwlink/?linkid=155979)
</td>
<td style="border:1px solid black;">
[**MS09-036**](http://go.microsoft.com/fwlink/?linkid=157296)
</td>
<td style="border:1px solid black;">
[**MS09-042**](http://go.microsoft.com/fwlink/?linkid=157140)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 5.2](http://www.microsoft.com/downloads/details.aspx?familyid=60c79729-ef01-4630-bd67-ec63e7f8b56b)  
(KB958469)  
(Critico)  
[RDP versione 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=a37a2d8a-a5ce-4f06-bf07-8cafa16e7a59)\*\*\*\*  
(KB956744)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3a8d8ef9-ad41-4237-9cbb-daecfd8f216c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cba78658-899c-428f-8b04-cfe14ce3c255)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=3119ab1e-6729-40a1-b28f-0dab50502be6)  
(KB973354)  
(Critico)  
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=ab054890-983b-4414-ad0a-da1b2d2a4895)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=7d9369b5-0c54-4c17-bc62-fba0a7b4728c)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=bfc474c2-e3c5-40df-85d4-4ac666ff0561)  
(KB973869)  
(Critico)  
[Controllo Microsoft MSWebDVD ActiveX](http://www.microsoft.com/downloads/details.aspx?familyid=301ad191-8d3f-41d3-b41c-e2e863893f73)  
(KB973815)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9cb0477f-0656-47f5-bd35-5716e0572fbd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=52f59c56-2aba-4626-a90e-311e0e73c813)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3fe9c745-d87c-43b0-9b2a-356fb34282b4)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 5.2](http://www.microsoft.com/downloads/details.aspx?familyid=57393588-dc96-4bda-ab1e-ae550961e5d4)  
(KB958469)  
(Critico)  
[RDP versione 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=957c2e01-89a1-4550-aacb-de8ff896d762)\*\*\*\*  
(KB956744)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e132d051-4444-4ef1-9b6f-2d7da9d2e88e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=58a7c8d9-ec36-46a6-a89b-d8dfd989fda4)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=17bd00e3-810c-4a72-bd13-1b55ffb52a5e)  
(KB973354)  
(Critico)  
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=5890233a-d8f7-490c-8bf5-3ed4bd1c6991)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=90e0e014-ed7e-498a-9f61-18bb09a384b3)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=9f502d79-99a8-45dc-9876-2df27e14ffaa)  
(KB973869)  
(Critico)  
[Controllo Microsoft MSWebDVD ActiveX](http://www.microsoft.com/downloads/details.aspx?familyid=2ae71a65-5eee-4dd2-bc79-b7c5a73022bc)  
(KB973815)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=96fbf65f-1db2-432d-92a0-6669d8abaeb0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2f77ef7b-54f8-4260-b6a6-d62a0f85ef45)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e2a788e7-a9d1-4574-b106-f8ab44c6c4a2)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[RDP versione 5.2](http://www.microsoft.com/downloads/details.aspx?familyid=8f88a714-b917-4193-9002-19fa65722028)  
(KB958469)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=96c3f496-7b2f-4dbc-b484-216c9943c2b1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=187b02bd-73d6-4f72-81d1-d9477d495499)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=7978b921-c5b5-461f-a284-b9848f568aa9)  
(KB973354)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=ad1791b3-8553-4433-a9f7-8b4f857665be)  
(KB973507)  
(Critico)  
[Controllo ActiveX del componente per la modifica del DHTML](http://www.microsoft.com/downloads/details.aspx?familyid=82c0bb02-70ad-4605-a1f4-4698adf9f4ac)  
(KB973869)  
(Critico)  
[Controllo Microsoft MSWebDVD ActiveX](http://www.microsoft.com/downloads/details.aspx?familyid=5b8a8958-c3cd-4b24-85a2-1baacf92d218)  
(KB973815)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=11321f48-8997-4b99-982a-3ba4ad3f5992)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ad55c653-ee6b-4c92-b7f4-3923bb916546)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=4f625d39-29d4-44f9-b4bd-cd99f1ea422d)  
(Importante)
</td>
</tr>
<tr>
<th colspan="9">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
</td>
<td style="border:1px solid black;">
[**MS09-039**](http://go.microsoft.com/fwlink/?linkid=155974)
</td>
<td style="border:1px solid black;">
[**MS09-038**](http://go.microsoft.com/fwlink/?linkid=155975)
</td>
<td style="border:1px solid black;">
[**MS09-037**](http://go.microsoft.com/fwlink/?linkid=158695)
</td>
<td style="border:1px solid black;">
[**MS09-041**](http://go.microsoft.com/fwlink/?linkid=155977)
</td>
<td style="border:1px solid black;">
[**MS09-040**](http://go.microsoft.com/fwlink/?linkid=155979)
</td>
<td style="border:1px solid black;">
[**MS09-036**](http://go.microsoft.com/fwlink/?linkid=157296)
</td>
<td style="border:1px solid black;">
[**MS09-042**](http://go.microsoft.com/fwlink/?linkid=157140)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 6.0 in Windows Vista](http://www.microsoft.com/downloads/details.aspx?familyid=cf95a552-f6fd-4e35-815a-d16c015cd3ea)  
(KB956744)  
(Importante)  
[RDP versione 6.1 per Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cf95a552-f6fd-4e35-815a-d16c015cd3ea)  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=81fce7bd-f33c-4586-949d-ac40d415f755)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=3766aed9-93f5-478e-a5bf-b7ee0b577088)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=80de158d-157e-4c21-9154-c1dbd6e57cb3)  
(KB973507)  
(Critico)  
[Controllo ActiveX dell'oggetto HtmlInput](http://www.microsoft.com/downloads/details.aspx?familyid=59fefa17-0ad4-4a62-82be-e6a2b7a0aec3)  
(KB973768)  
(Critico)  
(solo Media Center Edition 2005)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=979ac9da-940f-49e7-91a2-b12db3708076)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Vista](http://www.microsoft.com/downloads/details.aspx?familyid=00afd94c-b483-4155-884f-b617acca6e7d)  
(Importante)
</td>
<td style="border:1px solid black;">
Solo Windows Vista: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d42444bb-5030-4b47-87fa-9df3a8c640ff) (KB972591) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=310f3aa6-c264-45a2-b24a-3f178b41830e)\*\*\*\*\* (KB972592)  
(Importante)  
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=cbf40800-f3b3-43da-ace1-d942d3378ccd) (KB972593) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=87c4a868-b3b5-467d-96a4-633532ab548f)\*\*\*\*\* (KB972594)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d77f406d-11cb-4d19-94ec-938b356c3427)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 6.0 in Windows Vista x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=5e19cef7-2413-4575-9597-c6273a097aad)  
(KB956744)  
(Importante)  
[RDP versione 6.1 in Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5e19cef7-2413-4575-9597-c6273a097aad)  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a6cea61a-4ad9-4e18-bf18-348ae4ae51c4)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=64edbd64-9faa-4f54-b0d5-836c683ca7cd)  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=82940d30-6a30-47ca-b184-2ac96e35c294)  
(KB973507)  
(Critico)  
[Controllo ActiveX dell'oggetto HtmlInput](http://www.microsoft.com/downloads/details.aspx?familyid=92de8a2e-2d50-4278-937e-ccb862c5ab8f)  
(KB973768)  
(Critico)  
(solo Media Center Edition 2005)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b9aa04cc-a5c5-47ae-bf0f-250cff275d26)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=a0c698aa-a913-4981-8798-6bbb8cacfb86)  
(Importante)
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d42444bb-5030-4b47-87fa-9df3a8c640ff) (KB972591) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=310f3aa6-c264-45a2-b24a-3f178b41830e)\*\*\*\*\* (KB972592)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=cbf40800-f3b3-43da-ace1-d942d3378ccd) (KB972593) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=87c4a868-b3b5-467d-96a4-633532ab548f) (KB972594)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7a41b8c1-f955-474e-a08e-5e73964327d1)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="9">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
</td>
<td style="border:1px solid black;">
[**MS09-039**](http://go.microsoft.com/fwlink/?linkid=155974)
</td>
<td style="border:1px solid black;">
[**MS09-038**](http://go.microsoft.com/fwlink/?linkid=155975)
</td>
<td style="border:1px solid black;">
[**MS09-037**](http://go.microsoft.com/fwlink/?linkid=158695)
</td>
<td style="border:1px solid black;">
[**MS09-041**](http://go.microsoft.com/fwlink/?linkid=155977)
</td>
<td style="border:1px solid black;">
[**MS09-040**](http://go.microsoft.com/fwlink/?linkid=155979)
</td>
<td style="border:1px solid black;">
[**MS09-036**](http://go.microsoft.com/fwlink/?linkid=157296)
</td>
<td style="border:1px solid black;">
[**MS09-042**](http://go.microsoft.com/fwlink/?linkid=157140)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=71c17a87-710b-434d-9b2a-2f471674915a)\*\*  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fdc96a07-ed79-4798-8077-b2e9ca64cd0f)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=85d9e69f-99a2-467f-bf37-4b47466a12d4)\*\*  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=ba423491-6c29-49f2-811b-ac3f9bbc58fc)\*  
(KB973507)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=24c77c27-0b7d-4a35-a871-b453f90e5913)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=cbf40800-f3b3-43da-ace1-d942d3378ccd) (KB972593) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=87c4a868-b3b5-467d-96a4-633532ab548f) (KB972594)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=62f2e0a6-5e68-41c7-a851-d99bcff6ff3e)\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=f095d2d5-4513-4ae1-96c7-cbcf83304261)\*\*  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e3afba4-6761-4b3d-98bb-4b4145e27b7f)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=9501c8c2-a526-4661-8cba-7847bace1aa0)\*\*  
(KB973540)  
(Critico)  
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=b9311953-889a-415f-a396-250a005e95cd)\*  
(KB973507)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48d0432e-704a-4bbb-b0a1-cd14069a8e93)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=cbf40800-f3b3-43da-ace1-d942d3378ccd) (KB972593) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=87c4a868-b3b5-467d-96a4-633532ab548f) (KB972594)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6e5d1db9-efef-4112-8138-62f14670cf0d)\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[RDP versione 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=65d0af4e-22a2-4524-a003-2f4858012fa8)  
(KB956744)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aa1bb13a-5905-48c4-8e74-a41104593046)  
(Critico)
</td>
<td style="border:1px solid black;">
[Componente Windows ATL](http://www.microsoft.com/downloads/details.aspx?familyid=e5612bb4-5f37-4b38-bd2e-f198c413371c)  
(KB973507)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c119223c-f4e0-449b-8e7b-a6bf11c98f94)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=cbf40800-f3b3-43da-ace1-d942d3378ccd) (KB972593) e [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=87c4a868-b3b5-467d-96a4-633532ab548f) (KB972594)  
(Importante
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b813c74-b2ae-4962-9ebb-1311193d9e2d)  
(Moderato)
</td>
</tr>
</table>
 
**Note per Windows Server 2008**

**\*Sono interessate le installazioni di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Note per MS09-044**

**\*\*\***Gli utenti della versione 5.0 di RDP su Microsoft Windows 2000 Service Pack 4 devono installare sia KB958471 sia KB958470.

**\*\*\*\***Gli amministratori potrebbero aver installato manualmente questo download preconfigurato.

Vedere anche la sottosezione "Software client per MAC," sotto la sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS09-036**

**\*\*\*\*\***Poiché IIS 7.0 non viene eseguito in Windows Vista Starter e in Windows Vista Home Basic, le seguenti edizioni non sono interessate: Windows Vista Starter (a 32 bit), Windows Vista Home Basic (a 32 bit) e Windows Vista Home Basic (a 64 bit).

#### Software client per MAC

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Desktop remoto
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-044**](http://go.microsoft.com/fwlink/?linkid=157861)
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
Client di connessione desktop remoto per Mac
</td>
<td style="border:1px solid black;">
[Client di connessione desktop remoto per Mac 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=cd9ec77e-5b07-4332-849f-046611458871)**\***  
(Importante)
</td>
</tr>
</table>
 
**Note per MS09-044**

**\***Questo download effettua l'aggiornamento del client di connessione desktop remoto per Mac 2.0 al client di connessione desktop remoto per Mac 2.0.1, che risolve la vulnerabilità.

Vedere anche la sottosezione "Sistema operativo Windows e suoi componenti," sotto la sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=60e2e4e7-aa75-441d-b6fc-7e850bf8e580)  
(KB947320)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=95c94c9a-6aca-42fb-9679-3234f06c72f7)  
(KB947319)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Office Web Components
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2000 Web Components
</td>
<td style="border:1px solid black;">
[Microsoft Office 2000 Web Components Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=60e2e4e7-aa75-441d-b6fc-7e850bf8e580)  
(KB947320)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office XP Web Components
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Web Components Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=60e2e4e7-aa75-441d-b6fc-7e850bf8e580)  
(KB947320)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Web Components
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Web Components Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=95c94c9a-6aca-42fb-9679-3234f06c72f7)  
(KB947319)  
(Critico)  
[Microsoft Office 2003 Web Components Service Pack 1 per Microsoft Office System 2007](http://www.microsoft.com/downloads/details.aspx?familyid=644008e0-77c9-4a02-ac9b-e30d0930c4be)\*  
(KB947318)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Small Business Accounting 2006
</td>
<td style="border:1px solid black;">
[Microsoft Office Small Business Accounting 2006](http://www.microsoft.com/downloads/details.aspx?familyid=0d77ddb3-4d34-4cfe-913b-d05981f59a82)  
(KB968377)  
(Critico)
</td>
</tr>
</table>
 
**Note per MS09-043**

**\***SQL Server 2008 e Microsoft Forefront Threat Management Gateway Medium Business Edition ridistribuiscono il componente interessato di Office 2003 Web Components per Microsoft Office System 2007. L'aggiornamento per il componente Office 2003 Web Components di Microsoft Office System 2007 rileva la necessità di aggiornare SQL Server 2008 e Microsoft Forefront Threat Management Gateway Medium Business Edition e offre l'aggiornamento ai clienti.

Vedere anche le altre sottosezioni, sotto la sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Visual Studio
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2003
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ba2915a0-f5f4-4e18-b0c0-534d2a948585)  
(KB969172)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS09-043**

Vedere anche le altre sottosezioni, sotto la sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software per la protezione e prodotti server Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Internet Security and Acceleration Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Internet Security and Acceleration Server 2004
</td>
<td style="border:1px solid black;">
[Microsoft Internet Security and Acceleration Server 2004 Standard Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=8f79a073-27e8-46ef-87d8-f09b93521326)\*  
(KB947826)  
(Critico)  
[Microsoft Internet Security and Acceleration Server 2004 Enterprise Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=8f79a073-27e8-46ef-87d8-f09b93521326)  
(KB947826)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Internet Security and Acceleration Server 2006
</td>
<td style="border:1px solid black;">
[Microsoft Internet Security and Acceleration Server 2006 Standard Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8f79a073-27e8-46ef-87d8-f09b93521326)  
(KB947826)  
(Critico)  
[Microsoft Internet Security and Acceleration Server 2006 Enterprise Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8f79a073-27e8-46ef-87d8-f09b93521326)  
(KB947826)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft BizTalk Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-043**](http://go.microsoft.com/fwlink/?linkid=128110)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft BizTalk Server 2002
</td>
<td style="border:1px solid black;">
[Microsoft BizTalk Server 2002](http://www.microsoft.com/downloads/details.aspx?familyid=495839b6-0322-4755-997d-4a7762c53333)  
(KB971388)  
(Critico)
</td>
</tr>
</table>
 
**Note per MS09-043**

\*Microsoft ISA Server 2004 Standard Edition viene fornito come prodotto autonomo. Microsoft ISA Server 2004 Standard Edition viene anche fornito come componente di Windows Small Business Server 2003 Premium Edition Service Pack 1 e Windows Small Business Server 2003 R2 Premium Edition.

Vedere anche le altre sottosezioni, sotto la sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Nota** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx010402221040.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/en-us/wsus/dd573344.aspx).

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/mapp/partners.mspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Alexander Pfandt di [Digitiria](http://www.digitaria.com/) per aver segnalato un problema descritto in MS09-036
-   Ryan Smith e Alex Wheeler di [IBM ISS X-Force](http://www.iss.net/) per avere inizialmente segnalato il problema descritto nel bollettino MS09-037
-   Robert Freeman di [IBM ISS X-Force](http://www.iss.net/) per aver segnalato un problema descritto nel bollettino MS09-037
-   David Dewey di [IBM ISS X-Force](http://www.iss.net/) per aver segnalato un problema descritto nel bollettino MS09-037
-   Ryan Smith di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato due problemi descritti nel bollettino MS09-037
-   Vinay Anantharaman di [Adobe Systems, Inc](http://www.adobe.com/) per aver segnalato due problemi descritti nel bollettino MS09-038.
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-039
-   Liu LiGen di [National University of Defense Technology](http://english.nudt.edu.cn/) per aver segnalato un problema descritto nel bollettino MS09-039
-   Nikita Tarakanov di [Positive Technologies Research Team](http://en.securitylab.ru/lab/) per aver segnalato un problema descritto nel bollettino MS09-040
-   Cody Pierce di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS09-041
-   Peter Vreugdenhil di [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato due problemi descritti nel bollettino MS09-043
-   Peter Vreugdenhil di [Zero Day Initiative](http://www.zerodayinitiative.com/) e Haifei Li di [FortiGuard Global Security Research Team](http://www.fortiguardcenter.com/) di Fortinet per aver segnalato un problema descritto nel bollettino MS09-043
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-043
-   Wushi del [Team509](http://www.team509.com/), che collabora con Zero Day Initiative, per aver segnalato un problema descritto nel bollettino MS09-044
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-044

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/default.aspx?ln=it).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 agosto 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 agosto 2009): È stato corretto l'elenco degli aggiornamenti RDP per Windows XP Service Pack 2 e Windows XP Service Pack 3 per MS09-044 affinché corrispondano al bollettino. Sono stati modificati i requisiti di riavvio per MS09-037, MS09-042 e MS09-044.
-   V2.0 (25 agosto 2009): Per MS09-044, è stato corretto il collegamento per il download della versione 5.2 di RDP per Windows XP Service Pack 2 (KB958469). Inoltre, è stata corretta la nota a piè di pagina che indicava una sequenza di installazione errata per KB958471 e KB958470. Per i clienti che hanno già installato gli aggiornamenti non è necessario eseguire una nuova installazione.
-   V3.0 (8 settembre 2009): nuovo rilascio del bollettino MS09-037 per fornire nuovi aggiornamenti per il controllo ActiveX dell'oggetto HtmlInput in Windows XP Media Center Edition 2005 e in tutte le edizioni supportate di Windows Vista.
-   V4.0 (27 ottobre 2009): Microsoft ha rilasciato di nuovo il bollettino MS09-043 per offrire nuovamente l'aggiornamento per Microsoft Office 2003 Service Pack 3 e per Microsoft Office 2003 Web Components Service Pack 3 per risolvere un problema di rilevamento. Si tratta di una modifica che riguarda esclusivamente il rilevamento; non sono state effettuate modifiche ai file binari. I clienti che hanno già aggiornato i propri sistemi non devono reinstallare questo aggiornamento.

*Built at 2014-04-18T01:50:00Z-07:00*
