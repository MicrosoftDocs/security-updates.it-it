---
TOCTitle: 'MS11-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2011'
ms:assetid: 'ms11-jun'
ms:contentKeyID: 61240060
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2011
================================================================

Data di pubblicazione: martedì 14 giugno 2011 | Aggiornamento: mercoledì 18 gennaio 2012

**Versione:** 3.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a giugno 2011.

Con il rilascio dei bollettini sulla sicurezza di giugno 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 giugno 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 15 giugno 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032455073&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212284">MS11-038</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nell'automazione OLE può consentire l'esecuzione di codice in modalità remota (2476490)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nell'automazione OLE (Object Linking and Embedding) di Microsoft Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visita un sito Web che contiene un'immagine di Windows Metafile (WMF) appositamente predisposta. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare tale sito Web. Un utente malintenzionato deve invece persuadere le vittime a visitare un sito Web dannoso, in genere indicendole a fare clic su un collegamento in un messaggio di posta elettronica o in una richiesta di Instant Messenger.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212287">MS11-039</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità di .NET Framework e Microsoft Silverlight potrebbe consentire l'esecuzione codice in modalità remota (2514842)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft .NET Framework e Microsoft Silverlight. La vulnerabilità può consentire l'esecuzione codice in modalità remota in un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni browser XAML (XBAP) le applicazioni Silverlight. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La vulnerabilità può consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web. Questa vulnerabilità potrebbe essere anche utilizzata dalle applicazioni Windows .NET per ignorare le restrizioni della protezione dall'accesso di codice (CAS).</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework,<br />
Microsoft Silverlight</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217470">MS11-040</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità nel client firewall di Threat Management Gateway potrebbe consentire l'esecuzione di codice in modalità remota (2520426)</strong><br />
<br />
L'aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Forefront Threat Management Gateway (TMG) 2010 Client, in precedenza chiamato Microsoft Forefront Threat Management Gateway Firewall Client. La vulnerabilità potrebbe consentire l'esecuzione codice in modalità remota se un utente malintenzionato usa un computer client per eseguire richieste specifiche in un sistema in cui è utilizzato il client firewall TMG.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Forefront Threat Management Gateway</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217499">MS11-041</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei driver in modalità kernel di Windows potrebbe consentire l'esecuzione di codice in modalità remota (2525694)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente visita una condivisione di rete (o visita un sito Web che punta a una condivisione di rete) contenente un carattere OpenType (OTF) appositamente predisposto. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare un sito Web di questo tipo o una condivisione di rete. Al contrario, un utente malintenzionato dovrebbe indurre l'utente a visitare un sito Web o una condivisione di rete, in genere inducendolo a fare clic su un collegamento in un messaggio di posta elettronica o in Instant Messenger.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215838">MS11-042</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità nel Distributed File System potrebbero consentire l'esecuzione di codice in modalità remota (2535512)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nel file system distribuito (DFS) di Microsoft. La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia una risposta DFS appositamente predisposta a ad una richiesta DFS avviata dal client. Un utente malintenzionato che sfrutti questa vulnerabilità potrebbe eseguire codice non autorizzato e acquisire il controllo completo del sistema interessato. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215841">MS11-043</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente nel client SMB può consentire l'esecuzione di codice in modalità remota (2536276)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ha inviato una risposta SMB appositamente predisposta ad una richiesta SMB avviata dal client. Per sfruttare la vulnerabilità, un utente malintenzionato deve convincere l'utente a stabilire una connessione SMB a un server SMB creato appositamente.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=216436">MS11-044</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in .NET Framework può consentire l'esecuzione di codice in modalità remota (2538814)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Microsoft .NET Framework. La vulnerabilità può consentire l'esecuzione di codice in modalità remota su un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni XAML (XBAP). Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La vulnerabilità può consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web. Questa vulnerabilità potrebbe essere anche utilizzata dalle applicazioni Windows .NET per ignorare le restrizioni della protezione dall'accesso di codice (CAS).</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2530548)</strong><br />
<br />
Questo aggiornamento per la protezione risolve undici vulnerabilità di Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=218115">MS11-052</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Vector Markup Language può consentire l'esecuzione di codice in modalità remota (2544521)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nell'implementazione Microsoft di Vector Markup Language (VML). Questo aggiornamento per la protezione è considerato di livello critico per Internet Explorer 6, Internet Explorer 7 e Internet Explorer 8 sui client Windows e di livello moderato per Internet Explorer 6, Internet Explorer 7 e Internet Explorer 8 sui server Windows. Internet Explorer 9 non è interessato da questa vulnerabilità.<br />
<br />
Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217912">MS11-037</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in MHTML può consentire l'intercettazione di informazioni personali (2544893)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente del gestore di protocolli MHTML in Microsoft Windows. La vulnerabilità potrebbe consentire la divulgazione di informazioni se un utente apre un URL appositamente predisposto da un sito Web dell'utente malintenzionato. Un utente malintenzionato dovrebbe indurre l'utente a visitare il sito Web, in genere inducendolo a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel potrebbero consentire l'esecuzione di codice in modalità remota (2537146)</strong><br />
<br />
Questo aggiornamento per la protezione risolve otto vulnerabilità di Microsoft Office segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. L'installazione e la configurazione della Convalida file di Office (OFV) per evitare l'apertura di file sospetti blocca i vettori di attacco per sfruttare le vulnerabilità descritte in CVE-2011-1272, CVE-2011-1273 e CVE-2011-1279. Microsoft Excel 2010 è solo interessato da CVE-2011-1273 descritto in questo bollettino. La soluzione di fix automatico di Microsoft di disattivazione della modifica nella visualizzazione protetta per Excel 2010, disponibile nell'articolo della Microsoft Knowledge Base 2501584, blocca i vettori di attacco per sfruttare CVE-2011-1273.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217464">MS11-046</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel driver di funzioni ausiliario potrebbe consentire l'acquisizione di privilegi più elevati (2503665)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente nel driver di funzioni ausiliario di Microsoft Windows (AFD). La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede ad un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di sfruttare tale vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217468">MS11-047</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Hyper-V può consentire un attacco di tipo Denial of Service (2525835)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft, che è stata riscontrata in Windows Server 2008 Hyper-V e in Windows Server 2008 R2 Hyper-V. La vulnerabilità può consentire un attacco di tipo Denial of Service se un pacchetto appositamente predisposto viene inviato al VMBus da un utente autenticato in una delle macchine virtuali guest ospitate dal server Hyper-V. Per sfruttare la vulnerabilità, un utente malintenzionato deve essere in possesso di credenziali di accesso valide ed essere in grado di inviare contenuto appositamente predisposto da una macchina virtuale guest. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215840">MS11-048</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel server SMB può consentire un attacco di tipo Denial of Service (2536275)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire un attacco di tipo Denial of Service se un utente malintenzionato crea un pacchetto SMB appositamente predisposto e lo invia a un sistema interessato. Le procedure consigliate e le configurazioni predefinite standard dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale attraverso questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217077">MS11-049</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nell'editor XML di Microsoft può consentire l'intercettazione di informazioni personali (2543893)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nell'editor XML di Microsoft. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre un file di individuazione del servizio Web (.disco) appositamente predisposto con uno dei software interessati elencati in questo bollettino. Si noti che questa vulnerabilità non consente di eseguire codice o acquisire direttamente diritti utente più elevati, ma può essere utilizzata per produrre informazioni utili al fine di compromettere ulteriormente il sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Microsoft SQL Server,<br />
Microsoft Visual Studio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217101">MS11-051</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella registrazione Web dei Servizi certificati di Active Directory può consentire l'acquisizione di privilegi più elevati (2518295)</strong><br />
<br />
Quest'aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nella registrazione Web ai servizi Active Directory. Questa è una vulnerabilità di cross-site scripting (XSS) che potrebbe consentire l'acquisizione di privilegi più elevati, consentendo a un utente malintenzionato di eseguire comandi non autorizzati sul sito nel contesto dell'utente designato. Un utente malintenzionato in grado di sfruttare questa vulnerabilità dovrebbe inviare un collegamento appositamente predisposto e convincere gli utenti a fare clic sul collegamento. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare il sito Web. Al contrario, l'utente malintenzionato dovrebbe invece convincere le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o in Instant Messenger che le indirizzi al sito.</td>
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
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo della vulnerabilità</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217912">MS11-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alle richieste in formato MIME in MHTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1894">CVE-2011-1894</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente<br />
<br />
Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212284">MS11-038</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'underflow dell'automazione OLE</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0658">CVE-2011-0658</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=212287">MS11-039</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'offset della matrice in .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0664">CVE-2011-0664</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217470">MS11-040</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nel client firewall TMG</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1889">CVE-2011-1889</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217499">MS11-041</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida OTF in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1873">CVE-2011-1873</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215838">MS11-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria DFS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1868">CVE-2011-1868</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215838">MS11-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risposta di riferimento DFS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1869">CVE-2011-1869</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215841">MS11-043</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi delle risposta di SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1268">CVE-2011-1268</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=216436">MS11-044</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'ottimizzazione JIT in .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1271">CVE-2011-1271</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida dei record insufficiente dei dati Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1272">CVE-2011-1272</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi errata dei record di Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1273">CVE-2011-1273</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'accesso alla matrice fuori intervallo in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1274">CVE-2011-1274</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla sovrascrittura degli heap della memoria in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1275">CVE-2011-1275</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1276">CVE-2011-1276</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1277">CVE-2011-1277</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità WriteAV in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1278">CVE-2011-1278</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217502">MS11-045</a></td>
<td style="border:1px solid black;">Vulnerabilità WriteAV fuori intervallo in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1279">CVE-2011-1279</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217464">MS11-046</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati nel driver di funzioni ausiliario</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1249">CVE-2011-1249</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente<br />
<br />
Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217468">MS11-047</a></td>
<td style="border:1px solid black;">Vulnerabilità DoS persistente in VMBus</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1872">CVE-2011-1872</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=215840">MS11-048</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi delle richieste di SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1267">CVE-2011-1267</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217077">MS11-049</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione di entità esterne in XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1280">CVE-2011-1280</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nella gestione delle proprietà dei collegamenti</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1250">CVE-2011-1250</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nella manipolazione di DOM</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1251">CVE-2011-1251</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in toStaticHTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1252">CVE-2011-1252</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nel trascinamento</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1254">CVE-2011-1254</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in elementi ora</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1255">CVE-2011-1255</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nella modifica di DOM</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1256">CVE-2011-1256</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria del layout</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1260">CVE-2011-1260</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria degli oggetti Selection</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1261">CVE-2011-1261</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217212">MS11-050</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nel reindirizzamento HTTP</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1262">CVE-2011-1262</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> – Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217101">MS11-051</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ai servizi Active Directory</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1264">CVE-2011-1264</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=218115">MS11-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria VML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1266">CVE-2011-1266</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
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
  
**Tabella 1**

 
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
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2371079f-fb20-4fd5-999e-e73f3701818c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=686e5192-63e4-410e-b653-2cfddd5b409f)  
(KB2478656)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3db8a718-4441-4e1a-889f-abcc4bde1125)  
(KB2478658)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=67a25abd-f43c-4b01-b507-a109b739238f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=492310d3-bbb4-4fff-b5fe-3470c17e7681)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7e115a1-486b-4a2b-a7d6-42c4018fc02d)  
(KB2530095)  
(Critico)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=26ec66af-9727-4423-90da-012ed5b30856)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4203a59a-a809-45db-a234-fef0ff5063f9)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4a49ec89-2a8f-41d9-8f0b-ee57fdf21f50)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b53d6631-4ded-48f5-a503-925b89b322b2)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=686e5192-63e4-410e-b653-2cfddd5b409f)  
(KB2478656)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3db8a718-4441-4e1a-889f-abcc4bde1125)  
(KB2478658)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=035d5115-54b6-41d3-b9f0-890041ead178)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=af6b7627-c462-45fe-8948-70da37e60659)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e10a4c3c-2ef8-4cfc-ac9b-4d97bfa79ac1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7e115a1-486b-4a2b-a7d6-42c4018fc02d)  
(KB2530095)  
(Critico)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=f6e05fef-ee8c-44ff-a106-d7b8659c8d91)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9fc734db-a177-43d2-a74a-b1fe6ea6f779)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4e4e18a4-97dc-4c5e-a078-8466913aa29e)  
(Critico)
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
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7e6ff410-4552-4687-81ab-83d9c91f8af5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=686e5192-63e4-410e-b653-2cfddd5b409f)  
(KB2478656)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3db8a718-4441-4e1a-889f-abcc4bde1125)  
(KB2478658)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3aa8f1bc-07de-451a-8244-1733247e6f2e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2719e0fb-3cfd-47b2-906d-3e07b0e3c978)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7e115a1-486b-4a2b-a7d6-42c4018fc02d)  
(KB2530095)  
(Critico)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=638f6dd6-bea0-4356-b23a-45e865a6b28b)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a3bd0012-4a45-4f96-8a51-3ff1f85d1e37)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=19557984-5088-44cc-b5ba-9bab33df8e7e)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9c1a539f-1472-4394-8354-bd549d8332e0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=686e5192-63e4-410e-b653-2cfddd5b409f)  
(KB2478656)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3db8a718-4441-4e1a-889f-abcc4bde1125)  
(KB2478658)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4aa8c003-0353-4a5b-8aea-c01a103af393)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e9018258-5a72-47a1-8584-3d1aa52317c3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c962531e-f580-4195-989b-cf348cc96fa7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7e115a1-486b-4a2b-a7d6-42c4018fc02d)  
(KB2530095)  
(Critico)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=ce616970-343d-49f1-994d-4269b9a11448)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=70ece3b4-e5bb-469c-bfef-c8310681f5a7)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c92d94c5-5e8f-45aa-a24a-f4d0efd93732)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c194dd35-b9db-44a5-a252-38f9f803802f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=686e5192-63e4-410e-b653-2cfddd5b409f)  
(KB2478656)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3db8a718-4441-4e1a-889f-abcc4bde1125)  
(KB2478658)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=2e07b5fa-c9fa-495b-9352-c07ce46a7e8b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=96309c49-4822-4c47-b364-2ba65327cac5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ea18a916-03cf-4eac-bacc-ceb006491f24)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Nessun livello di gravità<sup>[2]</sup>)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7e115a1-486b-4a2b-a7d6-42c4018fc02d)  
(KB2530095)  
(Critico)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=960f8920-906b-48a8-8700-94f09babc628)  
(KB2518864)  
(Critico)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=f58ebc9e-00e1-413c-8076-d7a44003d0c7)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=80231a27-b37c-4101-a34f-19a26a040836)  
(Critico)
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
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f33c9e54-c2e5-498d-a798-5bbfe9e4249c)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=2eabacce-394f-4b9a-8306-0875ca19a3a9)  
(KB2478657)  
(Critico)  
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd3254-7e59-4cf9-afa8-45ae66bc7390)  
(KB2478659)  
(Critico)  
Solo Windows Vista Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afa11dda-a543-42a7-b997-5292fd869a8b)  
(KB2478660)  
(Critico)  
Windows Vista Service Pack 1 e Windows Vista Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aded8f20-479d-40c1-9560-c0581c6f77a2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a62edfd8-9016-4bb5-bf48-885498fa0042)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Critico)  
Solo Windows Vista Service Pack 1: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Critico)  
Solo Windows Vista Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista Service Pack 2: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Critico)  
Windows Vista Service Pack 1 e Windows Vista Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=fea735a8-032b-4fa6-8337-1fa411df0b88)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4cddfc68-eff6-4587-8607-63307d039489)  
(Critico)  
Solo Windows Vista Service Pack 2: [Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=392316fc-f531-469c-aa60-4ecf061a5354)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4566528f-62ee-4d78-b3af-131a7cc15e1f)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=2eabacce-394f-4b9a-8306-0875ca19a3a9)  
(KB2478657)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd3254-7e59-4cf9-afa8-45ae66bc7390)  
(KB2478659)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afa11dda-a543-42a7-b997-5292fd869a8b)  
(KB2478660)  
(Critico)  
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a519a5d7-bfe3-4e53-99e9-d85f7e34237f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=962cb40c-680c-4c37-98d4-ca9789ca7270)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cb561ba6-af4d-40cc-947c-923f9cca9a7e)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 1: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Nessun livello di gravità<sup>[2]</sup>)  
Solo Windows Vista x64 Edition Service Pack 2: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Critico)  
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=49dcb47b-3c79-4f69-ba07-f471304c16e2)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e0a8fbac-2c31-4cf8-9967-6171edabd560)  
(Critico)  
Solo Windows Vista x64 Edition Service Pack 2: [Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=44b2aa73-c318-47ac-ad87-0d24afd9cdd7)  
(Critico)
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
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0c9614d9-6f61-463d-b1fa-bd5eb2c1a5c5)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=2eabacce-394f-4b9a-8306-0875ca19a3a9)\*\*  
(KB2478657)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd3254-7e59-4cf9-afa8-45ae66bc7390)\*\*  
(KB2478659)  
(Critico)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afa11dda-a543-42a7-b997-5292fd869a8b)\*\*  
(KB2478660)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)\*\*<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8ebfa067-0236-4454-8605-df1b99742f90)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8ab9679e-6a69-4ca3-9210-7ca4fb1980c2)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)\*\*  
(KB2518863)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)\*\*  
(KB2518865)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)\*\*  
(KB2518863)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit soltanto: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)\*\*  
(KB2518865)  
(Critico)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)\*\*  
(KB2518866)  
(Critico)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)\*\*  
(KB2518866)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)\*\*<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b6547ff0-b059-495d-8816-bb094ac11be7)\*\*  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c9650c47-ac52-433d-b409-ce1cfe8d3e87)\*\*  
(Critico)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2: [Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=7f9b1ba2-8247-494b-990c-f62003188c5a)\*\*  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=36698775-0e4e-4980-ae4c-43542de424ca)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=2eabacce-394f-4b9a-8306-0875ca19a3a9)\*\*  
(KB2478657)  
(Critico)  
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd3254-7e59-4cf9-afa8-45ae66bc7390)\*\*  
(KB2478659)  
(Critico)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afa11dda-a543-42a7-b997-5292fd869a8b)\*\*  
(KB2478660)  
(Critico)  
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)\*\*<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cd8f3713-b408-4db6-aecd-7eed2176a715)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f1d76b82-9996-4d08-894b-9c16a4b3bb1e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=22c63fc3-2c5a-4e50-9026-2e04a6e74210)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)\*\*  
(KB2518863)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)\*\*  
(KB2518865)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)\*\*  
(KB2518863)  
(Critico)  
Windows Server 2008 solo per sistemi x64: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)\*\*  
(KB2518865)  
(Critico)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)\*\*  
(KB2518866)  
(Critico)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)\*\*  
(KB2518866)  
(Critico)  
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)\*\*<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=feff3364-4bfd-45f5-99da-9192b47ef5d4)\*\*  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7dff9f08-19cb-41dd-a315-84c1dac81510)\*\*  
(Critico)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2: [Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=fdf88a52-c099-44eb-95a0-650129c0e678)\*\*  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3edb613f-5bf0-4e28-9835-4afbb6ef0e01)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=2eabacce-394f-4b9a-8306-0875ca19a3a9)  
(KB2478657)  
(Critico)  
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd3254-7e59-4cf9-afa8-45ae66bc7390)  
(KB2478659)  
(Critico)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afa11dda-a543-42a7-b997-5292fd869a8b)  
(KB2478660)  
(Critico)  
Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5a61f888-c81e-4b8a-8932-2fe67df4b2ad)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f80c89c6-27ab-4f6a-afad-9c8e92cbbce4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5bb889de-8ff6-4587-8ef9-ffb13e8d60fd)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Nessun livello di gravità<sup>[2]</sup>)  
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f7092fe-079d-4175-b8b7-412f259ff7e4)  
(KB2518863)  
(Critico)  
Windows Server 2008 per sistemi Itanium soltanto: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80423e37-0a54-413d-b44a-41c68c2030b8)  
(KB2518865)  
(Critico)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2: [Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Critico)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2: [Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1e3ca981-5565-41a8-ab5e-941c92e74c7d)  
(KB2518866)  
(Critico)  
Windows Server 2008 per sistemi basati su Itanium e Windows Server 2008 per sistemi basati su Itanium Service Pack 2: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=d81a9219-da95-4fbf-af7f-898f553b0572)  
(Critico)
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
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=50ae36ff-2406-48a4-97cc-12782b6d30ac)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi a 32 bit: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=9720a317-ca4c-4a47-b99c-2c66301e62c6)  
(KB2478661)  
(Critico)  
Solo Windows 7 per sistemi a 32 bit Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=c8152a18-0367-4c00-a3c7-669325a899f4)  
(KB2478662)  
(Critico)  
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=9de1bf5d-6f25-496d-bc44-a32c5e8920fe)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=19a15098-1754-4536-a9ca-ff07d16464b7)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi a 32 bit: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bff13134-ed84-4370-beb4-340c340a5d98)  
(KB2518867)  
(Critico)  
Solo Windows 7 per sistemi a 32 bit Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=dab623bf-d23d-42a9-9e74-ae75d779b980)  
(KB2518869)  
(Critico)  
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=91b98f02-a09e-48f1-9f78-a949f7268542)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=79f846da-3b17-43c9-9016-a055c2c56975)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1241f0f8-a5c7-420a-a5b7-b6c3caa9e5e2)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi x64: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=9720a317-ca4c-4a47-b99c-2c66301e62c6)  
(KB2478661)  
(Critico)  
Solo Windows 7 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=c8152a18-0367-4c00-a3c7-669325a899f4)  
(KB2478662)  
(Critico)  
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e7f52b13-5b3d-438c-ae14-86da50c8b67a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=50d1c677-57aa-4e3f-bdfc-6f01b5d3bfe2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b449f23e-b3df-46e5-bfe3-98268d20ad54)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi x64: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bff13134-ed84-4370-beb4-340c340a5d98)  
(KB2518867)  
(Critico)  
Solo Windows 7 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=dab623bf-d23d-42a9-9e74-ae75d779b980)  
(KB2518869)  
(Critico)  
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=264107cc-68b4-401c-82f7-de64b535c18d)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=e87a09f2-b755-48ef-9b85-fc78d0bfce43)  
(Critico)
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
[**MS11-038**](http://go.microsoft.com/fwlink/?linkid=212284)
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-041**](http://go.microsoft.com/fwlink/?linkid=217499)
</td>
<td style="border:1px solid black;">
[**MS11-042**](http://go.microsoft.com/fwlink/?linkid=215838)
</td>
<td style="border:1px solid black;">
[**MS11-043**](http://go.microsoft.com/fwlink/?linkid=215841)
</td>
<td style="border:1px solid black;">
[**MS11-044**](http://go.microsoft.com/fwlink/?linkid=216436)
</td>
<td style="border:1px solid black;">
[**MS11-050**](http://go.microsoft.com/fwlink/?linkid=217212)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8181c359-cd79-438a-87be-093b363d0b04)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=9720a317-ca4c-4a47-b99c-2c66301e62c6)\*  
(KB2478661)  
(Critico)  
Windows Server 2008 R2 solo per sistemi x64: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=c8152a18-0367-4c00-a3c7-669325a899f4)\*  
(KB2478662)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)\*<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b77e5be6-d3eb-4e3a-9be2-831578f0447c)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=9d66b1e7-dbf9-4475-a973-49fb85557eca)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=06008192-3cac-477b-a913-83eed39d8718)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bff13134-ed84-4370-beb4-340c340a5d98)\*  
(KB2518867)  
(Critico)  
Windows Server 2008 R2 solo per sistemi x64: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=dab623bf-d23d-42a9-9e74-ae75d779b980)\*  
(KB2518869)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)\*<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=8b18e6f9-96b8-4dec-bcd0-d71f1bac3eb0)\*\*  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=81814b15-ebdf-4817-932b-5ea7a37fa6ed)\*\*  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6b63a1eb-445a-4cd3-b357-9a1dd82d7a35)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Server 2008 R2 per sistemi Itanium: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=9720a317-ca4c-4a47-b99c-2c66301e62c6)  
(KB2478661)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi Itanium Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=c8152a18-0367-4c00-a3c7-669325a899f4)  
(KB2478662)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=c72635e4-c733-4fa1-9db0-75de6ead9e1c)<sup>[1]</sup>
(KB2478663)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c00a33bc-c874-4693-b0f7-5034c5df9424)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3c8455f1-b8a0-4ba2-84a2-043d25ef75c5)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=93a32bd9-7e67-4ace-8c45-116f91b032f9)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Server 2008 R2 per sistemi Itanium: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bff13134-ed84-4370-beb4-340c340a5d98)  
(KB2518867)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi Itanium Service Pack 1: [Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=dab623bf-d23d-42a9-9e74-ae75d779b980)  
(KB2518869)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1: [Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=f7afba05-974f-48f8-b600-9e131ceb7951)<sup>[1]</sup>
(KB2518870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ab2406a8-06f7-4f88-9af4-dc136d64bc35)  
(Critico)
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Note per MS11-039**

<sup>[1]</sup>**.NET Framework 4.0 e .NET Framework 4.0 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4.0 e .NET Framework 4.0 Client Profile. .NET Framework 4.0 Client Profile è un sottoinsieme di .NET Framework 4.0. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4.0 sia .NET Framework 4.0 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Note per MS11-044**

<sup>[1]</sup>**.NET Framework 4.0 e .NET Framework 4.0 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4.0 e .NET Framework 4.0 Client Profile. .NET Framework 4.0 Client Profile è un sottoinsieme di .NET Framework 4.0. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4.0 sia .NET Framework 4.0 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

<sup>[2]</sup>Livelli di gravità non sono applicabili a quest'aggiornamento perché la vulnerabilità trattata in questo bollettino non interessa questo software. Tuttavia, agli utenti di questo software Microsoft viene consigliato di applicare l'aggiornamento per la protezione come misura preventiva per difendersi da eventuali nuovi vettori identificabili in futuro.

**Tabella 2**

 
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
</tr>
<tr>
<th colspan="7">
Windows XP
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
<td style="border:1px solid black;">
Nessuno
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=6c760c7f-94f1-437f-a645-fd33b50d03f4)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0b88f9e9-3439-44e5-92c8-66a3c97cb03d)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=03b45ad8-cc6b-473b-8112-bd513ed97f5d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ce5bc2d7-9438-4bf0-be5e-be9dd00c3286)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a1db7736-f3e4-45df-af1d-52746978a0a8)  
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=c94c0d17-fdbe-41b3-a23d-98f43f907b89)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ff955dc3-58ca-40ea-b7f1-9ff40c37f997)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ed502ece-737e-44cb-84fd-8a0d1bc321c8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7b211b02-a005-46a3-ad1d-d4baaeec8289)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=71497891-41a2-476d-b524-4eb5cecb9639)  
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
</tr>
<tr>
<th colspan="7">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=5dafb455-969e-4be9-8735-d4ee0682d22f)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ba3beb80-a921-489e-a6ff-a7b2d665ada6)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=a8038325-0d14-445b-a5d9-ce7ac1fa44b5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6427ea5d-05d0-4367-805c-9cb305802b3c)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c614cb8b-223e-4f84-b94c-f15747760aa5)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ef90d6c1-ea7f-4c32-9c90-0303e04c7436)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=e78829d0-8215-4e56-8959-ebd3bc8e9a91)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=3bec943e-5758-4439-a947-a8fafd30edec)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5f7bcbad-f647-4fbb-88d4-b19c54db6f00)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7f65891-32c0-4817-b3b2-d8be73145df9)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9a951087-25c5-4f5c-8407-a1585491ae0b)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=62944095-33d6-4131-be32-a79d9ec4d4a9)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=1e822515-9f0a-4ef0-bb70-d4889d200f47)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=47a0fdc6-7576-4c32-b8fd-cbb05d57599d)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ca8b1d09-9f80-417b-99b1-8f86e86e1f11)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=dd48b93b-24fa-45a3-91fb-9f9f9418c49f)  
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
</tr>
<tr>
<th colspan="7">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
<td style="border:1px solid black;">
Nessuno
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
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e541f1bb-c9bf-4dc8-96ec-58a3de5ba7fd)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=cd059690-52b0-4b37-9fbb-d9906ae46fed)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ebea38a7-1fbe-4141-a529-52d7a7326d6a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b69e3bda-940b-4524-a724-0af4ae0ec719)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5f0007c3-8d11-4940-8766-1112e3777aae)  
(Importante)
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
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6c7d7162-ef19-49f4-a8fc-5db7415445a4)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=256bb26f-df9e-4259-881b-e8313a9fafa8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=54833350-a385-4a31-995a-9ddc38798c21)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e3a26bc5-1757-4b38-9cae-419c919f4877)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fadf6f12-1f09-4d49-93b1-8fce01400b4f)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4446121a-0aab-4fbc-ba74-68d7650e8bca)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ed089de4-c9ec-4ac7-a711-5f7cb29c05bc)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6a3bbd67-94db-40b2-8786-cb39a493ec92)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e34e4cf9-cdae-4240-8574-950c0be00822)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8960dd62-7cf7-41cb-97b2-b082bd1750aa)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=46ade106-e0cb-4c71-8230-793a15062823)\*\*  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=01399fc7-dc2b-461e-a1a5-751a3b61bde0)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=dd32b7c6-daa1-47aa-807f-25a678790cf2)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4cb870f3-9878-4075-b8fd-2ee90c8e3bc8)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a3604f05-26b2-451b-9153-0e718158371e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=24789423-72b7-48d1-bdc1-f0e5174d99bb)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0abc6908-ac6a-4da3-843a-af6841ccc1db)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6141a1c5-ecaf-4553-9d27-dd6e5c4a13fd)\*\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=16a8b78a-3979-4cc7-bbe5-6d962aa64336)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e1243011-00e6-49f2-a676-c04cb805d36a)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e8a82b44-e1d8-45f8-b8b8-b1f74e1efce0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=057f1356-9c70-4457-a1df-69334fdab467)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
<td style="border:1px solid black;">
Nessuno
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
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=27e767d8-84e3-434f-bb8d-3b2303774ad0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c3647646-658a-423b-b0cb-bba7613b67e7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=63d8b801-5178-474b-a21e-72a0ce501d3e)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cf9e5ecd-68f7-4982-b4ed-be80859b757c)  
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
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=747ba56a-0d47-4946-99a4-bae1f11ea748)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7996511d-4b8e-49c3-a0fa-4da907a6c947)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cd7d3cb9-cb60-4b62-b0df-a38fe21802e9)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2707650a-604c-4044-acc4-07a30b5640d8)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-052**](http://go.microsoft.com/fwlink/?linkid=218115)
</td>
<td style="border:1px solid black;">
[**MS11-037**](http://go.microsoft.com/fwlink/?linkid=217912)
</td>
<td style="border:1px solid black;">
[**MS11-046**](http://go.microsoft.com/fwlink/?linkid=217464)
</td>
<td style="border:1px solid black;">
[**MS11-047**](http://go.microsoft.com/fwlink/?linkid=217468)
</td>
<td style="border:1px solid black;">
[**MS11-048**](http://go.microsoft.com/fwlink/?linkid=215840)
</td>
<td style="border:1px solid black;">
[**MS11-051**](http://go.microsoft.com/fwlink/?linkid=217101)
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
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=cff7f53d-0fd6-48f8-a9d6-bf19e0a32905)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=40354f73-4f4d-4a4a-abac-f8a3d4c3ae5f)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e67c73ca-d0f9-40c1-8b6e-25b1b13caa3a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c9c6c36d-a455-42f7-b7d4-9fb9824c07cb)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f9824310-772d-4e1e-980e-11e2db3ac53e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1da04414-6210-43ea-8e0a-cf21cf144076)\*\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4dd2c0f4-b29c-4648-a123-83d3ae6a878f)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=22853823-8f63-4258-8991-1ad50e58a0d9)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72d1d6b6-e8bd-492b-b65a-82060beef441)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0533d293-e186-4d39-a925-ab3d9ed46290)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="3">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-045**](http://go.microsoft.com/fwlink/?linkid=217502)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=853c0663-94f7-4634-98ad-47ca4b1f7b1e)  
(KB2541003)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f38f183a-9c64-406b-9bf6-807cb2d55e56)  
(KB2541025)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5b271f87-a279-419f-9437-ded224fa19f1)<sup>[1]</sup>
(KB2541007)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=baba7ec1-4a5e-4e13-9d0e-9085a39a0554)  
(KB2523021)  
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
[Microsoft Excel 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=d6e9f422-43b0-4da5-8356-c38482e8eebb)  
(KB2523021)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-045**](http://go.microsoft.com/fwlink/?linkid=217502)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=d12d0868-4f28-4c0a-ab61-338878064b70)  
(KB2555786)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=9e2d348b-c753-4eab-838c-370cd5af5e14)  
(KB2555785)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=3c58555c-1eba-42fe-a10f-b30af9031e44)  
(KB2555784)  
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
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=6118d5f5-b6fd-4584-be25-209534772379)  
(KB2555787)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft InfoPath
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-045**](http://go.microsoft.com/fwlink/?linkid=217502)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft InfoPath 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=88eedb0b-a2cf-4a1b-b1b9-0b2926c25872)  
(KB2510061)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft InfoPath 2010 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=90ffe910-bd9c-48aa-8007-2b43e1a99999)  
(KB2510065)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft InfoPath 2010 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f3244003-fb63-44d8-bedc-6399c39aacba)  
(KB2510065)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-045**](http://go.microsoft.com/fwlink/?linkid=217502)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
Microsoft Excel Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=77c1e7e2-207f-46fd-81f2-43a25eddc010)  
(KB2541015)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3512a033-871d-49ec-a8d2-1b9c7dec4936)  
(KB2541012)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS11-045**

<sup>[1]</sup>Per Microsoft Office Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB2541007, i clienti devono installare anche l'aggiornamento per la protezione del Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2 (KB2541012) per essere protetti dalle vulnerabilità descritte in questo bollettino.

**Nota per MS11-049**

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
Microsoft SQL Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
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
SQL Server 2005 Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=faca7f7a-c346-48e3-9bf5-f140a51aae4e)  
(KB2494113)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d214763c-5a16-4959-90ff-08112345d867)  
(KB2494112)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 x64 Edition Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 x64 Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=faca7f7a-c346-48e3-9bf5-f140a51aae4e)  
(KB2494113)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 x64 Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d214763c-5a16-4959-90ff-08112345d867)  
(KB2494112)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 per sistemi Itanium Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=faca7f7a-c346-48e3-9bf5-f140a51aae4e)  
(KB2494113)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d214763c-5a16-4959-90ff-08112345d867)  
(KB2494112)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2aba4a2e-477f-4267-9ebe-ab7b29d218ad)  
(KB2494120)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2975ad1a-1852-4771-b3fa-2be79899be57)  
(KB2494123)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 x64 Edition Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 x64 Edition Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2aba4a2e-477f-4267-9ebe-ab7b29d218ad)  
(KB2494120)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 x64 Edition Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2975ad1a-1852-4771-b3fa-2be79899be57)  
(KB2494123)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 per sistemi Itanium Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 per sistemi Itanium Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2aba4a2e-477f-4267-9ebe-ab7b29d218ad)  
(KB2494120)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 per sistemi Itanium Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2975ad1a-1852-4771-b3fa-2be79899be57)  
(KB2494123)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 Express Edition Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Express Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=faca7f7a-c346-48e3-9bf5-f140a51aae4e)  
(KB2494113)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Express Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d214763c-5a16-4959-90ff-08112345d867)  
(KB2494112)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 Express Edition Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Express Edition Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2aba4a2e-477f-4267-9ebe-ab7b29d218ad)  
(KB2494120)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Express Edition Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2975ad1a-1852-4771-b3fa-2be79899be57)  
(KB2494123)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 Express Edition with Advanced Services Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Express Edition with Advanced Services Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=faca7f7a-c346-48e3-9bf5-f140a51aae4e)  
(KB2494113)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Express Edition with Advanced Services Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d214763c-5a16-4959-90ff-08112345d867)  
(KB2494112)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 Express Edition with Advanced Services Service Pack 4
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Express Edition with Advanced Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2aba4a2e-477f-4267-9ebe-ab7b29d218ad)  
(KB2494120)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2005 Express Edition with Advanced Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=2975ad1a-1852-4771-b3fa-2be79899be57)  
(KB2494123)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server Management Studio Express (SSMSE) 2005
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server Management Studio Express (SSMSE) 2005](http://www.microsoft.com/downloads/details.aspx?familyid=34c3ba21-b158-4e6d-82ba-831053d41161)  
(KB2546869)  
(Importante)  
Aggiornamento QFE:  
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server Management Studio Express (SSMSE) 2005 x 64 Edition
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server Management Studio Express (SSMSE) 2005 x 64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=34c3ba21-b158-4e6d-82ba-831053d41161)  
(KB2546869)  
(Importante)  
Aggiornamento QFE:  
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2008 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae7db514-d96b-4cff-a13d-c74f4cf8cf0c)<sup>[1]</sup>
(KB2494096)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=312a39c4-cb32-4216-8672-1b1c0937ba6c)<sup>[1]</sup>
(KB2494100)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2008 per sistemi x64 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae7db514-d96b-4cff-a13d-c74f4cf8cf0c)<sup>[1]</sup>
(KB2494096)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=312a39c4-cb32-4216-8672-1b1c0937ba6c)<sup>[1]</sup>
(KB2494100)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2008 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae7db514-d96b-4cff-a13d-c74f4cf8cf0c)  
(KB2494096)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=312a39c4-cb32-4216-8672-1b1c0937ba6c)  
(KB2494100)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6f4767bf-257d-4822-b768-7b6702261276)<sup>[1]</sup>
(KB2494089)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=23240963-e2c6-4d40-8179-661117b53e91)<sup>[1]</sup>
(KB2494094)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2008 per sistemi x64 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6f4767bf-257d-4822-b768-7b6702261276)<sup>[1]</sup>
(KB2494089)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=23240963-e2c6-4d40-8179-661117b53e91)<sup>[1]</sup>
(KB2494094)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6f4767bf-257d-4822-b768-7b6702261276)  
(KB2494089)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=23240963-e2c6-4d40-8179-661117b53e91)  
(KB2494094)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2008 R2 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 R2 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=80e98567-1b28-49b1-a646-579f8c115a41)<sup>[1]</sup>
(KB2494088)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 R2 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=9df95137-d1b3-4fac-8958-8042aa2010c4)<sup>[1]</sup>
(KB2494086)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=80e98567-1b28-49b1-a646-579f8c115a41)<sup>[1]</sup>
(KB2494088)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=9df95137-d1b3-4fac-8958-8042aa2010c4)<sup>[1]</sup>
(KB2494086)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=80e98567-1b28-49b1-a646-579f8c115a41)  
(KB2494088)  
(Importante)  
Aggiornamento QFE:  
[SQL Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=9df95137-d1b3-4fac-8958-8042aa2010c4)  
(KB2494086)  
(Importante)
</td>
</tr>
</table>
 
**Noteper MS11-049**

<sup>[1]</sup>Questo aggiornamento si applica anche alle edizioni corrispondenti Express e Express with Advanced Services Editions.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="3">
Microsoft Silverlight
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 4
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=2f71b104-b66f-4146-9d70-fcde766c91b8) installato in Mac  
(KB2512827)  
(Critico)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=2f71b104-b66f-4146-9d70-fcde766c91b8) installato su tutte le versioni dei client Microsoft Windows  
(KB2512827)  
(Critico)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=2f71b104-b66f-4146-9d70-fcde766c91b8) installato su tutte le versioni di Microsoft Windows Server\*\*  
(KB2512827)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Visual Studio
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-039**](http://go.microsoft.com/fwlink/?linkid=212287)
</td>
<td style="border:1px solid black;">
[**MS11-049**](http://go.microsoft.com/fwlink/?linkid=217077)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2005 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e5ce8a9a-e89b-4095-9f21-7e6f307fbf2b)  
(KB2251481)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio 2008 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2008 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cc01bce9-3f38-4590-9c6e-a4048c886d33)  
(KB2251487)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2010
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2010](http://www.microsoft.com/downloads/details.aspx?familyid=213b820f-dcba-4895-b339-b50eeb92524d)  
(KB2251489)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS11-039**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS11-049**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software di protezione Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Forefront
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-040**](http://go.microsoft.com/fwlink/?linkid=217470)
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
Microsoft Forefront Threat Management Gateway 2010 Client
</td>
<td style="border:1px solid black;">
[Microsoft Forefront Threat Management Gateway 2010 Client](http://www.microsoft.com/downloads/details.aspx?familyid=d1c85acd-a6df-4634-9cd4-c562ad92097e)  
(Critico)
</td>
</tr>
</table>
 

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

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Billy Rios e Eduardo Vela Nava di [Google Security Team](http://www.google.com/) per aver collaborato con noi alle modifiche contenute nel bollettino MS11-037
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS11-038
-   Michael J. Liu per aver segnalato un problema descritto nel bollettino MS11-039
-   Koro di [www.korosoft.net](http://www.korosoft.net/) per aver segnalato un problema descritto nel bollettino MS11-041
-   Laurent Gaffié di [NGS Software](http://www.ngssoftware.com/) per aver segnalato un problema descritto in MS11-042
-   Dan Kaminsky per aver collaborato con noi allo studio di un problema descritto in MS11-044
-   Bing Liu di [FortiGuard Labs di Fortinet](http://www.fortiguard.com/) per aver segnalato un problema descritto nel bollettino MS11-045
-   Un ricercatore anonimo che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-045
-   Omair, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS11-045
-   Un ricercatore anonimo che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-045
-   Nicolas Gregoire di [Agarri](http://www.agarri.fr/), che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS11-045
-   Omair per aver segnalato un problema descritto nel bollettino MS11-045
-   Will Dormann del [CERT/CC](http://www.cert.org/) per aver segnalato due problemi descritti in MS11-045
-   Steven Adair di [Shadowserver Foundation](http://www.shadowserver.org) e Chris S. per aver segnalato un problema descritto in MS11-046
-   Nicolas Economou di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS11-047
-   Jesse Ou di [Cigital](http://www.cigital.com) per aver segnalato un problema descritto nel bollettino MS11-049
-   Robert Swiecki di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS11-050
-   [NSFOCUS Security Team](http://www.nsfocus.com/) per aver segnalato un problema descritto nel bollettino MS11-050
-   Un ricercatore anonimo, che collabora con il programma [Beyond Security's SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html), per aver segnalato un problema descritto in MS11-050
-   Adi Cohen di [IBM Rational Application Security](http://blog.watchfire.com/) per aver segnalato un problema descritto in MS11-050
-   [Trend Micro](http://www.trendmicro.com) per aver collaborato con noi allo studio di un problema descritto in MS11-050
-   Nirmal Singh Bhary di [Norman](http://www.norman.com) per aver segnalato un problema descritto in MS11-050
-   Un ricercatore anonimo che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-050
-   Damian Put, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS11-050
-   Yoel Gluck, Yogesh Badwe e Varun Badhwar del team Product Security di [salesforce.com](http://www.salesforce.com/) per aver segnalato un problema descritto in MS11-050
-   Jose Antonio Vazquez Gonzalez, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS11-050
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS11-050
-   Peter Winter-Smith, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS11-050
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver collaborato con noi alle modifiche al sistema di difesa illustrate in MS11-050
-   Ruggero Strabla di [eMaze](http://www.emaze.net/) Networks; [Saipem Security Team](http://www.saipem.com/) per aver segnalato un problema descritto nel bollettino MS11-051.
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS11-052

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it) o contattare 1-866-PCSAFETY. Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto &amp; Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 giugno 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (14 giugno 2011): Per MS11-042, Windows 7 per sistemi a 32 bit Service Pack 1, Windows 7 per sistemi x64 Service Pack 1, Windows Server 2008 R2 per sistemi x64 Service Pack 1 e Windows Server 2008 R2 per sistemi Itanium Service Pack 1 sono stati rimossi dalla sottosezione **Software interessato e percorsi per il download**. La modifica è esclusivamente informativa. Non sono previste modifiche ai file di aggiornamento per la protezione o per la logica di rilevamento.
-   V2.0 (9 agosto 2011): È stato rilasciato di nuovo MS11-043 per offrire nuovamente l'aggiornamento su tutti i sistemi operativi supportati per risolvere un problema di stabilità. I clienti che hanno già aggiornato il sistema devono reinstallare MS11-043. È stato rilasciato di nuovo anche MS11-049 per comunicare una modifica di rilevamento all'aggiornamento per Microsoft Visual Studio 2005 Service Pack 1 e aggiungere il rilevamento per il software correlato. Non sono presenti modifiche ai file di aggiornamento per la protezione in MS11-049. I clienti che hanno già aggiornato il sistema non devono reinstallare MS11-049.
-   V2.1 (26 ottobre 2011): per MS11-039 e MS11-044 è stata corretta l'applicabilità dell'installazione Server Core per .NET Framework 4 in Windows Server 2008 R2 per i sistemi x64.
-   V3.0 (8 novembre 2011): Microsoft ha rilasciato di nuovo il bollettino MS11-037 per offrire nuovamente l'aggiornamento per tutte le edizioni supportate di Windows XP e Windows Server 2003. I clienti che utilizzano Windows XP o Windows Server 2003, compresi quelli che hanno già installato l'aggiornamento reso disponibile il 14 giugno 2011, dovrebbero installare il nuovo aggiornamento offerto.
-   V3.1 (18 gennaio 2012): Per MS11-049, è stata aggiunta una nota alla sezione Software interessato e percorsi per il download per chiarire che questo aggiornamento si applica anche a SQL Server 2008 a 32 bit e x64, nonché a SQL Server 2008 R2 Express e Express Advanced Editions.

*Built at 2014-04-18T01:50:00Z-07:00*
