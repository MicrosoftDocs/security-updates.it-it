---
TOCTitle: 'MS09-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2009'
ms:assetid: 'ms09-jun'
ms:contentKeyID: 61240036
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2009
================================================================

Data di pubblicazione: martedì 9 giugno 2009 | Aggiornamento: mercoledì 10 giugno 2009

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a giugno 2009.

Con il rilascio dei bollettini di giugno 2009, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 giugno 2009. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini l'10 giugno 2009 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032395225). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-018">MS09-018</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Active Directory possono consentire l'esecuzione di codice in modalità remota (971055)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nelle implementazioni di Active Directory in Microsoft Windows 2000 Server e Windows Server 2003 e di Active Directory Application Mode (ADAM) se installato in Windows XP Professional e Windows Server 2003. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo in remoto del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-022">MS09-022</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nello spooler di stampa di Windows possono consentire l'esecuzione di codice in modalità remota (961501)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità relative allo spooler di stampa di Windows, che sono state segnalate privatamente. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un server interessato ha ricevuto una richiesta RPC appositamente predisposta. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-027">MS09-027</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (969514)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità che possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Word appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente che possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Excel appositamente predisposto che contiene un oggetto record non valido. Sfruttando una di queste vulnerabilità, un utente malintenzionato potrebbe assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-024">MS09-024</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente nei convertitori di Microsoft Works può consentire l'esecuzione di codice in modalità remota (957632)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel convertitore di Microsoft Works. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file di Works appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-026">MS09-026</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in RPC può consentire l'acquisizione di privilegi più elevati (970238)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità legata alla funzionalità RPC (Remote Procedure Call) di Windows per cui il motore di marshalling RPC non aggiorna correttamente il proprio stato interno. Questa vulnerabilità è stata divulgata pubblicamente. La vulnerabilità può consentire a un utente malintenzionato di eseguire codice arbitrario e di assumere il controllo completo di un sistema interessato. Le edizioni supportate di Microsoft Windows non sono fornite con server o client RPC soggetti allo sfruttamento di questa vulnerabilità. In una configurazione predefinita, gli utenti non possono subire un attacco volto a sfruttare questa vulnerabilità. Tuttavia, la vulnerabilità è presente nel runtime di esecuzione di Microsoft Windows RPC e può interessare applicazioni RPC di terze parti.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-025">MS09- 025</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (968537)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità divulgate pubblicamente e due vulnerabilità segnalate privatamente nel kernel di Windows che possono consentire l'acquisizione di privilegi più elevati. Sfruttando una di queste vulnerabilità, un utente malintenzionato può eseguire codice arbitrario e assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-020">MS09-020</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Internet Information Services (IIS) possono consentire l'acquisizione di privilegi più elevati (970483)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Internet Information Services (IIS). Alcune vulnerabilità possono consentire l'acquisizione di privilegi più elevati nel momento in cui un utente malintenzionato invia una richiesta HTTP appositamente predisposta a un sito Web che richiede autenticazione. Le vulnerabilità consentono a un utente malintenzionato di ignorare la configurazione di IIS che specifica il tipo di autenticazione consentito, ma non la verifica dell'elenco di controllo di accesso basato su file system (ACL), necessaria per stabilire se un file è accessibile da un dato utente. Lo sfruttamento di queste vulnerabilità limita comunque le autorizzazioni ottenute dall'utente malintenzionato a quelle concesse all'account utente anonimo dagli ACL del file system.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-023">MS09-023</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Ricerca di Windows può consentire l'intercettazione di informazioni personali (963093)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Ricerca di Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente esegue una ricerca che restituisce un file appositamente predisposto come primo risultato o se l'utente visualizza in anteprima un file appositamente predisposto dai risultati della ricerca. Per impostazione predefinita, il componente Ricerca di Windows non è preinstallato in Microsoft Windows XP e Windows Server 2003. È un componente facoltativo disponibile per il download. Il componente Ricerca di Windows installato nelle edizioni supportate di Windows Vista e Windows Server 2008 non è interessato da questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Moderato</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo del bollettino</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability Index</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-018">MS09-018</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Active Directory possono consentire l'esecuzione di codice in modalità remota (971055)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1138">CVE-2009-1138</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Esiste la possibilità di un'esecuzione di codice in modalità remota sui server Windows 2000 che espongono il servizio LDAP (TCP predefinito/389) sulla rete. Tuttavia, è improbabile lo sfruttamento della vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-018">MS09-018</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Active Directory possono consentire l'esecuzione di codice in modalità remota (971055)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1139">CVE-2009-1139</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">L'effetto di questa vulnerabilità sulla protezione è una perdita di memoria che può comportare la negazione del servizio. L'esecuzione di codice non è possibile.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2007-3091">CVE-2007-3091</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1140">CVE-2009-1140</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'accesso a informazioni personali, che in genere non comporta l'esecuzione di codice, bensì l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1141">CVE-2009-1141</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1528">CVE-2009-1528</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1529">CVE-2009-1529</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1530">CVE-2009-1530</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1531">CVE-2009-1531</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-019">MS09-019</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (969897)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1532">CVE-2009-1532</a></td>
<td style="border:1px solid black;">Per IE8 per Windows XP e Windows Vista senza DEP:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità<br />
<br />
Per IE8 per Windows Vista con DEP, Windows Server 2003 e Windows Server 2008:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">L'alta probabilità di sfruttamento della vulnerabilità è relativa a Internet Explorer 8 per Windows XP e per Windows Vista, se DEP non è abilitato.<br />
<br />
Per Internet Explorer 8 per Windows Vista, se DEP è abilitato, la probabilità di sfruttamento della vulnerabilità è bassa. ASLR/DEP e il fatto che i componenti .NET siano disabilitati di default nella navigazione in siti Internet sono fattori mitiganti.<br />
<br />
Per Internet Explorer 8 per Windows Server 2003 e Windows Server 2008, la probabilità di sfruttamento della vulnerabilità è bassa perché l'Enhanced Security Configuration disabilita gli script nella navigazione in siti Internet.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-020">MS09-020</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Internet Information Services (IIS) possono consentire l'acquisizione di privilegi più elevati (970483)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1122">CVE-2009-1122</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Bassa probabilità di esecuzione di codice ma alta probabilità di intercettazione di informazioni personali dovuta all'elusione dell'autenticazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-020">MS09-020</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Internet Information Services (IIS) possono consentire l'acquisizione di privilegi più elevati (970483)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1535">CVE-2009-1535</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Il codice pubblico è disponibile per l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0549">CVE-2009-0549</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0557">CVE-2009-0557</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0558">CVE-2009-0558</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0559">CVE-2009-0559</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Il pericolo di un'esecuzione di codice esiste solo per Office 2000. Attacchi contro le versioni successive di Office in genere non comportano l'esecuzione di codice.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0560">CVE-2009-0560</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0561">CVE-2009-0561</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-021">MS09-021</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (969462)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1134">CVE-2009-1134</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-022">MS09-022</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità nello spooler di stampa di Windows possono consentire l'esecuzione di codice in modalità remota (961501)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0228">CVE-2009-0228</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-022">MS09-022</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità nello spooler di stampa di Windows possono consentire l'esecuzione di codice in modalità remota (961501)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0229">CVE-2009-0229</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali senza alcuna possibilità di esecuzione di codice.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-022">MS09-022</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità nello spooler di stampa di Windows possono consentire l'esecuzione di codice in modalità remota (961501)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0230">CVE-2009-0230</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-023">MS09-023</a></td>
<td style="border:1px solid black;">Una vulnerabilità in Ricerca di Windows può consentire l'intercettazione di informazioni personali (963093)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0239">CVE-2009-0239</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-024">MS09-024</a></td>
<td style="border:1px solid black;">Una vulnerabilità presente nei convertitori di Microsoft Works può consentire l'esecuzione di codice in modalità remota (957632)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1533">CVE-2009-1533</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-025">MS09- 025</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (968537)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1123">CVE-2009-1123</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-025">MS09- 025</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (968537)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1124">CVE-2009-1124</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-025">MS09- 025</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (968537)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1125">CVE-2009- 1125</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-025">MS09- 025</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (968537)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1126">CVE-2009-1126</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Lo sfruttamento della vulnerabilità è più probabile in Windows 2000. Grazie alla protezione /GS la probabilità di esecuzione di codice dalla vulnerabilità legata al sovraccarico del buffer stack è ridotta in Windows XP e Windows Server 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-026">MS09-026</a></td>
<td style="border:1px solid black;">Una vulnerabilità in RPC può consentire l'acquisizione di privilegi più elevati (970238)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0568">CVE-2009-0568</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Questa vulnerabilità non interessa in maniera diretta alcun software Microsoft. Tuttavia, le workstation sulle quali i fornitori di software indipendenti implementano i servizi RPC potrebbero essere suscettibili all'esecuzione di codice in modalità remota se questo aggiornamento per la protezione non è installato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-027">MS09-027</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (969514)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0563">CVE-2009-0563</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-027">MS09-027</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (969514)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0565">CVE-2009- 0565</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
</tbody>
</table>
  
Software interessato e posizioni per il download  
------------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
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
</tr>
<tr>
<th colspan="8">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-018**](http://technet.microsoft.com/security/bulletin/ms09-018)
</td>
<td style="border:1px solid black;">
[**MS09-022**](http://technet.microsoft.com/security/bulletin/ms09-022)
</td>
<td style="border:1px solid black;">
[**MS09-019**](http://technet.microsoft.com/security/bulletin/ms09-019)
</td>
<td style="border:1px solid black;">
[**MS09-026**](http://technet.microsoft.com/security/bulletin/ms09-026)
</td>
<td style="border:1px solid black;">
[**MS09- 025**](http://technet.microsoft.com/security/bulletin/ms09-025)
</td>
<td style="border:1px solid black;">
[**MS09-020**](http://technet.microsoft.com/security/bulletin/ms09-020)
</td>
<td style="border:1px solid black;">
[**MS09-023**](http://technet.microsoft.com/security/bulletin/ms09-023)
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
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Active Directory in Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=bba6e20a-0345-46ae-a6f1-fd27fdee7c21)  
(KB969805)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=86378753-db24-44c2-a27d-cc0239f40ab8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=d645ad82-13c3-4030-808b-834e86ed3298)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fe8b3796-a407-4f41-89eb-35b4bcc24ff6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=155a79c1-e5e4-4f62-b4b0-53aca59f20ac)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=79b0481d-a3d7-477b-928a-a98cc79374af)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=8515a294-4f25-4dc5-860a-e7ad9b6c1c01)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[](http://technet.microsoft.com/security/bulletin/ms09-018)**MS09-018**
</td>
<td style="border:1px solid black;">
[](http://technet.microsoft.com/security/bulletin/ms09-022)**MS09-022**
</td>
<td style="border:1px solid black;">
[**MS09-019**](http://technet.microsoft.com/security/bulletin/ms09-019)
</td>
<td style="border:1px solid black;">
[**MS09-026**](http://technet.microsoft.com/security/bulletin/ms09-026)
</td>
<td style="border:1px solid black;">
[**MS09- 025**](http://technet.microsoft.com/security/bulletin/ms09-025)
</td>
<td style="border:1px solid black;">
[**MS09-020**](http://technet.microsoft.com/security/bulletin/ms09-020)
</td>
<td style="border:1px solid black;">
[**MS09-023**](http://technet.microsoft.com/security/bulletin/ms09-023)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM) installato in Windows XP Professional Service Pack 2 e Windows XP Professional Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cb2c9b76-0c65-4754-9941-d45a7c74a29a)  
(KB970437)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f2119aca-a98e-4810-be52-f38241443baf)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=3d7f63ee-d7c3-48a5-902e-60625405e97d)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=827b735c-660b-4723-b688-3297e107153a)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d9e27ce1-4e7c-437f-9477-e7805a33da08)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f033fa78-c451-44f8-aa6c-a49622c37f40)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6349e046-a3f8-4ae5-b8c3-c9879cc99e8f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 5.1 in Windows XP Professional Service Pack 2 e Windows XP Professional Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=97da589f-4534-42f6-9f29-967b5a33c542)  
(Importante)
</td>
<td style="border:1px solid black;">
[Ricerca di Windows 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=759f22cb-ea7f-49dd-a200-19cb83fffd8d)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=2ef3aaf0-a2a9-4c17-99ab-a0dc3d3f7e86)  
(KB970437)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=22699d09-1e68-456a-8733-bfad6667ebf5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=088f70eb-c5c5-426a-880a-18ed386d0b56)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e5d2c81e-ffab-4e3b-a59a-a55000597213)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=a24aedf0-7a31-4ee8-a9a6-998f1160c700)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=20734b70-37f1-47dd-bc09-d56f93577a55)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3769800e-af93-4a44-8a1e-b30cc54b226f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=8982e6d2-e1f7-4208-88e3-80b159a8e21a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Ricerca di Windows 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=50c56dd6-c34d-4632-a779-8bcf8fdb341b)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[](http://technet.microsoft.com/security/bulletin/ms09-018)**MS09-018**
</td>
<td style="border:1px solid black;">
[](http://technet.microsoft.com/security/bulletin/ms09-022)**MS09-022**
</td>
<td style="border:1px solid black;">
[**MS09-019**](http://technet.microsoft.com/security/bulletin/ms09-019)
</td>
<td style="border:1px solid black;">
[**MS09-026**](http://technet.microsoft.com/security/bulletin/ms09-026)
</td>
<td style="border:1px solid black;">
[**MS09- 025**](http://technet.microsoft.com/security/bulletin/ms09-025)
</td>
<td style="border:1px solid black;">
[**MS09-020**](http://technet.microsoft.com/security/bulletin/ms09-020)
</td>
<td style="border:1px solid black;">
[**MS09-023**](http://technet.microsoft.com/security/bulletin/ms09-023)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=d814ce65-a193-4027-a6cd-106d388830a6)   
(KB969805)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=f6f99957-f74f-4446-8734-a468283eebae)   
(KB970437)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=865414f8-3f77-4fee-acc6-6684a3dc0aa4)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=72a23752-86fb-4cc9-ab8e-63ffdfae5bec)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a980b867-c67f-4c61-b6db-e55c2ca68dc0)  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=298143f2-f37a-4a2c-86ac-9804d4ff1dad)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=62bb9e22-4f4b-4ffc-ba76-f626e94c79d5)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9356404c-d89a-4de0-b9b4-f6e1bdadf745)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=2bd4e410-dbd8-431a-b316-e1e2f1825c3a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Ricerca di Windows 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=e72ef31f-5161-4fe6-8ed3-6206e02cef31)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=0d1f23c8-06eb-4996-92eb-0eb635fd6a42)  
(KB969805)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=1a2badc7-c0a5-4032-a009-73ebe9d76313)  
(KB970437)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=197a6cc7-4ba3-4d2e-b621-0ef3da645ef2)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=2a03d3c4-e39d-43a3-8d42-216e9551be96)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5e7d6372-9c8c-449d-88fd-afd4f92ad9e6)  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4a5401d7-ca97-4734-a0e9-d7ffe0777e34)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=888b8dd8-d76c-42f5-a377-1f1750d3cf56)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5a3123af-173d-49eb-9997-14e82e764aee)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=ea363223-535d-4142-9aba-3890960c6259)  
(Importante)
</td>
<td style="border:1px solid black;">
[Ricerca di Windows 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ffc3680-f9bf-423b-96a7-102f4cc9c240)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=92e7808b-92ff-449d-bb73-ee8638e9ccd1)  
(KB969805)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=719efd62-fb33-447d-b6dd-2aaafbbad881)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=58efde2c-e0b8-4259-b19e-80564b834882)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a2d2907e-67ae-44a4-a805-8670e659ea57)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3084f46e-02b9-4d99-a7a1-033817f9bd9f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=13b50993-410f-4e7a-a33a-6d9b48dbb4d1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e6b806eb-e2c4-4436-8964-720db593055d)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-018**](http://technet.microsoft.com/security/bulletin/ms09-018)
</td>
<td style="border:1px solid black;">
[](http://technet.microsoft.com/security/bulletin/ms09-022)**MS09-022**
</td>
<td style="border:1px solid black;">
[**MS09-019**](http://technet.microsoft.com/security/bulletin/ms09-019)
</td>
<td style="border:1px solid black;">
[**MS09-026**](http://technet.microsoft.com/security/bulletin/ms09-026)
</td>
<td style="border:1px solid black;">
[**MS09- 025**](http://technet.microsoft.com/security/bulletin/ms09-025)
</td>
<td style="border:1px solid black;">
[**MS09-020**](http://technet.microsoft.com/security/bulletin/ms09-020)
</td>
<td style="border:1px solid black;">
[**MS09-023**](http://technet.microsoft.com/security/bulletin/ms09-023)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3ad8f037-2434-4dea-bfc3-9d3b4008b828)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e60215c3-b8b9-4e45-9d9f-b3fb0b47cce1)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=6f2730e9-b4fc-4f20-96cf-73f1be63f374)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5ca227c0-f2dd-429c-a542-e08e93527214)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c31b36f8-330c-4a0c-9a3d-7cbe9a1ab8c8)  
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
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=85c317cd-2a14-4747-9f50-3af3ddd3ae1b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=88185088-8c2c-4bc6-89b2-87f4d4849cf7)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5edb14f7-11ec-4180-9f0f-b2673f1c8d83)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=188adafe-1feb-46ad-b237-a88d35104dcd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d70a65f-07ce-4992-8bec-28fefd7587bc)  
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
<th colspan="8">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-018**](http://technet.microsoft.com/security/bulletin/ms09-018)
</td>
<td style="border:1px solid black;">
[**MS09-022**](http://technet.microsoft.com/security/bulletin/ms09-022)
</td>
<td style="border:1px solid black;">
[**MS09-019**](http://technet.microsoft.com/security/bulletin/ms09-019)
</td>
<td style="border:1px solid black;">
[**MS09-026**](http://technet.microsoft.com/security/bulletin/ms09-026)
</td>
<td style="border:1px solid black;">
[**MS09- 025**](http://technet.microsoft.com/security/bulletin/ms09-025)
</td>
<td style="border:1px solid black;">
[**MS09-020**](http://technet.microsoft.com/security/bulletin/ms09-020)
</td>
<td style="border:1px solid black;">
[**MS09-023**](http://technet.microsoft.com/security/bulletin/ms09-023)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0f18356d-9f09-4d24-8361-970c0d1ccac4)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a0e3f975-57da-43fa-ac12-3d14fd6ce939)\*\*  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=aaad301c-d232-4733-a0df-8e5d41bbfde8)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eaa26c6c-5bf7-4099-bb21-1e03de3a25ca)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98ba52b2-da1a-4939-a10e-d43b3a7e7ed4)\*  
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
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d0a6e8d-a31d-4f3d-a7d7-e61215bfebed)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=758edce7-2a82-4b2e-bd71-5b7075cc4b17)\*\*  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=faac92d4-4a2b-4bb5-8bd1-1519a9fa8147)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=447aaa4f-946b-4f23-b151-dcf46ea9f80e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dbaa5a72-c267-4907-a207-525c2803d7b9)\*  
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
Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bbac3deb-6c93-45aa-832c-02b915ac7f44)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=67d4c189-030d-42eb-98b9-7957ccd92592)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f33012b9-5d5b-4f72-8d49-a8e1c8bc1337)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e0e3ad56-a363-44ba-af4d-b7f551c88afd)  
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
 
**Note per Windows Server 2008**

**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Suite e software Microsoft Office

 
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
</tr>
<tr>
<th colspan="4">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-027**](http://technet.microsoft.com/security/bulletin/ms09-027)
</td>
<td style="border:1px solid black;">
[**MS09-021**](http://technet.microsoft.com/security/bulletin/ms09-021)
</td>
<td style="border:1px solid black;">
[**MS09-024**](http://technet.microsoft.com/security/bulletin/ms09-024)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3663e9f2-a952-4238-b902-90b5b09feb38)  
(KB969600)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=dd16e243-b8e2-4afb-86b6-4d60214598eb)  
(KB969683)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4bf95806-3d32-411b-9779-a81aebad45e9)  
(KB957838)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f1323be1-15f2-491b-abae-c03ba1394398)  
(KB969602)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=dd80ce95-0aec-4493-b9d1-c3dad95c3415)  
(KB969680)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b0ba8c9e-75ee-46bd-9e92-d4e6599309ad)  
(KB957646)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7cbc2587-2c8c-49b4-9f40-e4cdccb61ecd)  
(KB969603)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=10156044-a5a4-4312-98a7-1b1ced625ddb)  
(KB969681)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2003 Service Pack 3 con il convertitore file Microsoft Works 6–9](http://www.microsoft.com/downloads/details.aspx?familyid=a7ba3ea7-d06a-4c14-9107-9b92ef68fcae)\*\*\*  
(KB968326)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office System Service 2007 Pack 1 e Microsoft Office System 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2007 Service Pack 1 e Microsoft Office Word 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7e205108-4c28-4cab-a4d0-4ed3fd696473)  
(KB969604)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2bcd565a-6acb-407d-80da-0398526ddf99)\*  
(KB969682)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=bd47e1e5-cd2e-4c08-9864-471e97f38ca3)  
(KB969559)  
(Importante)
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
[**MS09-027**](http://technet.microsoft.com/security/bulletin/ms09-027)
</td>
<td style="border:1px solid black;">
[**MS09-021**](http://technet.microsoft.com/security/bulletin/ms09-021)
</td>
<td style="border:1px solid black;">
[**MS09-024**](http://technet.microsoft.com/security/bulletin/ms09-024)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=5557bfb7-ebb4-4c42-8042-41e830c4e550)  
(KB969661)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=5557bfb7-ebb4-4c42-8042-41e830c4e550)  
(KB969661)  
(Importante)
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
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=58326da2-eb75-4b42-b1bc-e70319defb58)  
(KB971822)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=58326da2-eb75-4b42-b1bc-e70319defb58)  
(KB971822)  
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
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=9d6d9eaa-8442-4184-8886-faab2803bde6)  
(KB971824)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=9d6d9eaa-8442-4184-8886-faab2803bde6)  
(KB971824)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-027**](http://technet.microsoft.com/security/bulletin/ms09-027)
</td>
<td style="border:1px solid black;">
[**MS09-021**](http://technet.microsoft.com/security/bulletin/ms09-021)
</td>
<td style="border:1px solid black;">
[**MS09-024**](http://technet.microsoft.com/security/bulletin/ms09-024)
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
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=20e6933d-85f8-4cec-9534-893789cd053e)  
(KB969685)  
(Importante)  
[Microsoft Office Excel Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=ac0530dc-7f63-4ad0-85c1-784ad28156cf)  
(KB969686)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Word Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Office Word Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=82980a40-f10c-4f02-b06c-3a12d4434a6b)  
(KB969614)  
(Importante)  
[Microsoft Office Word Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=82980a40-f10c-4f02-b06c-3a12d4434a6b)  
(KB969614)  
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
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=63bd8f14-e736-46ce-af66-d30f17461e5a)  
(KB969613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a8be8457-b0b6-455e-907e-d13be883adf2)  
(KB969679)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works 8.5
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Works 8.5](http://www.microsoft.com/downloads/details.aspx?familyid=628280fe-e035-4274-85f2-393d9bad543c)  
(KB967043)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Works 9
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Works 9](http://www.microsoft.com/downloads/details.aspx?familyid=f6fa110e-45c6-450f-ae47-c89a06e3f762)  
(KB967044)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 1 e Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=862e6ad1-8124-4060-93b1-2b882ef5ce3d)\*\*  
(KB969737)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1 e Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=b7b6e611-2c5d-4639-add9-972055789ecd)\*\*  
(KB969737)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Note per MS09-021**

\*Per Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB969682, gli utenti devono installare anche l'aggiornamento per la protezione per il [pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e il Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a8be8457-b0b6-455e-907e-d13be883adf2) (KB969679) per essere protetti dalle vulnerabilità descritte nel bollettino.

\*\*Questo aggiornamento si applica ai server che hanno installato Excel Services, come Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet, nella loro configurazione predefinita. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services.

**Nota per MS09-024**

\*\*\*Microsoft Office Word 2003 è interessato se è installato un convertitore di Works vulnerabile. I convertitori di Works per Microsoft Office Word 2003 possono essere scaricati da [Convertitore file di Microsoft Works 6–9](http://www.microsoft.com/downloads/details.aspx?familyid=bf41401e-70fa-465d-ae2e-cf44dbf05297&displaylang=en).

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://technet.microsoft.com/it-it/sms/bb676802.aspx) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/it-it/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043.aspx), incluso nell'[Application Compatibility Toolkit 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

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

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/it-it/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/it-it/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Joshua J. Drake di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-018
-   Justin Wyatt del [Beaverton il Distretto](http://www.beaverton.k12.or.us/home/) Scolastico per aver segnalato un problema ha descritto in MS09-018
-   David Bloom di [Google Inc.](http://www.google.com/) per avere collaborato con noi allo studio di un problema descritto nel bollettino MS09-018
-   Jorge Luis Alvarez Medina di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS09-019.
-   Haifei Li di [FortiGuard Global Security Research Team](http://www.fortiguardcenter.com/) di Fortinet per aver segnalato un problema descritto nel bollettino MS09-019
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-019
-   Peter Vreugdenhil, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-019
-   Wushi, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato due problemi descritti nel bollettino MS09-019
-   Nils, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-019
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-020
-   Bing Liu di [FortiGuard Global Security Research Team](http://www.fortiguardcenter.com/) di Fortinet per aver segnalato tre problemi descritti nel bollettino MS09-021
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver segnalato due problemi descritti nel bollettino MS09-021
-   [TELUS Security Labs Vulnerability Research Team](http://telussecuritylabs.com/) per aver segnalato un problema descritto nel bollettino MS09-021.
-   Sean Larsson e Joshua Drake di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-021
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-021
-   Jun Mao di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-022
-   Yair Amit di [IBM Rational Application Security](http://blog.watchfire.com/) per aver segnalato un problema descritto nel bollettino MS09-023
-   Shaun Colley di [NGS Software](http://www.ngssoftware.com/) e Yuji Ukai di [Fourteenforty Research Institute, Inc.](http://www.fourteenforty.jp/) per aver segnalato un problema descritto nel bollettino MS09-024
-   Thomas Garnier per aver segnalato due problemi descritti nel bollettino MS09-025
-   Wushi del [team509](http://www.team509.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-027
-   Nicolas Joly di [VUPEN Security](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS09-027

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (09 giugno 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (10 giugno 2009): sono stati corretti rating e note fondamentali per CVE-2009-1138 nell'Exploitability Index.

*Built at 2014-04-18T01:50:00Z-07:00*
