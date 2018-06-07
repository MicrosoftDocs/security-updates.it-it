---
TOCTitle: 'MS11-APR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Aprile 2011'
ms:assetid: 'ms11-apr'
ms:contentKeyID: 61240054
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-apr(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Aprile 2011
================================================================

Data di pubblicazione: martedì 12 aprile 2011 | Aggiornamento: mercoledì 26 ottobre 2011

**Versione:** 6.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati ad aprile 2011.

Con il rilascio dei bollettini sulla sicurezza di aprile 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 07 aprile 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 13 aprile 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di aprile](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032455069&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214126">MS11-018</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet (2497640)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Questo aggiornamento per la protezione è considerato di livello critico per Internet Explorer 6, Internet Explorer 7 e Internet Explorer 8 sui client Windows e di livello moderato per Internet Explorer 6, Internet Explorer 7 e Internet Explorer 8 sui server Windows. Internet Explorer 9 non è interessato da queste vulnerabilità.<br />
<br />
Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212314">MS11-019</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel client SMB possono consentire l'esecuzione di codice in modalità remota (2511455)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Windows. Le vulnerabilità più gravi possono consentire l'esecuzione di codice in modalità remota, se un utente malintenzionato ha inviato una risposta SMB creata appositamente ad una richiesta SMB avviata dal client. Per sfruttare la vulnerabilità, un utente malintenzionato deve convincere l'utente a stabilire una connessione SMB a un server SMB creato appositamente.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212236">MS11-020</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente nel server SMB può consentire l'esecuzione di codice in modalità remota (2508429)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato crea un pacchetto SMB appositamente predisposto e lo invia a un sistema interessato. Le procedure consigliate e le configurazioni predefinite standard dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale attraverso queste vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214005">MS11-027</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit ActiveX (2508272)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente e una vulnerabilità divulgata pubblicamente relative al software Microsoft. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta che crea un'istanza di un controllo ActiveX con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Questo aggiornamento contiene anche i kill bit per tre controlli ActiveX di terze parti.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207931">MS11-028</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in .NET Framework può consentire l'esecuzione di codice in modalità remota (2484015)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Microsoft .NET Framework. La vulnerabilità può consentire l'esecuzione di codice in modalità remota su un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni XAML (XBAP). Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La vulnerabilità può consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web. Questa vulnerabilità potrebbe essere anche utilizzata dalle applicazioni Windows .NET per ignorare le restrizioni della protezione dall'accesso di codice (CAS).</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208524">MS11-029</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in GDI+ può consentire l'esecuzione di codice in modalità remota (2489979)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows GDI+ che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un file di immagine appositamente predisposto con software interessato o esplora un sito Web che presenta del contenuto appositamente predisposto. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212595">MS11-030</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella risoluzione DNS può consentire l'esecuzione di codice in modalità remota (2509553)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità nella risoluzione di Windows DNS che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato accede alla rete e crea un programma personalizzato per inviare query di trasmissione LLMNR appositamente predisposte ai sistemi di destinazione. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte. In questo caso, le porte LLMNR devono essere bloccate da Internet.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212243">MS11-031</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei motori di script JScript e VBScript</strong> <strong>può consentire l'esecuzione di codice in modalità remota (2514666)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità dei motori di script JScript e VBScript che è stata segnalata privatamente. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota durante la visualizzazione di un sito Web appositamente predisposto. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web. L'utente malintenzionato dovrebbe invece convincere le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212224">MS11-032</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente nel driver OpenType/CFF (Compact Font Format) può consentire l'esecuzione di codice in modalità remota (2507618)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel driver OpenType/CFF (Compact Font Format) di Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un contenuto reso con un carattere CFF appositamente predisposto. In nessuno di questi casi un utente malintenzionato può obbligare gli utenti a visualizzare il contenuto appositamente predisposto. L'utente malintenzionato deve invece convincere gli utenti a visitare un sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che li indirizzi al sito Web.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2489279)</strong><br />
<br />
Questo aggiornamento per la protezione risolve nove vulnerabilità di Microsoft Office segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210727">MS11-022</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft PowerPoint possono consentire l'esecuzione di codice in modalità remota (2489283)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità di Microsoft PowerPoint segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di PowerPoint appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La soluzione di <strong>fix automatico Microsoft</strong> per PowerPoint 2010, &quot;Disattiva modifiche nella Visualizzazione protetta per PowerPoint 2010&quot;, disponibile nell'<a href="http://support.microsoft.com/kb/2501584">articolo della Microsoft Knowledge Base 2501584</a>, blocca i vettori di attacco per sfruttare le vulnerabilità descritte in CVE-2011-0655 e CVE-2011-0656.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210206">MS11-023</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Office possono consentire l'esecuzione di codice in modalità</strong> <strong>remota (2489293)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Office. Le vulnerabilità potrebbero consentire l'esecuzione di codice in modalità remota se un utente apre un file di Office appositamente predisposto o se un utente apre un file di Office legittimo situato nella stessa directory di rete di un file della libreria appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212226">MS11-024</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità nell'Editor di frontespizio fax di Windows possono consentire l'esecuzione di codice in modalità remota (2527308)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Microsoft Windows che sono state divulgate pubblicamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di frontespizio appositamente predisposto (.cov) utilizzando l'Editor di frontespizio fax di Windows. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=209720">MS11-025</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella libreria di Microsoft Foundation Class (MFC) può consentire l'esecuzione di</strong> <strong>codice in modalità remota (2500212)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in alcune applicazioni create usando la libreria Microsoft Foundation Class (MFC). La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo associato a un'applicazione interessata e il file è situato nella stessa cartella di rete del file di libreria appositamente predisposto. L'attacco è possibile solo se l'utente visita un file system remoto o una condivisione WebDAV di dubbia provenienza e apre un documento da questa posizione che è poi caricato dall'applicazione interessata.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Strumenti e software Microsoft per gli sviluppatori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212523">MS11-026</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in MHTML può consentire l'intercettazione di informazioni personali (2503658)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente del gestore di protocolli MHTML in Microsoft Windows. Questa vulnerabilità può consentire l'intercettazione di informazioni personali durante la visualizzazione di un sito Web appositamente predisposto. In uno scenario di attacco dal Web, un sito Web potrebbe contenere un collegamento appositamente predisposto per sfruttare questa vulnerabilità. Un utente malintenzionato dovrebbe convincere gli utenti a visitare il sito Web e aprire il collegamento appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208110">MS11-033</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei convertitori di testo di WordPad può consentire l'esecuzione di codice in modalità remota (2485663)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file appositamente predisposto con WordPad. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2506223)</strong><br />
<br />
Questo aggiornamento per la protezione risolve trenta vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso localmente ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
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
  
**Come** **utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).

 
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=209720">MS11-025</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento non sicuro delle librerie in MFC</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3190">CVE-2010-3190</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207931">MS11-028</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento dello stack di .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3958">CVE-2010-3958</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212224">MS11-032</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico dello stack del carattere OpenType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0034">CVE-2011-0034</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208524">MS11-029</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer in GDI+</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0041">CVE-2011-0041</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214126">MS11-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nella gestione dei layout</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0094">CVE-2011-0094</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità viene sfruttata</strong> <strong>in un numero limitato di attacchi</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico dei valori integer in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0097">CVE-2011-0097</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow degli heap in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0098">CVE-2011-0098</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità WriteAV dell'analisi dei record in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0101">CVE-2011-0101</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210206">MS11-023</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento non sicuro delle librerie nel componente Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0107">CVE-2011-0107</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214126">MS11-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria MSHTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0346">CVE-2011-0346</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212314">MS11-019</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi della risposta del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0660">CVE-2011-0660</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212236">MS11-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi della transazione SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0661">CVE-2011-0661</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0662">CVE-2011-0662</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0665">CVE-2011-0665</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0666">CVE-2011-0666</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0667">CVE-2011-0667</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0670">CVE-2011-0670</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0671">CVE-2011-0671</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0672">CVE-2011-0672</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0673">CVE-2011-0673</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0674">CVE-2011-0674</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0675">CVE-2011-0675</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0676">CVE-2011-0676</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0677">CVE-2011-0677</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210727">MS11-022</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota dell'Atom di OfficeArt</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0976">CVE-2011-0976</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'indicizzazione della matrice in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0978">CVE-2011-0978</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento dell'elenco collegato in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0979">CVE-2011-0979</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al puntatore pendente in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0980">CVE-2011-0980</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1225">CVE-2011-1225</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1226">CVE-2011-1226</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1227">CVE-2011-1227</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1228">CVE-2011-1228</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1229">CVE-2011-1229</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1230">CVE-2011-1230</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1231">CVE-2011-1231</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1232">CVE-2011-1232</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1233">CVE-2011-1233</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1235">CVE-2011-1235</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1236">CVE-2011-1236</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1237">CVE-2011-1237</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1239">CVE-2011-1239</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1240">CVE-2011-1240</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1241">CVE-2011-1241</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1242">CVE-2011-1242</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214126">MS11-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nella gestione degli oggetti</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1345">CVE-2011-1345</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità viene sfruttata in un numero limitato</strong> <strong>di attacchi</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=208110">MS11-033</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi del convertitore di WordPad</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0028">CVE-2011-0028</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0103">CVE-2011-0103</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla sovrascrittura del buffer in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0104">CVE-2011-0104</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210121">MS11-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'inizializzazione dei dati in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0105">CVE-2011-0105</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212314">MS11-019</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento del pool di browser</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0654">CVE-2011-0654</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210727">MS11-022</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota in Time Bandit Techno-Color con virgola mobile</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0655">CVE-2011-0655</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210727">MS11-022</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota della directory Persist</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0656">CVE-2011-0656</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212595">MS11-030</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alle query DNS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0657">CVE-2011-0657</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212243">MS11-031</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla riallocazione della memoria di script</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0663">CVE-2011-0663</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=210206">MS11-023</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento dell'oggetto grafico in Microsoft Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0977">CVE-2011-0977</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1234">CVE-2011-1234</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212226">MS11-024</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria dell'Editor di frontespizio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3974">CVE-2010-3974</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212226">MS11-024</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free dell'Editor di frontespizio fax</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-4701">CVE-2010-4701</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212523">MS11-026</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alle richieste in formato MIME in MHTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0096">CVE-2011-0096</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente<br />
<br />
Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=211826">MS11-034</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1238">CVE-2011-1238</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214126">MS11-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Javascript</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1245">CVE-2011-1245</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
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
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="14">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=c3a8cec0-f947-4d4e-a6ae-c7f4f1f311b0)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0b7d0403-8965-4c62-970c-20b561f66713)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=689c5496-56c4-48a6-9f3d-b5f5aaf3e566)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f5378e7b-4619-4c42-9d9f-87b209c6d878)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ccb08a8a-f4d9-4320-8ffb-3fd4fe217987)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b031a496-aa74-4367-b2ae-24843c061745)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ce925e76-cb85-48f6-8c0f-e53fa2b09be6)  
(KB2446704)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=59266a9d-a319-4309-a046-7f15c6da0136)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2d433adb-bcaf-4c59-9405-a4892f8ccba3)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=637f4d4c-de07-4c6a-95f8-3bd0cbfe77b2)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=fbe1e7e3-1d5f-4daf-a4a5-67fe79292963)  
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9080c5a1-e638-4047-a70a-9367f1acced7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=50fc3869-f2fc-43c8-8049-aad62f2cb332)  
(KB2491683)  
(Importante)  
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a8220a21-02fc-4ad6-988d-844276b2fd66)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7f0a4616-8e3e-4925-9d95-ce6e614e45ae)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6753ca98-feb4-4c7f-9969-9294038a2bbb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=39e55bbf-c1c5-4696-bfe7-632e997cd98e)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=986f07ae-0fdc-4be2-8a74-5eb56d4300ef)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ed88f183-dd06-46f6-ae8a-a594a752f248)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=6d3433ee-c2e1-433f-a3d9-c049d66e2190)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c01441da-8933-4f60-923b-d9b00db8ba3d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7ee202da-a711-42ee-bea3-7202a70e4ea0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eddd2964-9765-461d-9df8-2c05402948e8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ce925e76-cb85-48f6-8c0f-e53fa2b09be6)  
(KB2446704)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3797009a-b9a4-4e83-8614-e1589c8b5090)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29ff546e-a232-4f23-a223-c029c71ff1c6)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.6 e VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=a5586246-2908-4def-9298-c16060098197)  
(KB2510587)  
(Critico)  
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=3a5f65e0-bb00-4e55-b8b5-77751349a3ec)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=57aa7ee2-254d-40b5-9ff0-cba969daf45a)  
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2374e09a-cb3e-4bc3-bb4b-53b611025121)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b93311b4-1b8f-478d-8833-750c5e01e6f8)  
(KB2491683)  
(Importante)  
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0f60fc99-cd88-4237-8b31-a4e618502f7e)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b01fe9a5-66a4-4683-963b-e78aea214579)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3c94bc96-99ea-44a1-9052-e69de5e21f81)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=83771177-284e-4918-86a9-980e8229c7c9)  
(Importante)
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=b902c58a-9e2f-4352-8d2f-fffda5344598)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5c464287-3dab-4342-a38d-a12719d3b158)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=45feb35b-b24e-4160-adb0-d0b7ae530e90)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d46fe0bf-28c2-4696-87bc-dd3c8287fc28)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=64c550d4-c927-4382-91e1-473ed6790819)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=53756404-39e4-43af-81e9-81471536aa66)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ce925e76-cb85-48f6-8c0f-e53fa2b09be6)  
(KB2446704)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fd284233-e177-4064-9b02-f83dcb727dbe)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=753ed6e3-df2e-4b2d-9e9f-7275cd94d214)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.6 e VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=e026f2ed-8a20-4268-9b29-04a78bde1999)  
(KB2510587)  
(Critico)  
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=5b0ed0b2-07f9-43da-bb5d-5be5a45969ee)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=01aa2beb-9fc1-40f0-a2a4-bcd3d9cb31f8)  
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5d71d3f5-fd6b-4f3b-8389-37c899748d4b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=edda8cce-b764-4ef1-afbe-391fbd087362)  
(KB2491683)  
(Importante)  
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bf084b4c-aac9-4cc6-bb30-87fc96ba9430)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0209a004-f23a-40d9-991f-864046f4605f)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9fbfc742-6c74-49a2-b3cc-e1d5d8c84b77)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=af320f27-bb3a-4e76-a279-4632267c8761)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=5d8f14d1-85cc-478f-8b50-5c355a331f59)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9d8bbea9-c456-4569-ad96-c2cd0f5fae7e)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=979d2ec5-5114-4ec7-aa97-e9289c590cbb)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ca0fb4d3-7651-4760-83fa-b71c86cbe459)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ef62db94-4f72-4245-ac9f-6391035e2516)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c8d59f49-45ec-4527-b3a8-4925f710bbfd)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ce925e76-cb85-48f6-8c0f-e53fa2b09be6)  
(KB2446704)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d5adaf4e-4cd7-42ea-8202-31b5c856f5e3)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a0192dbc-4d0d-4555-9ef7-3e10209a6389)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.6 e VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=83ce6c99-a57d-4ed1-972b-a6b6798e6675)  
(KB2510587)  
(Critico)  
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=af791715-77a1-405b-a69e-d63f75dd7ccd)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=bf0a2966-25c4-4717-bcd6-016ce610d220)  
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3a498ff0-21d9-493a-b127-6bc20f1baf95)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f04d939a-da11-4a9f-9e03-b6c3bf3ca58b)  
(KB2491683)  
(Importante)  
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=12b01f3a-ccf8-41c1-ac5a-e417a6ddbe95)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6c287571-54ea-4298-8b7d-b98b2c830cc3)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=897b97b0-1bab-4b1b-b417-950fab0d4a65)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9c95f81c-9812-4070-88d7-34422c638e42)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=8afe86fc-58b4-4a95-b047-c09138fa4f5e)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f1abfb48-3c8a-4b2d-b739-cc61628b387d)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=87eb8b93-9829-45ec-9528-52787732044e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=79aeb3cd-7c73-467b-b91e-02c6ea01e911)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=9c784734-f44f-4a3c-8223-6289f7dc2ad8)  
(Nessun livello di gravità<sup>[1]</sup>)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ce925e76-cb85-48f6-8c0f-e53fa2b09be6)  
(KB2446704)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=72a513bb-f901-4992-8562-d1afe1afec8a)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=f5ad6963-2d6a-4d59-9e25-4fc088647fcd)  
(Importante)
</td>
<td style="border:1px solid black;">
[JScript 5.6 e VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=b7d36bae-7ca4-4a40-9efb-13f484fa5518)  
(KB2510587)  
(Critico)  
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=3f519013-ed14-41a8-aa45-cf8b095d3152)  
(KB2510581)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c71f4398-2e3b-4b81-a650-8806e618db7f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=efb575c7-3259-49b1-b59c-89d9544e37a6)  
(KB2491683)  
(Importante)  
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=03a7ee49-7bd6-4215-9779-1b48c10d08b9)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3fb450a0-d087-4f36-9301-05ffbf94cc1a)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ede38974-4e57-4ea1-8731-b91e96534693)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=f58cf64a-bf31-4496-be75-5775a123338b)  
(Importante)
</td>
</tr>
<tr>
<th colspan="14">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=00c3c176-feff-4022-ac4c-2d4732ca3d78)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5ea94705-4f76-4b0d-bbbc-afb5e75204bf)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=da8dd55d-6630-484e-836c-9feeab5cc311)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d6eddff4-a242-4dec-9d84-72891db2b754)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80bf050a-9aff-4cd4-8e2f-196b0a92b1c0)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=94b6a1b3-e048-437b-a224-2a64b3735bc3)  
(KB2449741)  
(Critico)  
Solo Windows Vista Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1407aaec-b3e0-404c-b84f-0c8e808614c4)  
(KB2449742)  
(Critico)  
Windows Vista Service Pack 1 e Windows Vista Service Pack 2:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4ff2e440-79c2-4045-b225-913d1740fdb9)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2a17e44f-54aa-423d-b3c7-a4f404f7c28b)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=719e2c86-30e5-4cd5-94f4-d6de54efee5f)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=21decb84-75ef-4bde-a802-1e661a505e94)<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7c4fc81-d1ef-4378-862b-e955d75fb2de)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=11a8f240-51b3-4e31-a24a-a235179f3396)  
(KB2491683)  
(Importante)  
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e6cba040-9d7c-4777-a2f7-e4dd11dfb845)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c8fce0fb-4c90-479b-8ce9-75e60d52d256)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b4743167-9614-445a-9e91-10efdac505a8)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=79f52733-44e4-47b6-86ca-1395a095b4e7)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=bc63b233-9db0-4fb1-a61c-fa7e9e44ba10)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=040f8b46-f458-4a72-a1b0-ad8a65a1194c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2878c587-6544-40b4-9288-fc3b3ce1128d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a81412d0-2516-4bf4-87f7-3e41ebf6b82b)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=94b6a1b3-e048-437b-a224-2a64b3735bc3)  
(KB2449741)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1407aaec-b3e0-404c-b84f-0c8e808614c4)  
(KB2449742)  
(Critico)  
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4d826026-e62a-4cec-8682-49fbe7f65cd6)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e708d24f-e348-4c4d-99ed-e78dd1689d01)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=89b9d01e-bcbc-4f2c-973b-51051494f406)  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=d4ac199e-7bf8-4661-a4e5-c53719b2673a)<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8d654a78-0e4f-452c-8874-fbf478813857)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=61db662e-88d7-4454-b4b7-e987728fb137)  
(KB2491683)  
(Importante)  
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1c942282-0f80-46c1-aeef-1ef948e105a3)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7da10b64-d0a9-4e42-aa3a-87c657122a8c)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7e410d5c-b9f7-4a63-8300-36b2d57c6128)  
(Importante)
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7d8603b8-bb52-4cf6-be8b-bb3475d30fc5)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d5d76e90-1cef-47e8-9d8d-2c5a43f42ba3)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f8c9390a-5ca1-492a-9e35-a516de48deb5)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=31c48ba9-7774-4633-862d-5c27c3703584)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c3247886-76d0-4292-be9d-3e9b0221c46a)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=94b6a1b3-e048-437b-a224-2a64b3735bc3)\*\*  
(KB2449741)  
(Critico)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1407aaec-b3e0-404c-b84f-0c8e808614c4)\*\*  
(KB2449742)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)\*\*<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fbada866-7d36-4b85-acde-fd856a998737)\*\*\*  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9894be38-a582-4c15-ad0e-cc3afab2aebc)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=d8b33ffd-eff1-4a10-b6fc-3c8f01e0fec5)\*\*  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=afd128ff-717f-4d98-b214-f2c28d59623d)\*\*<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9105377e-83c7-4010-8fd6-26e42e98c2cc)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=90f56368-776b-4d45-ad68-91afbd316d25)\*\*  
(KB2491683)  
(Importante)  
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fa972742-1166-4a9e-ab64-6a4f968f9c6d)\*  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=036f1285-7484-4e3b-8799-2c6c08166596)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c6ac26b8-8cc8-40fe-baab-22bf13df1aa8)\*  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c6d58f64-bdd5-4fe6-96f4-9641b8e7b570)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=51203a31-368b-4b47-96a5-9e9e5a55cd76)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b0cfd5e0-6de5-4863-b5e4-b223a0e36d72)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=de843115-cf98-4511-aa93-f620e4572555)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=51521b6b-94a7-4bcf-ad5f-fc304728b10f)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 solo per sistemi x64:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=94b6a1b3-e048-437b-a224-2a64b3735bc3)\*\*  
(KB2449741)  
(Critico)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1407aaec-b3e0-404c-b84f-0c8e808614c4)\*\*  
(KB2449742)  
(Critico)  
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)\*\*<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8f4ddfcb-374d-4cad-8c61-2b988b46f628)\*\*\*  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2d7d2021-020f-4cc9-a027-258d7e5faec9)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=6c2e6b87-afcd-461a-8a43-9a2fb277b18a)\*\*  
(KB2510581)  
(Critico)  
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=40e8beca-0b5a-43b0-98f8-b32a82ad65d6)\*\*<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=060e8b20-edca-4427-9d60-eb57261eb668)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=22a001fc-5c2e-4539-85c9-0c2054a1777d)\*\*  
(KB2491683)  
(Importante)  
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fc250c8a-ebaf-4264-9393-dc23cc372d9f)\*  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1438cec8-8dab-4510-ad75-dc6959dac0d8)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ac49f5d3-5e2f-4916-99be-a3254278da7e)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f6f6f22c-fc7f-4e96-b6b5-be3c1acecf6e)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8eaf51cd-2f6e-4bbc-bc4f-9deed03649ac)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b89b8e28-cd98-4bcc-8729-5e51d52d1e92)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7c38b0d-7240-420a-88d3-2749a40e386f)  
(Nessun livello di gravità<sup>[1]</sup>)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=94b6a1b3-e048-437b-a224-2a64b3735bc3)  
(KB2449741)  
(Critico)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1407aaec-b3e0-404c-b84f-0c8e808614c4)  
(KB2449742)  
(Critico)  
Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2fd71543-0e18-4907-89b9-355d24d7db69)  
(KB2412687)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c0275df0-10ac-4500-ab86-b7e9a34f8e1d)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.7 e VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=afb49d24-1913-4e5f-a3ea-c6c9642e2017)  
(KB2510581)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2b8571cb-2dae-4bff-9f13-feb89840044c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=421024f1-aa86-459e-b6de-53851a3fcba2)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f35ecdd1-6b5c-40e7-a00b-ca083bdf5cba)  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3b93de4f-01f4-4efd-afc1-31d87b92fad2)  
(Importante)
</td>
</tr>
<tr>
<th colspan="14">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=59676b71-8b9d-4230-a9e0-b20db3e3ec7e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0dcba089-19f7-46ca-9e52-24eaebad4715)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d3ef905b-3584-4842-9ec2-cf3856305d49)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=46510959-e4a2-4c21-b33c-fd3d97b3ac3d)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi a 32 bit:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=157aa425-953c-4fc9-ab76-4e65d4be8baa)  
(KB2446709)  
(Critico)  
Solo Windows 7 per sistemi a 32 bit Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=8f87b8aa-1a2a-405e-aee0-9247d553756a)  
(KB2446710)  
(Critico)  
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8fdae09b-d1bb-4ef5-aa45-2a05f2a5e12d)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=17ebf291-fdae-4e78-9377-871b3103ce16)<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=751c45ea-0943-4948-807f-8716c6ff9198)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=bf762b86-b949-4e84-8ca4-93ebe669c1b8)  
(KB2491683)  
(Importante)  
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0f5a122e-dd5e-4b08-881a-f13b38642720)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=aed201c1-f1fb-4df9-8875-6f57ea0eb15b)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6e7ff003-ff3f-49bb-8e45-d869885dd8d7)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3a998678-2678-489e-8711-39322663147d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b7fd356a-56d0-4638-8901-40acfa600f25)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7ddc943b-6868-4e8f-a869-89b47133c287)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=432555cf-aed8-4329-a74f-526441521082)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=157aa425-953c-4fc9-ab76-4e65d4be8baa)  
(KB2446709)  
(Critico)  
Solo Windows 7 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=8f87b8aa-1a2a-405e-aee0-9247d553756a)  
(KB2446710)  
(Critico)  
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=40879dfb-efa4-41ba-8d5c-22e926a55eef)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=c95ad86d-da58-4d7a-9ffd-8441f92baaa5)<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=976c882a-bc07-4128-927f-82a2df46cf45)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a6793ecf-a3f6-4989-8e4c-c5c0005f9ac4)  
(KB2491683)  
(Importante)  
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=658301f1-103a-48a2-9b67-61cf8e1dad50)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1a32bf04-7eed-4d27-a8e4-054b4a5b76cb)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0c0aef7e-501c-4ca3-ae7f-497a8c169121)  
(Importante)
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-018**](http://go.microsoft.com/fwlink/?linkid=214126)
</td>
<td style="border:1px solid black;">
[**MS11-019**](http://go.microsoft.com/fwlink/?linkid=212314)
</td>
<td style="border:1px solid black;">
[**MS11-020**](http://go.microsoft.com/fwlink/?linkid=212236)
</td>
<td style="border:1px solid black;">
[**MS11-027**](http://go.microsoft.com/fwlink/?linkid=214005)
</td>
<td style="border:1px solid black;">
[**MS11-028**](http://go.microsoft.com/fwlink/?linkid=207931)
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-030**](http://go.microsoft.com/fwlink/?linkid=212595)
</td>
<td style="border:1px solid black;">
[**MS11-031**](http://go.microsoft.com/fwlink/?linkid=212243)
</td>
<td style="border:1px solid black;">
[**MS11-032**](http://go.microsoft.com/fwlink/?linkid=212224)
</td>
<td style="border:1px solid black;">
[**MS11-024**](http://go.microsoft.com/fwlink/?linkid=212226)
</td>
<td style="border:1px solid black;">
[**MS11-026**](http://go.microsoft.com/fwlink/?linkid=212523)
</td>
<td style="border:1px solid black;">
[**MS11-033**](http://go.microsoft.com/fwlink/?linkid=208110)
</td>
<td style="border:1px solid black;">
[**MS11-034**](http://go.microsoft.com/fwlink/?linkid=211826)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
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
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c7b2482b-44bf-4c01-99d8-f93868659a24)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=27a3847b-695b-4f60-aea5-86b0dbe68945)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c4352802-9c5a-4c07-8303-3a4b78d3f954)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e4fa8ed0-acb0-4864-be18-29a27f8501de)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=157aa425-953c-4fc9-ab76-4e65d4be8baa)\*  
(KB2446709)  
(Critico)  
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=8f87b8aa-1a2a-405e-aee0-9247d553756a)\*  
(KB2446710)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)\*<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2084c726-187e-41f9-9bea-da18f490d29e)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=aecc2c7a-285c-409d-be23-c5b4b5449496)\*\*<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6f2a52cc-4833-448d-becc-2eac1a447410)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=465c0478-6a74-4b00-8608-938cc492549f)\*\*  
(KB2491683)  
(Importante)  
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4c5c3a0f-0672-49d0-bcbd-c7f40e11d092)\*  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=665faa7e-2368-4421-9dd5-ea6df2c79498)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2fc66224-45c6-4e8f-ad00-6a1ec30b4505)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=af6db318-fbec-4286-a3a7-4081620146e5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e7d3f21-bdbd-4826-855d-85422aa5f836)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0005377b-443f-44ca-a890-620b2dcea6f1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d7bcf4d7-b697-4c5f-adbc-a2b3700e0ad5)  
(Moderato)
</td>
<td style="border:1px solid black;">
Solo Windows Server 2008 R2 per sistemi Itanium:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=157aa425-953c-4fc9-ab76-4e65d4be8baa)  
(KB2446709)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi Itanium Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=8f87b8aa-1a2a-405e-aee0-9247d553756a)  
(KB2446710)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1:  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=91aa6772-4811-4a58-9bc0-8aa271ed99df)<sup>[1]</sup>
(KB2446708)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=34d2793e-a2cd-49f6-b524-6598ea86175f)  
(Critico)
</td>
<td style="border:1px solid black;">
[JScript 5.8 e VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=e1bc0ed8-5a93-4d01-b407-919dfd894b5f)<sup>[1]</sup>
(KB2510531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c6ca0b7c-8151-4d54-aa9b-5ec2b75d8ab6)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1a993f8c-d28a-4a95-a3c6-059f06e75461)  
(KB2506212)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=140ea384-2877-401f-ac3b-f84f6966e970)  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=485ccf96-27a0-499e-9f52-2836b73d26d2)  
(Importante)
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*\*Le installazioni con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano, come indicato, le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 se installati utilizzando l'opzione di installazione di Server Core, anche se i file interessati da questa vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS11-027**

<sup>[1]</sup>Questo specifico sistema operativo non è interessato dalle vulnerabilità descritte in questo bollettino. L'aggiornamento disponibile imposta i kill bit per i controlli di terze parti.

**Nota per MS11-028**

<sup>[1]</sup>**.NET Framework 4.0 e .NET Framework 4.0 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4.0 e .NET Framework 4.0 Client Profile. .NET Framework 4.0 Client Profile è un sottoinsieme di .NET Framework 4.0. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4.0 sia .NET Framework 4.0 Client Profile. Per ulteriori informazioni, vedere: [Installare .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

**Nota per MS11-029**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS11-031**

<sup>[1]</sup>I Sistemi con Internet Explorer 9 non sono interessati e non richiedono questo aggiornamento. È necessario il corretto aggiornamento delle versioni di JScript e VBScript installate sui sistemi che non sono stati aggiornati con Internet Explorer 9. Per le istruzioni su come determinare le versioni di JScript e VBScript installate sul sistema in uso, vedere il bollettino.

**Nota per MS11-024**

Dove ci sono due aggiornamenti disponibili per lo stesso sistema operativo, installare entrambi gli aggiornamenti.

#### Applicazioni e software Microsoft Office

 
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
</tr>
<tr>
<th colspan="5">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-021**](http://go.microsoft.com/fwlink/?linkid=210121)
</td>
<td style="border:1px solid black;">
[**MS11-022**](http://go.microsoft.com/fwlink/?linkid=210727)
</td>
<td style="border:1px solid black;">
[**MS11-023**](http://go.microsoft.com/fwlink/?linkid=210206)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
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
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6c87c2a9-3705-4680-8a9b-63b6ec83674d)  
(KB2509461)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=db2c5cfe-588c-4646-b86a-3fb8248f7af4)  
(KB2466169)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0d215ab6-c9be-4f43-9501-658bb7ef008e)  
(KB2464617)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6c87c2a9-3705-4680-8a9b-63b6ec83674d)  
(KB2509461)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=916a076d-d754-4092-b23d-c8826db7e397)  
(KB2502786)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2ce8349f-79b1-41ef-a1c0-cbe40ccf9f20)  
(KB2464588)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=8b68cf68-1606-4649-b860-a64702c6cf33)  
(KB2509503)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5ae34fe0-03bd-48a9-a7ac-de8f7b1aff90)<sup>[1]</sup>
(KB2464583)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6b2526fe-a061-4a17-992e-ac867bef130e)  
(KB2464594)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dbba0cd4-ab72-4e2b-9524-fd6be27f0b02)  
(KB2509488)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a427f0e2-b74d-4ef3-bec4-0a101d09bfa3)  
(KB2466146)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=549ca7f0-44bf-4965-a9d2-aa5e8dac2238)  
(KB2519975)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=13dca35d-2209-4c5c-9150-d6db2bb3b496)  
(KB2466146)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=ef62deae-2b07-41c9-a4bf-b746566e59ee)  
(KB2519975)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="5">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-021**](http://go.microsoft.com/fwlink/?linkid=210121)
</td>
<td style="border:1px solid black;">
[**MS11-022**](http://go.microsoft.com/fwlink/?linkid=210727)
</td>
<td style="border:1px solid black;">
[**MS11-023**](http://go.microsoft.com/fwlink/?linkid=210206)
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=f756d836-6ab2-4adb-9dee-6cb523d7c1f5)  
(KB2505924)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=f756d836-6ab2-4adb-9dee-6cb523d7c1f5)  
(KB2505924)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=f756d836-6ab2-4adb-9dee-6cb523d7c1f5)  
(KB2505924)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=84dfe3f4-a2a1-47b9-8da1-29ae67230918)  
(KB2505927)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=84dfe3f4-a2a1-47b9-8da1-29ae67230918)  
(KB2505927)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=84dfe3f4-a2a1-47b9-8da1-29ae67230918)  
(KB2505927)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=ef1e612f-d8e3-4628-9fe4-ad136f0debd3)  
(KB2525412)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=ef1e612f-d8e3-4628-9fe4-ad136f0debd3)  
(KB2525412)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=0c323a12-6385-4666-ad39-a9516a8eda14)  
(KB2505935)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=0c323a12-6385-4666-ad39-a9516a8eda14)  
(KB2505935)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=0c323a12-6385-4666-ad39-a9516a8eda14)  
(KB2505935)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-029**](http://go.microsoft.com/fwlink/?linkid=208524)
</td>
<td style="border:1px solid black;">
[**MS11-021**](http://go.microsoft.com/fwlink/?linkid=210121)
</td>
<td style="border:1px solid black;">
[**MS11-022**](http://go.microsoft.com/fwlink/?linkid=210727)
</td>
<td style="border:1px solid black;">
[**MS11-023**](http://go.microsoft.com/fwlink/?linkid=210206)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2d75786a-2368-4ef2-970b-fa2e57d63ca9)  
(KB2466158)  
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
Visualizzatore di PowerPoint Microsoft 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Visualizzatore di PowerPoint Microsoft 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6e23d3c3-2944-42ea-80b3-0663af60d0f1)  
(KB2464623)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visualizzatore di Microsoft Power Point
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Visualizzatore di Microsoft Power Point](http://www.microsoft.com/downloads/details.aspx?familyid=44a703f5-b581-4900-bdbb-0f0e8d9bf0e6)  
(KB2519984)  
(Importante)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=946cc611-4d75-4728-b9d3-1c8b557b02c2)  
(KB2466156)  
(Importante)
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=913efc28-7deb-47b8-8c22-8eb5fc2631e4)  
(KB2464635)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS11-029**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS11-021**

<sup>[1]</sup>Per Microsoft Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB2464583, i clienti devono installare anche l'aggiornamento per la protezione del Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2 (KB2466156), per essere protetti dalle vulnerabilità descritte in questo bollettino.

**Nota per MS11-022**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Office Web Apps
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-022**](http://go.microsoft.com/fwlink/?linkid=210727)
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
Microsoft Office Web Apps
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint Web App](http://www.microsoft.com/downloads/details.aspx?familyid=9847dc05-7d4a-4a64-9e6a-622d3fa171f9)  
(KB2520047)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS11-022**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

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
[**MS11-025**](http://go.microsoft.com/fwlink/?linkid=209720)
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
Microsoft Visual Studio .NET 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e9501082-a651-452b-8c1a-43987ffd3102)  
(KB2465373)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2005 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ee64d83b-6c06-4ccf-b12d-99e2a7a7b18d)  
(KB2538218)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio 2008 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2008 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e6a8e024-12ee-43d5-9aae-4c721505d6df)  
(KB2538241)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2010 e Microsoft Visual Studio 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2010](http://www.microsoft.com/downloads/details.aspx?familyid=7fd643a8-8e05-4d27-8853-33f79f01cb26)  
(KB2542054)  
(Importante)  
[Microsoft Visual Studio 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1a21c9db-dfa3-4a07-a1e0-89a8069b7c17)  
(KB2565057)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual C++ 2005 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=ae2e1a40-7b45-4fe9-a20f-2ed2923aca62)  
(KB2538242)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual C++ 2008 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=a821847e-4c44-45c0-9128-61c822bb3280)  
(KB2538243)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual C++ 2010 e Microsoft Visual C++ 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual C++ 2010 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=fe558aed-9274-415f-8a0f-d9d8622fb35b)  
(KB2467173)  
(Importante)  
[Microsoft Visual C++ 2010 Redistributable Package Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7557d29b-731b-4abb-8815-2b87a4132efb)  
(KB2565063)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

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

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/it-it/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

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

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Un ricercatore anonimo che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-018
-   [MITRE](http://mitre.org/) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS11-018
-   Michal Zalewski di [Google Inc.](http://www.google.com/) per aver collaborato con noi su un problema descritto nel bollettino MS11-018
-   David Bloom di [Google Inc.](http://www.google.com/) per aver segnalato due problemi descritti nel bollettino MS11-018
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS11-018
-   Alin Rad Pop di [Secunia Research](http://secunia.com/) per aver segnalato due problemi descritti nel bollettino MS11-021
-   Muhammad Junaid Bohio di [Telus Security Labs](http://www.telussecuritylabs.com) per aver segnalato un problema descritto nel bollettino MS11-021
-   Aniway, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato tre problemi descritti nel bollettino MS11-021
-   Un ricercatore anonimo che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-021
-   Rodrigo Rubira Branco di [Check Point Vulnerability Discovery Team](http://www.checkpoint.com/) (VDT) per aver segnalato un problema descritto nel bollettino MS11-021
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS11-021
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS11-021
-   [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato tre problemi descritti nel bollettino MS11-022
-   Haifei Li di FortiGuard Labs di [Fortinet](http://www.fortiguard.com/) per aver segnalato un problema descritto nel bollettino MS11-023
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di[TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS11-023
-   Carsten Eiram di [Secunia](http://secunia.com/) per aver collaborato con noi su un problema descritto nel bollettino MS11-024
-   [Google Security Team](http://www.google.com/) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS11-026
-   Chris Ries dell'Information Security Office della Carnegie Mellon University per aver segnalato un problema descritto nel bollettino MS11-027
-   RadLSneak, che collabora con [iSIGHT Partners](http://www.isightpartners.com/) Global Vulnerability Partnership, per aver segnalato un problema descritto nel bollettino MS11-027
-   Nicolas Joly e Chaouki Bekrar di [VUPEN Threat Protection Program](http://www.vupen.com/english/) per aver segnalato un problema descritto nel bollettino MS11-029
-   Neel Mehta di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS11-030
-   [Jesse Ruderman](http://www.squarefree.com/) di [Mozilla](http://www.mozilla.org/) per aver collaborato con noi su un problema descritto nel bollettino MS11-031
-   Adam Twardoch di [Fontlab Ltd.](http://www.fontlab.com/) per aver segnalato un problema descritto nel bollettino MS11-032
-   Carsten Eiram di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS11-033
-   Tarjei Mandt di [Norman](http://www.norman.com/) per aver segnalato 30 problemi descritti nel bollettino MS11-034

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 aprile 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 aprile 2011): Per il bollettino MS11-019, è stata chiarita la descrizione della vulnerabilità nel Riepilogo.
-   V2.0 (15 aprile 2011): Per MS11-032, è stato alzato il livello di valutazione dell'Exploitability Index per CVE-2011-0034 a "1 - Alta probabilità di sfruttamento della vulnerabilità".
-   V3.0 (21 aprile 2011): È stato rivisto il bollettino per offrire l'aggiornamento per la protezione appena rilasciato per MS11-025.
-   V3.1 (27 aprile 2011): Per MS11-024, è stato modificato l'Exploitability Index aggiungendo CVE-2010-4701 per risolvere il problema della vulnerabilità grazie al presente aggiornamento. La modifica è esclusivamente informativa.
-   V4.0 (16 maggio 2011): Nuova pubblicazione del bollettino MS11-018 per offrire nuovamente l'aggiornamento per Internet Explorer 7 nelle edizioni supportate di Windows XP e Windows Server 2003. Si tratta di una modifica che riguarda esclusivamente il rilevamento. Non sono previste modifiche ai file binari. L'aggiornamento viene offerto solo ai clienti interessati. I clienti che hanno installato l'aggiornamento manualmente e quelli che eseguono configurazioni non interessate dalla modifica alla logica di rilevamento non devono eseguire ulteriori operazioni.
-   V5.0 (14 giugno 2011): Per MS11-025, è stato offerto un nuovo aggiornamento per Microsoft Visual Studio 2005 Service Pack 1, Microsoft Visual Studio 2008 Service Pack 1, Microsoft Visual Studio 2010, Microsoft Visual C + + 2005 Service Pack 1 Redistributable Package e Microsoft Visual C + + 2008 Service Pack 1 Redistributable Package. I clienti che hanno installato precedentemente quest'aggiornamento devono installare i nuovi pacchetti sui sistemi interessati.
-   V6.0 (9 agosto 2011): Per MS11-025, sono stati aggiunti Microsoft Visual Studio 2010 Service Pack 1 (KB2565057) e Microsoft Visual C++ 2010 Redistributable Package Service Pack 1 (KB2565063) come software interessati.
-   V6.1 (26 ottobre 2011): per MS11-028 è stata corretta l'applicabilità dell'installazione Server Core per .NET Framework 4 in Windows Server 2008 R2 per i sistemi x64.

*Built at 2014-04-18T01:50:00Z-07:00*
