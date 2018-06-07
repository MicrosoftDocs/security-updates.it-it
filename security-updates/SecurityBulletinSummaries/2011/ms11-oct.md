---
TOCTitle: 'MS11-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2011'
ms:assetid: 'ms11-oct'
ms:contentKeyID: 61240064
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2011
=================================================================

Data di pubblicazione: martedì 11 ottobre 2011 | Aggiornamento: mercoledì 26 ottobre 2011

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati nel mese di ottobre 2011.

Con il rilascio dei bollettini sulla sicurezza di ottobre 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 6 ottobre 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 12 ottobre 2011 alle 11:00, ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032487956). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227075">MS11-078</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità di .NET Framework e Microsoft Silverlight potrebbe consentire l'esecuzione codice in modalità remota (2604930)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft .NET Framework e Microsoft Silverlight. La vulnerabilità può consentire l'esecuzione codice in modalità remota in un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni browser XAML (XBAP) le applicazioni Silverlight. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La vulnerabilità può consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web. Questa vulnerabilità potrebbe essere anche utilizzata dalle applicazioni Windows .NET per ignorare le restrizioni della protezione dall'accesso di codice (CAS).</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft .NET Framework, Microsoft Silverlight</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2586448)</strong><br />
<br />
Questo aggiornamento per la protezione risolve otto vulnerabilità di Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=221538">MS11- 075</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Active Accessibility può consentire l'esecuzione di codice in modalità remota (2623699)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel componente Microsoft Active Accessibility. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato convince un utente ad aprire un file legittimo situato nella stessa directory di rete di un file della libreria con collegamento dinamico (DLL) appositamente predisposto. Quindi, durante l'apertura del file legittimo, il componente Microsoft Active Accessibility può tentare di caricare il file DLL ed eseguire il codice contenuto al suo interno. L'attacco è possibile solo se l'utente visita un file system remoto o una condivisione WebDAV di dubbia provenienza e apre un documento da questa posizione che è poi caricato da un'applicazione vulnerabile.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227073">MS11-076</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Windows Media Center può consentire l'esecuzione di codice in modalità remota (2604926)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Windows Media Center. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato convince un utente ad aprire un file legittimo situato nella stessa directory di rete di un file della libreria con collegamento dinamico (DLL) appositamente predisposto. Quindi, durante l'apertura del file legittimo, Windows Media Center può tentare di caricare il file DLL ed eseguire qualsiasi codice esso contenga. Affinché un attacco remoto abbia successo, un utente deve visitare una posizione file system remota non attendibile o una condivisione WebDAV e aprire un file legittimo.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225915">MS11-077</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (2567053)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente in Microsoft Windows. La più grave delle vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file del tipo di carattere appositamente predisposto (ad esempio un file .fon) in una condivisione di rete, in una posizione UNC o WebDAV o nell'allegato di un messaggio di posta elettronica. Affinché un attacco remoto abbia successo, un utente deve visitare una posizione file system remota non attendibile o una condivisione WebDAV e aprire il file del tipo di carattere appositamente predisposto oppure aprire il file come allegato di un messaggio di posta elettronica.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Forefront Unified Access Gateway possono consentire l'esecuzione di codice in modalità remota (2544641)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente in Forefront Unified Access Gateway (UAG). La più grave delle vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visita un sito Web interessato che utilizza un URL appositamente predisposto. Tuttavia, non è in alcun modo possibile obbligare gli utenti a visitare un sito Web di questo tipo. L'utente malintenzionato dovrebbe invece invogliare le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Forefront Unified Access Gateway</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227486">MS11-080</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel driver di funzioni ausiliario può consentire l'acquisizione di privilegi più elevati (2592799)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel driver di funzioni ausiliario di Microsoft (AFD). La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede ad un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di sfruttare tale vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=228596">MS11-082</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Host Integration Server possono consentire un attacco di tipo Denial of Service (2607670)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Host Integration Server che sono state divulgate pubblicamente. Le vulnerabilità possono consentire un attacco di tipo Denial of Service se un utente remoto malintenzionato invia pacchetti di rete appositamente predisposti a un Host Integration Server in ascolto sulla porta UDP 1478 o sulle porte TCP 1477 e 1478. Le procedure consigliate e le configurazioni firewall standard predefinite per i firewall possono contribuire a proteggere le reti dagli attacchi che provengono dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte. In questo caso, le porte Host Integration Server devono essere bloccate da Internet.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Host Integration Server</td>
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
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=221538">MS11-075</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento errato delle librerie in Active Accessibility</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1247">CVE-2011-1247</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227073">MS11-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento errato delle librerie in Media Center</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2009">CVE-2011-2009</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225915">MS11-077</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1985">CVE-2011-1985</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225915">MS11-077</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer del file della libreria di caratteri</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2003">CVE-2011-2003</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225915">MS11-077</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2011">CVE-2011-2011</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227075">MS11-078</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'ereditarietà delle classi in .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1253">CVE-2011-1253</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al cross-site scripting con &quot;response splitting&quot; nelle tabelle Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1895">CVE-2011-1895</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Intercettazione di informazioni personali su determinate piattaforme a cui si fa riferimento nel bollettino</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al cross-site scripting riflesso nelle tabelle Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1896">CVE-2011-1896</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Intercettazione di informazioni personali su determinate piattaforme a cui si fa riferimento nel bollettino</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al cross-site scripting riflesso predefinito</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1897">CVE-2011-1897</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Intercettazione di informazioni personali su determinate piattaforme a cui si fa riferimento nel bollettino</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in siti Web dannosi</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1969">CVE-2011-1969</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217472">MS11-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al blocco dei cookie con annullamento della sessione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2012">CVE-2011-2012</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=227486">MS11-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati nel driver di funzioni ausiliario</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2005">CVE-2011-2005</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota durante uno scorrimento</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1993">CVE-2011-1993</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota di OLEAuto32.dll</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1995">CVE-2011-1995</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota degli elementi opzione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1996">CVE-2011-1996</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota durante un evento OnLoad</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1997">CVE-2011-1997</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota di Jscript9.dll</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1998">CVE-2011-1998</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota degli elementi selezione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1999">CVE-2011-1999</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota degli elementi body</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2000">CVE-2011-2000</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=226382">MS11-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota in una tabella delle funzioni virtuali corrotta</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2001">CVE-2011-2001</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=228596">MS11-082</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service con ciclo infinito in snabase.exe</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2007">CVE-2011-2007</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=228596">MS11-082</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service con accesso alla memoria non assegnata</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2008">CVE-2011-2008</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
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
Nessuno
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
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a54a7ad5-0504-4cc6-9eca-ba9f31c35a17)  
(KB2572066)  
(solo Media Center Edition 2005 e Tablet PC Edition 2005)  
(Critico)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=719b3da5-52ca-4d56-a2c5-69711039e59d)  
(KB2572073)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=822f91f5-bf92-42c4-ad33-b971be37d772)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e942554d-6cb6-4e48-a876-3470671a95a2)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=a911b5b0-5e46-4a37-83e7-595e20585c56)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=96af60b9-4b8d-4a9b-b125-10775bb48252)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9157e677-ab3f-44b0-9735-192bc7421ba7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f1b2dceb-5bef-4522-9001-8dff0545d805)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=719b3da5-52ca-4d56-a2c5-69711039e59d)  
(KB2572073)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=6260318c-e579-4cdf-93e3-4608892bc79e)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f04ad852-1418-4fc4-bd57-f47895bbf3a8)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=67ebf641-1341-4642-96ba-bab5446d7b5d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c8fcf427-17d0-4caa-b406-50703f980862)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0f2444ac-61bd-47cf-9c1e-da86a2b0cfb5)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9a37864e-8543-4c52-aa73-e3c190860d76)  
(Importante)
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b968b0bd-577b-4ea2-a192-a80fe7c20791)  
(KB2572069)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=719b3da5-52ca-4d56-a2c5-69711039e59d)  
(KB2572073)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=172c55f3-6249-4ba3-a4a4-677a03262ff3)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6ffbdb93-7b92-4197-bb6c-5c305e8072a8)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=14ef20d4-3530-49b2-91b7-d278d9098023)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=09e178f8-2bd2-46e1-b975-4938ee1f304d)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3bd62bf6-3400-4c03-95fe-148112b341e8)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29228167-b811-43d7-b4a0-91e385b598a5)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=719b3da5-52ca-4d56-a2c5-69711039e59d)  
(KB2572073)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=f5a0a8db-34d4-4f0a-ab6b-7b2fb420ab91)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7379b3bf-6af0-43cb-bf8b-505e8563fc84)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b35c95f5-30b0-43a9-aa6a-6db63cab0dcb)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9b8030db-1f47-4666-8cb5-1c56577f2340)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b73f4e87-9655-46d5-beb2-ea245dcd280d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0816d729-6769-4ca6-a14e-71750eca8d29)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=719b3da5-52ca-4d56-a2c5-69711039e59d)  
(KB2572073)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=5825cb4a-47d5-423f-b4c5-2d0fc50856c0)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=11c4878e-df58-4369-b9c0-cb0a230c92dd)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=82653b8c-0e58-440d-9702-8847f599caed)  
(KB2605295)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a618cc19-5ebc-462e-a518-d9bfe41ed98e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=42465652-2664-4fd5-9a22-ae847b08e7c8)  
(Importante)
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c27128d-eaf9-4416-b8b1-9edab9102feb)  
(KB2572075)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=630335ac-5a30-46b4-acc1-c4d8bd289668)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=76c8124e-81b9-4a6a-bd53-fbdaf45189aa)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=7de276a3-a20d-49de-82b0-51cb22ad73af)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=96b089c0-a2e7-44cb-9fc4-9569b3993afa)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=44f7f10b-86ff-470f-996a-d4aa51c4d18f)  
(KB2579686)  
(Importante)  
[Windows Media Center TV Pack per Windows Vista (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=60e50f72-4001-423c-831c-8ff1f1b8f090)<sup>[1]</sup>
(KB2579692)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ff53d01b-97b7-40d2-af88-4978f1099a7c)  
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
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c27128d-eaf9-4416-b8b1-9edab9102feb)  
(KB2572075)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9aabd7a2-0b2f-4c42-a9cf-2ec69ae6b82d)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3454940c-acc2-4e09-8154-075b4be1b697)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=3df0c31b-344a-4163-93d2-79df1653b339)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b79a389c-8340-4dd2-9ab1-a0943c5a220f)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cbb66cd7-2688-410f-8a03-fd28e6ef5b01)  
(KB2579686)  
(Importante)  
[Windows Media Center TV Pack per Windows Vista (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=371c7dab-5aa6-4502-80ee-ae69b736b972)<sup>[1]</sup>
(KB2579692)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=47322e11-f1cf-4f70-b939-8cac9bbfc2bc)  
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)\*\*  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c27128d-eaf9-4416-b8b1-9edab9102feb)\*\*  
(KB2572075)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)\*\*<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5660e23c-13a3-4275-ac69-38f03f17491a)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=bd144435-1afd-4d6e-a100-fbd613eee409)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=1a7f9855-20ce-4fe0-a903-bd1f145075df)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7cd1ecec-8a3f-4cb2-833c-a177c9602ff5)\*  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c7498ee-eba4-44fd-8846-0b2e96c96705)\*  
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
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)\*\*  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c27128d-eaf9-4416-b8b1-9edab9102feb)\*\*  
(KB2572075)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)\*\*<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=415b1c59-f3dc-4f4f-b2eb-68692d6efc05)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b0c4949f-bce0-4255-a5f2-cf5ecf7416da)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=28a09e42-5865-48b2-af26-ebc8162c3286)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=456e450c-3928-4130-8127-e4d3f482c1ca)\*  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=40386742-f397-402e-8810-63d3d6ba12a6)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6100e577-deb5-4395-b851-e19e0ca79507)  
(KB2572067)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c27128d-eaf9-4416-b8b1-9edab9102feb)  
(KB2572075)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=31e68c7f-4db5-463f-a315-92f574af080b)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2e9930d3-ba13-446d-bfa0-60720c48203b)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3633402b-96cb-4f36-b137-d07d1baf28c7)  
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Solo Windows 7 per sistemi a 32 bit:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=81be7ff1-3ba2-430c-9edf-619cc246daf2)  
(KB2572076)  
(Critico)  
Solo Windows 7 per sistemi a 32 bit Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=98403988-7438-4260-95b5-a4796dbe0618)  
(KB2572077)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=4de175be-bbb7-4912-ba4e-d6fe96606c9e)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=b49876c7-7c65-4b6d-be9a-9f18be23037b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=02d28e59-b38f-433a-a568-e86f9d43dd42)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=76fcf0ec-9062-4090-acb2-401355341a2b)  
(KB2579686)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9e40bc26-f77f-4b57-9b3d-9d053c19ac56)  
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
Solo Windows 7 per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=81be7ff1-3ba2-430c-9edf-619cc246daf2)  
(KB2572076)  
(Critico)  
Solo Windows 7 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=98403988-7438-4260-95b5-a4796dbe0618)  
(KB2572077)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=16fd238e-6f65-4d38-88ae-2689817588e1)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=cc0773f2-6099-4d55-9971-ee6546369c7f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=904dec69-e8b9-4b23-a5ea-d3e7e9b9df07)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78c099b7-4bcb-4da7-8967-512c6541c541)  
(KB2579686)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=219554e6-eb5a-42d0-90c0-42b4d0772cfd)  
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
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
</td>
<td style="border:1px solid black;">
[**MS11-081**](http://go.microsoft.com/fwlink/?linkid=226382)
</td>
<td style="border:1px solid black;">
[**MS11-075**](http://go.microsoft.com/fwlink/?linkid=221538)
</td>
<td style="border:1px solid black;">
[**MS11-076**](http://go.microsoft.com/fwlink/?linkid=227073)
</td>
<td style="border:1px solid black;">
[**MS11-077**](http://go.microsoft.com/fwlink/?linkid=225915)
</td>
<td style="border:1px solid black;">
[**MS11-080**](http://go.microsoft.com/fwlink/?linkid=227486)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=81be7ff1-3ba2-430c-9edf-619cc246daf2)\*  
(KB2572076)  
(Critico)  
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=98403988-7438-4260-95b5-a4796dbe0618)\*  
(KB2572077)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)\*<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=8435781e-0f77-41d0-abb9-9b70f5b02d33)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=646a9a56-c343-45cb-a255-303602aa5a64)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c7bd50b7-03f1-4ea4-ad71-d428822c62f8)\*  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=39bd4cfb-fe61-41b8-a5a2-73a9e720fc72)\*  
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
Solo Windows Server 2008 R2 per sistemi Itanium:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=81be7ff1-3ba2-430c-9edf-619cc246daf2)  
(KB2572076)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi Itanium Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=98403988-7438-4260-95b5-a4796dbe0618)  
(KB2572077)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=770e7b58-6544-4f59-9893-b3eadf6d6c8a)<sup>[1]</sup>
(KB2572078)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=2676597e-c1d4-4397-8dc4-515ce3d0c5fd)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=aa816682-9652-433c-b1b4-5d0bc17b6a87)  
(KB2564958)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0d35c6d0-6d2d-42bf-a97f-4c5e01b1937e)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Noteper Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS11-078**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS11-076**

<sup>[1]</sup>Windows Media Center TV Pack per Windows Vista è disponibile come componente facoltativo solo nelle installazioni OEM (Original Equipment Manufacturer) delle edizioni Home Premium e Ultimate di Windows Vista. I clienti che hanno installato questo componente facoltativo nei sistemi x64 devono installare entrambi gli aggiornamenti disponibili. Nel rispetto delle procedure consigliate, Microsoft consiglia di installare l'aggiornamento del sistema operativo (KB2579686) prima dell'aggiornamento di Windows Media Center TV Pack (KB2579692). I clienti che hanno installato Media Center TV Pack nei sistemi a 32 bit devono installare solo KB2579692.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Host Integration Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-082**](http://go.microsoft.com/fwlink/?linkid=228596)
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
Microsoft Host Integration Server 2004
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2004 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b7536139-63ea-482a-8d1c-0faad1fcfaa4)  
(KB2578757)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Host Integration Server 2006
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2006 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3bc0c89c-56b2-4463-b671-2a58bed9667b)  
(KB2579597)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Host Integration Server 2009
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2009](http://www.microsoft.com/downloads/details.aspx?familyid=28716ed4-f215-4c69-b6b8-63fbeecefc5b)  
(KB2579598)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Host Integration Server 2010
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2010](http://www.microsoft.com/downloads/details.aspx?familyid=dbbd67d8-68aa-424d-8eaf-a273a71624d1)  
(KB2579599)  
(Importante)
</td>
</tr>
</table>
 

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Silverlight
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-078**](http://go.microsoft.com/fwlink/?linkid=227075)
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
Microsoft Silverlight 4
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=8bde4992-bdf7-4345-835a-4e1fbfcd8c5f) installato in Mac  
(KB2617986)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=8bde4992-bdf7-4345-835a-4e1fbfcd8c5f) installato in tutte le versioni supportate dei client Microsoft Windows  
(KB2617986)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=8bde4992-bdf7-4345-835a-4e1fbfcd8c5f) installato in tutte le versioni supportate dei server Microsoft Windows\*\*  
(KB2617986)
</td>
</tr>
</table>
 
**Note** **per MS11-078**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software di accesso in modalità remota di Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Forefront Unified Access Gateway
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-079**](http://go.microsoft.com/fwlink/?linkid=217472)
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
Microsoft Forefront Unified Access Gateway
</td>
<td style="border:1px solid black;">
[Microsoft Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=770ad8ba-4d9a-404e-9515-6ed1e41682df)<sup>[1]</sup>
(KB2522482)  
(Importante)  
[Aggiornamento 1 di Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=b0de8d20-9c25-41c0-9c02-d263b9ed22fa)<sup>[1]</sup>
(KB2522483)  
(Importante)  
[Aggiornamento 2 di Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=166bdfcb-5088-4471-9d51-a3071ac13b73)<sup>[1]</sup>
(KB2522484)  
(Importante)  
[Microsoft Forefront Unified Access Gateway 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8b6ad2ae-e168-45d9-bd3f-5590e0cbd2b5)<sup>[1]</sup>
(KB2522485)  
(Importante)
</td>
</tr>
</table>
 
**Nota** **per MS11-079**

<sup>[1]</sup>Questo aggiornamento è disponibile soltanto nell'Area download Microsoft.

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

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   [Mila Parkour](http://contagiodump.com), che collabora con Anshul Kothari e Nishant Kaushik di [Adobe Systems, Inc.](http://www.adobe.com) per aver segnalato un problema descritto nel bollettino MS11-075
-   Andrei Lutas di [BitDefender](http://www.bitdefender.com/) per aver segnalato un problema descritto nel bollettino MS11-077
-   Tarjei Mandt di [Norman](http://www.norman.com/) per aver segnalato un problema descritto nel bollettino MS11-077
-   Maik Wellmann per aver segnalato un problema descritto nel bollettino MS11-077
-   David Warren di [CERT/CC](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS11-077
-   Un ricercatore anonimo, che collabora con il programma [Beyond Security's SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html), per aver segnalato un problema descritto nel bollettino MS11-078
-   [Tenable Network Security](http://www.tenable.com/) per aver segnalato tre problemi descritti nel bollettino MS11-079
-   Elisabeth Demeter di [SEC Consult Unternehmensberatung GmbH](http://www.sec-consult.com/) per aver segnalato un problema descritto nel bollettino MS11-079
-   Zhou Bo di [National University of Defense Technology](http://www.nudt.edu.cn/) per aver segnalato un problema descritto nel bollettino MS11-080
-   Vishwas Sharma di McAfee Labs per aver segnalato un problema descritto nel bollettino MS11-081
-   David Bloom di [Greplin](https://www.greplin.com) per aver segnalato due problemi descritti nel bollettino MS11-081
-   Ivan Fratric, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com), per aver segnalato due problemi descritti nel bollettino MS11-081
-   [GWSlabs](http://www.gwslabs.com), che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato un problema descritto nel bollettino MS11-081
-   Sebastian Apelt, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com), per aver segnalato un problema descritto nel bollettino MS11-081
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com), per aver segnalato un problema descritto nel bollettino MS11-081
-   Eduardo Vela Nava di [Google Inc.](http://www.google.com) e David Bloom di [Greplin](https://www.greplin.com) per aver collaborato con noi alle modifiche al sistema di difesa contenute nel bollettino MS11-081
-   [Soroush Dalili](http://www.secproject.com) per aver collaborato con noi alle modifiche al sistema di difesa contenute nel bollettino MS11-081
-   Billy Rios di [Google Inc.](http://www.google.com) per aver collaborato con noi alle modifiche al sistema di difesa contenute nel bollettino MS11-081

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 ottobre 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (26 ottobre 2011): per MS11-078 è stata corretta l'applicabilità dell'installazione Server Core per .NET Framework 4 in Windows Server 2008 R2 per i sistemi x64.

*Built at 2014-04-18T01:50:00Z-07:00*
