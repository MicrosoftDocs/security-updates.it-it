---
TOCTitle: 'MS09-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - ottobre 2009'
ms:assetid: 'ms09-oct'
ms:contentKeyID: 61240040
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - ottobre 2009
=================================================================

Data di pubblicazione: martedì 13 ottobre 2009 | Aggiornamento: martedì 22 giugno 2010

**Versione:** 4.2

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a ottobre 2009.

Con il rilascio dei bollettini del mese di ottobre 2009, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente l'8 ottobre 2009. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini l'14 ottobre 2009 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032407488&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-050</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in SMBv2 possono consentire l'esecuzione di codice in modalità remota (975517)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e due vulnerabilità segnalate privatamente a Microsoft in Server Message Block versione 2 (SMBv2). La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ha inviato un pacchetto SMB appositamente predisposto a un computer che esegue il servizio Server. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-051</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei file di runtime di Windows Media possono consentire l'esecuzione di codice in modalità remota (975682)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nei file di runtime di Windows Media. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente ha aperto un file multimediale appositamente predisposto o ha ricevuto un flusso di contenuti appositamente predisposto da un sito Web o qualunque applicazione fornisca contenuti Web. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-052</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Windows Media Player può consentire l'esecuzione di codice in modalità remota (974112)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Windows Media Player che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se viene riprodotto con Windows Media Player 6.4 un file ASF appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=163979">MS09-054</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (974455)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Si consiglia agli utenti Firefox che eseguono il plug-in di Windows Presentation Foundation (WPF) e non lo hanno disattivato, di applicare questo aggiornamento per la protezione. Per ulteriori informazioni su questo problema, consultare la sezione Domande frequenti sulla vulnerabilità legata alla gestione di componenti HTML – CVE-2009-2529.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-055">MS09-055</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit di ActiveX (973525)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità comune a più controlli ActiveX attualmente sfruttata e che è stata segnalata privatamente. La vulnerabilità presente nei controlli ActiveX compilati mediante la versione vulnerabile di Microsoft Active Template Library (ATL) può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer, creando il controllo ActiveX. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-060</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei controlli ActiveX di Microsoft Active Template Library (ATL) per Microsoft Office possono consentire l'esecuzione di codice in modalità remota (973965)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente presenti nei controlli ActiveX per Microsoft Office compilati con una versione vulnerabile di Microsoft ATL (Active Template Library). Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente carica un componente o un controllo appositamente predisposti. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=160527">MS09-061</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel Common Language Runtime di Microsoft .NET possono consentire l'esecuzione di codice in modalità remota (974378)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità di Microsoft .NET Framework e Microsoft Silverlight. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota su un sistema client se un utente apre una pagina Web appositamente predisposta utilizzando un browser Web in grado di eseguire le applicazioni browser XAML (XBAP) o le applicazioni Silverlight, oppure se un utente malintenzionato riesce a convincere un utente ad eseguire un'applicazione Microsoft .NET appositamente predisposta. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Le vulnerabilità possono consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web. Le applicazioni Microsoft .NET, le applicazioni Silverlight, le pagine XBAP e ASP.NET che non sono dannose non rischiano di essere compromesse a causa di questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework,<br />
Microsoft Silverlight</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=161342">MS09-062</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità di Microsoft Windows GDI+, che sono state segnalate privatamente a Microsoft. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza un file di immagine appositamente predisposto con software interessato o esplora un sito Web che presenta del contenuto appositamente predisposto. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer,<br />
Microsoft .NET Framework,<br />
Microsoft Office,<br />
Microsoft SQL Server,<br />
Strumenti per gli sviluppatori Microsoft,<br />
Microsoft Forefront</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=164004">MS09-053</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel servizio FTP per Internet Information Services possono consentire l'esecuzione di codice in modalità remota (975254)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità divulgate pubblicamente che sono state riscontrate nel servizio FTP in Microsoft Internet Information Services (IIS) 5.0, Microsoft Internet Information Services (IIS) 5.1, Microsoft Internet Information Services (IIS) 6.0 e Microsoft Internet Information Services (IIS) 7.0. In IIS 7.0, solo il servizio FTP 6.0 è interessato. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota (RCE) sui sistemi che eseguono il servizio FTP in IIS 5.0 oppure possono causare un attacco di tipo Denial of Service (DoS) sui sistemi che eseguono il servizio FTP in IIS 5.0, IIS 5.1, IIS 6.0 o IIS 7.0.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-056</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità presenti nella CryptoAPI di Windows possono consentire attacchi di spoofing (974571)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Microsoft Windows che sono state divulgate pubblicamente. Tali vulnerabilità possono consentire attacchi di spoofing se un utente malintenzionato ottiene l'accesso al certificato utilizzato da un utente finale per l'autenticazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Spoofing</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-057</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel servizio di indicizzazione può consentire l'esecuzione di codice in modalità remota (969059)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato crea una pagina Web dannosa che richiama il servizio di indicizzazione mediante una chiamata al relativo componente ActiveX. Questa chiamata può contenere un URL dannoso e sfruttare la vulnerabilità, concedendo all'utente malintenzionato l'accesso al sistema client con gli stessi privilegi dell'utente che sta visitando la pagina Web. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-058</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (971486)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità del kernel di Windows, che sono state segnalate privatamente a Microsoft. La più grave delle vulnerabilità potrebbe consentire l'acquisizione di privilegi più elevati se un utente malintenzionato ha accesso al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare una di queste vulnerabilità, l'utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS09-059</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Local Security Authority Subsystem Service può consentire un attacco di tipo Denial of Service (975467)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato ha inviato un pacchetto appositamente predisposto durante il processo di autenticazione NTLM.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
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
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                                        | Titolo del bollettino                                                                                                                                                            | ID CVE                                                                            | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                                                                                                                                                                                                                                                                                                                                                                                                                           |  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS09-050](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità in SMBv2 possono consentire l'esecuzione di codice in modalità remota (975517)                                                                              | [CVE-2009-2526](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2526)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità legata agli attacchi di tipo Denial of Service.                                                                                                                                                                                                                                                                                                                                                                                              |  
| [MS09-050](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità in SMBv2 possono consentire l'esecuzione di codice in modalità remota (975517)                                                                              | [CVE-2009-2532](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2532)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-050](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità in SMBv2 possono consentire l'esecuzione di codice in modalità remota (975517)                                                                              | [CVE-2009-3103](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3103)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Il codice dannoso è stato reso disponibile pubblicamente.                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-051](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità nei file di runtime di Windows Media possono consentire l'esecuzione di codice in modalità remota (975682)                                                  | [CVE-2009- 0555](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0555) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-051](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità nei file di runtime di Windows Media possono consentire l'esecuzione di codice in modalità remota (975682)                                                  | [CVE-2009- 2525](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2525) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-052](http://technet.microsoft.com/it-it/security/default.aspx) | Una vulnerabilità di Windows Media Player può consentire l'esecuzione di codice in modalità remota (974112)                                                                      | [CVE-2009-2527](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2527)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-053](http://go.microsoft.com/fwlink/?linkid=164004)            | Alcune vulnerabilità nel servizio FTP per Internet Information Services possono consentire l'esecuzione di codice in modalità remota (975254)                                    | [CVE-2009-2521](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2521)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service. Il codice dannoso è stato reso disponibile pubblicamente.                                                                                                                                                                                                                                                                                                                                             |  
| [MS09-053](http://go.microsoft.com/fwlink/?linkid=164004)            | Alcune vulnerabilità nel servizio FTP per Internet Information Services possono consentire l'esecuzione di codice in modalità remota (975254)                                    | [CVE-2009-3023](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3023)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Il codice dannoso è stato reso disponibile pubblicamente.                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-054](http://go.microsoft.com/fwlink/?linkid=163979)            | Aggiornamento cumulativo per la protezione di Internet Explorer (974455)                                                                                                         | [CVE-2009-1547](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1547)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-054](http://go.microsoft.com/fwlink/?linkid=163979)            | Aggiornamento cumulativo per la protezione di Internet Explorer (974455)                                                                                                         | [CVE-2009-2529](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2529)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-054](http://go.microsoft.com/fwlink/?linkid=163979)            | Aggiornamento cumulativo per la protezione di Internet Explorer (974455)                                                                                                         | [CVE-2009-2530](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2530)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Nei sistemi Microsoft Windows 2000, la mancanza di protezioni degli heap aumenta la valutazione dell'Exploitability Index a [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità.                                                                                                                                                                                                                      |  
| [MS09-054](http://go.microsoft.com/fwlink/?linkid=163979)            | Aggiornamento cumulativo per la protezione di Internet Explorer (974455)                                                                                                         | [CVE-2009-2531](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2531)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |  
| [MS09-055](http://technet.microsoft.com/security/bulletin/ms09-055)  | Aggiornamento cumulativo per la protezione dei kill bit ActiveX (973525)                                                                                                         | [CVE-2009-2493](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2493)  | Nessuno                                                                                                                     | (A questa vulnerabilità è già stata assegnata una valutazione dell'Exploitability Index nel [riepilogo dei bollettini di luglio](http://technet.microsoft.com/security/bulletin/ms09-jul). Questo perché la vulnerabilità è stata affrontata per la prima volta nel bollettino [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035).) Vedere anche lo stesso codice CVE nel bollettino [MS09-060](http://technet.microsoft.com/it-it/security/default.aspx). |  
| [MS09-056](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità presenti nella CryptoAPI di Windows possono consentire attacchi di spoofing (974571)                                                                        | [CVE-2009-2510](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2510)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità legata allo spoofing.                                                                                                                                                                                                                                                                                                                                                                                                                        |  
| [MS09-056](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità presenti nella CryptoAPI di Windows possono consentire attacchi di spoofing (974571)                                                                        | [CVE-2009-2511](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2511)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità legata allo spoofing.                                                                                                                                                                                                                                                                                                                                                                                                                        |  
| [MS09-057](http://technet.microsoft.com/it-it/security/default.aspx) | Una vulnerabilità nel servizio di indicizzazione può consentire l'esecuzione di codice in modalità remota (969059)                                                               | [CVE-2009-2507](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2507)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-058](http://technet.microsoft.com/it-it/security/default.aspx) | Le vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (971486)                                                                       | [CVE-2009-2515](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2515)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-058](http://technet.microsoft.com/it-it/security/default.aspx) | Le vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (971486)                                                                       | [CVE-2009-2516](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2516)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Questa vulnerabilità provoca una condizione di Denial of Service quando colpita utilizzando una condivisione di rete, ed una condizione di acquisizione di privilegi più elevati quando utilizzata localmente per colpire un sistema locale.                                                                                                                                                                                                                                |  
| [MS09-058](http://technet.microsoft.com/it-it/security/default.aspx) | Le vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (971486)                                                                       | [CVE-2009-2517](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2517)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.                                                                                                                                                                                                                                                                                                                                                                                                       |  
| [MS09-059](http://technet.microsoft.com/it-it/security/default.aspx) | Una vulnerabilità in Local Security Authority Subsystem Service può consentire un attacco di tipo Denial of Service (975467)                                                     | [CVE-2009-2524](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2524)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità legata agli attacchi di tipo Denial of Service.                                                                                                                                                                                                                                                                                                                                                                                              |  
| [MS09-060](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità nei controlli ActiveX di Microsoft Active Template Library (ATL) per Microsoft Office possono consentire l'esecuzione di codice in modalità remota (973965) | [CVE-2009-0901](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0901)  | Nessuno                                                                                                                     | (A questa vulnerabilità è già stata assegnata una valutazione dell'Exploitability Index nel [riepilogo dei bollettini di luglio](http://technet.microsoft.com/security/bulletin/ms09-jul). Questo perché la vulnerabilità è stata affrontata per la prima volta nel bollettino [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035)).                                                                                                                        |  
| [MS09-060](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità nei controlli ActiveX di Microsoft Active Template Library (ATL) per Microsoft Office possono consentire l'esecuzione di codice in modalità remota (973965) | [CVE-2009-2493](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2493)  | Nessuno                                                                                                                     | (A questa vulnerabilità è già stata assegnata una valutazione dell'Exploitability Index nel [riepilogo dei bollettini di luglio](http://technet.microsoft.com/security/bulletin/ms09-jul). Questo perché la vulnerabilità è stata affrontata per la prima volta nel bollettino [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035).) Vedere anche lo stesso codice CVE nel bollettino [MS09-055](http://technet.microsoft.com/security/bulletin/ms09-055).  |  
| [MS09-060](http://technet.microsoft.com/it-it/security/default.aspx) | Alcune vulnerabilità nei controlli ActiveX di Microsoft Active Template Library (ATL) per Microsoft Office possono consentire l'esecuzione di codice in modalità remota (973965) | [CVE-2009-2495](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2495)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Questa vulnerabilità riguarda l'intercettazione di informazioni personali.                                                                                                                                                                                                                                                                                                                                                                                                  |  
| [MS09-061](http://go.microsoft.com/fwlink/?linkid=160527)            | Alcune vulnerabilità nel Common Language Runtime di Microsoft .NET possono consentire l'esecuzione di codice in modalità remota (974378)                                         | [CVE-2009-0090](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0090)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-061](http://go.microsoft.com/fwlink/?linkid=160527)            | Alcune vulnerabilità nel Common Language Runtime di Microsoft .NET possono consentire l'esecuzione di codice in modalità remota (974378)                                         | [CVE-2009-0091](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0091)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-061](http://go.microsoft.com/fwlink/?linkid=160527)            | Alcune vulnerabilità nel Common Language Runtime di Microsoft .NET possono consentire l'esecuzione di codice in modalità remota (974378)                                         | [CVE-2009-2497](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2497)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Esiste la possibilità di attacchi con impatto su Internet.                                                                                                                                                                                                                                                                                                                                                                                                                  |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2500](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2500)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2501](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2501)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2502](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2502)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2503](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2503)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2504](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2504)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2518](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2518)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-2528](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2528)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |  
| [MS09-062](http://go.microsoft.com/fwlink/?linkid=161342)            | Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (957488)                                                                               | [CVE-2009-3126](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3126)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
  
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
</tr>
<tr>
<th colspan="13">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Nessuno**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec DirectShow WMA Voice](http://www.microsoft.com/downloads/details.aspx?familyid=4fe0dff5-04d9-4409-8d1d-52419537126b)  
(KB969878)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=8f850a82-61f9-447b-a0aa-a2c192cc5d2e)  
(KB954155)  
(Critico)  
[Gestione compressione audio](http://www.microsoft.com/downloads/details.aspx?familyid=6dfd5405-cabe-4bd7-9330-b6bde1d99194)  
(KB975025)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=13035ef7-7e47-487c-8b7c-7795d33ce7de)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=26515c7b-d7a6-4405-96b5-a518dcb39d38)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8154ba37-0fbc-4d31-9d6e-0b21586ad65a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=edfea805-9544-4dc0-a52c-d7594205657b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f3fef608-dafb-4b37-a65a-9cc4ae8e2c4c)  
(KB958869)  
(Critico)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ecf78619-80fa-417d-852b-1b5b2cf574e2)  
(KB971108)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3e534aa8-29c2-4379-9f57-931a6ff47418)  
(KB971110)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e6f5e730-85cc-4c08-a50d-c456b1e9f5bc)  
(KB971111)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=7fecd367-aaff-458b-91bc-8925c8e57528)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=52b9198d-b65f-467a-a5ab-141e23d64a86)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=b34d94b5-b828-4e16-a636-04344c60d945)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=bdfa6583-28a2-4d6b-91d2-157a8518b664)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="13">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec DirectShow WMA Voice](http://www.microsoft.com/downloads/details.aspx?familyid=4fe0dff5-04d9-4409-8d1d-52419537126b)  
(KB969878)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=4516c219-e357-485e-a52b-23dcb8ee49d8)  
(KB954155)  
(Critico)  
(solo Windows XP Service Pack 2)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=746d3440-5a6a-421e-9286-7b534a1dfe54)  
(KB954155)  
(Critico)  
(solo Windows XP Service Pack 3)  
[Gestione compressione audio](http://www.microsoft.com/downloads/details.aspx?familyid=6ecc7129-8caa-4daf-a8e2-8f3536225fb3)  
(KB975025)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=b2efe1ac-d8d7-41bb-b87d-fc5e22afef0f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=9aacf890-afb4-46a7-a13f-dd9fe3c0ca4a)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=dc166dc6-577f-4d8d-94df-dd963233dd85)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=8799159d-df69-49f6-9db5-49147690ce0c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=171d43d3-669c-4923-b266-e47591833c05)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=1bc56c26-1c7c-47e3-94f4-37af7e00392c)  
(KB953295)  
(Critico)  
(Solo Tablet PC Edition 2005 e Media Center Edition 2005)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e2acde20-a6d3-4135-b6eb-1214f743d474)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2ae0bdd4-f8b2-420a-b1ac-d2cdaa87c828)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9c5ab624-e37b-418a-a919-d8f652b15679)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=768fd74e-0a2f-4353-ac22-65d0d6321739)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cece4c55-0756-4357-9d2d-6709e8426068)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e997ea40-668e-40df-bd50-0ca53437b375)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec DirectShow WMA Voice](http://www.microsoft.com/downloads/details.aspx?familyid=c116ae9d-e416-4b7d-be75-4b4b2ebcc33a)  
(KB969878)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=4729de51-8fd8-46c6-b4ad-9c9f25202684)  
(KB954155)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=fe0d51b2-345e-4eb7-a036-d8c3f6a683d2) in Windows Media Format SDK 9.5 x64 Edition  
(KB954155)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=a866a490-6d3a-4ecd-acf4-770312ba2fd6) in Windows Media Format SDK 11  
(KB954155)  
(Critico)  
[Gestione compressione audio](http://www.microsoft.com/downloads/details.aspx?familyid=46daf7c7-1cd3-4f47-9c7a-d5eb6ea7327b)  
(KB975025)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=a9e7dfd8-7ba1-4f14-8e60-92ef00d91467)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=89a2cf2a-a7a2-4d4b-aa6f-24dde288d500)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=bd54e595-25f2-4839-a838-2a0f809bde2b)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=77b18fc2-e769-47c6-8e72-916716a49e58)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c08623bf-94bc-4c50-8c10-f50fb8448a0b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ad92503a-8c91-4d73-98b0-942d7961637d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=819dd2d1-cad5-4784-9baf-185d8a76df5d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ad29696d-4611-4a12-9dfa-74fa6866b759)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=270ec100-5ba1-4f8c-aa36-105d30ad57bf)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5459b7d4-1fab-4a04-ab9d-b8323505c1e2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=17008892-7950-44c4-850d-002c8d73495f)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<th colspan="13">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec DirectShow WMA Voice](http://www.microsoft.com/downloads/details.aspx?familyid=4fe0dff5-04d9-4409-8d1d-52419537126b)  
(KB969878)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=00b3cb86-c9eb-4fbe-987e-2b0d94271d87)  
(KB954155)  
(Critico)  
[Gestione compressione audio](http://www.microsoft.com/downloads/details.aspx?familyid=ab1803ff-2371-487f-a7b6-95747c46ba4e)  
(KB975025)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=5f82d01c-573e-425e-b9f2-86a54f377b19)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=8101625d-ee93-46e5-aec2-3bdbf2d86472)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4647bcf1-69fb-4ad6-9e03-7bc22d8a914b)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=9eae7eca-1a6f-4397-a6e2-7dda6b9d5276)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f3249c99-82e4-45dc-a254-28e647e822c8)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d1b4a58b-f0b1-4400-a6e6-0255b0513bd1) (KB953298)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=414466a4-39a0-476d-9a43-ae7674cbd6a0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48256ea3-b433-4e84-9019-22300069cfc1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d170cef9-f5d2-4fcd-997b-e778ad5a6797)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=78072164-84d1-44da-8ede-2a9d212d47a9)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e3f3842-f8fd-4969-a2cf-706db38d7580)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9dff4662-7771-4bdc-87ec-7899d79b3a55)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec DirectShow WMA Voice](http://www.microsoft.com/downloads/details.aspx?familyid=c116ae9d-e416-4b7d-be75-4b4b2ebcc33a)  
(KB969878)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=13ba4839-7fa9-4bbb-95f6-3fafb6c49f20)  
(KB954155)  
(Critico)  
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=fe0d51b2-345e-4eb7-a036-d8c3f6a683d2) in Windows Media Format SDK 9.5 x64 Edition  
(KB954155)  
(Critico)  
[Gestione compressione audio](http://www.microsoft.com/downloads/details.aspx?familyid=46daf7c7-1cd3-4f47-9c7a-d5eb6ea7327b)  
(KB975025)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=65e9036e-2e1b-40ff-a84b-c507107bcce8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=2f966053-01eb-4a23-a9d5-71deac2498ea)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e7d77bd9-8317-42f3-9ad1-a0b8bfa65b53)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=708a549d-11fd-43bf-a6e1-309e3205d59d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1ad3f7b3-58d5-4507-ae20-a265e47cee9c)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eb95e8d9-6ef5-4526-99d2-507e50de049b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=61bded07-201e-4815-ac1e-468bf907e063)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d170cef9-f5d2-4fcd-997b-e778ad5a6797)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8aa1f97d-ad53-4450-bb93-4a147dd10a87)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=95286b8d-4b53-4e6c-af59-e9e18fad3559)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8df7a2d9-2f97-4f18-84e8-415a1632cf09)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
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
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=79a1a94d-3b47-47e9-9476-2f591c3f6a59)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=07e66c09-2cd7-47ba-bf87-d3da602184b4)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=575e75d9-e348-4fbb-9eaa-43240e4d715e)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d4a328b5-5470-46b0-86c7-cfe0e6a3ea01) (KB953300)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=491874d4-5eea-4545-9b7d-3861857c862e) (KB974417)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a678ceb9-a37a-4c29-8bd1-f209922990e5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b99d4d9b-e0cc-4a8c-ad99-6a53958b37c8)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=2ede1eb9-7f5f-411d-bbc3-5db46d80e0bb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=fb5678b9-5ef1-42db-902e-c9ea02880e0a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=faef714b-5f46-47f2-bea7-881df05a1bc0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=83c77015-7f96-4c0d-bd56-60aef90ea2f8)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<th colspan="13">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29842c0c-8930-4b5f-83c6-1a718974b63f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=f17ee0ea-f1e2-49f4-9f90-60296246ddfe)  
(KB954155)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f6995616-2a84-4c26-9599-26f1314873ed)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e8f6014f-950b-4e11-a105-51d298069f1a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7313c03b-8844-4086-a0cc-43dfdb3ca48c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=6f99521e-86b3-4083-9132-e5ac06d40b63) (KB974468)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3cf329c6-6d3d-41eb-bb72-8ba241df0882) (KB974292)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7438eb1e-6e86-4aa1-b1f4-f71a7699d233) (KB974467)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=19aa01f3-026d-4264-85f8-216d0597969b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bb96eb1c-66a2-4276-9773-eea22179bcd4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b5a9a95-9439-40c8-acef-000b919daa04)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=acf6f3e6-282e-4f05-9060-8d0ebb874b97)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=04ae306b-0d0d-4767-ab54-cc11aec477ed)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=30e5410d-0942-4964-9037-52330488efda) (KB974291)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 and Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72fe9066-2397-439d-82fb-2b7f9d2bcce8) (KB974469)  
(Critico)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614a92ee-0512-4ccc-b6b8-32ebcec8e6a4) (KB974470)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=acf6f3e6-282e-4f05-9060-8d0ebb874b97)  
(Moderato)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=62ed5d0a-5ca6-4942-80c9-7808b14cb6b5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=26905f12-92c7-4d45-99e7-227f03d2cb82)  
(KB954155)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b3de5236-afdd-436e-8648-5382d564cc99)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=85978f28-5fc0-481b-9b03-2021c785889b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7216bcb1-ff16-402b-ad1b-1500d46d0157)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=6f99521e-86b3-4083-9132-e5ac06d40b63) (KB974468)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3cf329c6-6d3d-41eb-bb72-8ba241df0882) (KB974292)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7438eb1e-6e86-4aa1-b1f4-f71a7699d233) (KB974467)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8f5f0c1d-1dd6-47fa-aef2-d3c96c8fc06e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bce096c8-833b-45c8-99cd-1280f0744f2f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4a60f789-1a4a-49a8-8d13-fda989ed40be)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=13a3fe0b-e300-4568-aa08-d586ab8d5434)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=58c995ca-f308-4e07-8e60-2e542384d95d)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=30e5410d-0942-4964-9037-52330488efda) (KB974291)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2 and Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72fe9066-2397-439d-82fb-2b7f9d2bcce8) (KB974469)  
(Critico)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f) (KB953297)  
(Critico)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614a92ee-0512-4ccc-b6b8-32ebcec8e6a4) (KB974470)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=13a3fe0b-e300-4568-aa08-d586ab8d5434)  
(Moderato)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr>
<th colspan="13">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ff6bfcf3-76c9-4c45-b57d-22f94458dd6e)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=2eaa9857-a147-4f31-9bf4-b9e2cf4c15c3)\*\*  
(KB954155)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=72dd580e-eb53-41da-a5c0-a392ad388bfc)\*\*  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=1baf7e96-ba3e-47e7-8ea3-eb092e653a39)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=51eb56fa-8204-45f3-86d7-6d03a2c8d78d)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)\*\*  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=30e5410d-0942-4964-9037-52330488efda)\*\*  
(KB974291)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72fe9066-2397-439d-82fb-2b7f9d2bcce8)\*\*  
(KB974469)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=fd1694af-8873-43aa-9243-91f7cde452b7)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d9c5039f-d0cf-4d84-850f-f2f7701dcb79)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f9b487af-fe73-42a8-b240-d59c4321f95b)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=71aec6f6-a36b-465e-8885-b094dfd30423)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f2f617c2-f149-4e9b-bfdd-08ed0f3f99db)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)\*\*  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614a92ee-0512-4ccc-b6b8-32ebcec8e6a4)\*\*  
(KB974470)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=71aec6f6-a36b-465e-8885-b094dfd30423)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aff6f9c7-4a72-48f2-b750-204d796c7daa)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Audio Voice Decoder](http://www.microsoft.com/downloads/details.aspx?familyid=70aabba3-53d6-4b52-be83-6d3f3869ecbd)\*\*  
(KB954155)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0111d741-bda4-4a50-a12b-d3337ff4441d)\*\*  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7a4b755b-7fa0-43aa-8862-c1d0c7d94c2c)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=131b047a-ae93-4a99-83e5-71d5a79e96ea)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)\*\*  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=30e5410d-0942-4964-9037-52330488efda)\*\*  
(KB974291)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72fe9066-2397-439d-82fb-2b7f9d2bcce8)\*\*  
(KB974469)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a x64](http://www.microsoft.com/downloads/details.aspx?familyid=41bc4cdb-273a-4a6e-80d9-c8ce20e32da9)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=db969ddc-708e-42b7-9956-6c27bf346bbb)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0d8a2a3e-d7d4-47fb-8364-16fce28e4d38)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=88f4189f-71fe-404a-869e-3f76692acf94)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=deb84cb8-2ba3-47e3-9185-2bbc5b0a7e18)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)\*\*  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614a92ee-0512-4ccc-b6b8-32ebcec8e6a4)\*\*  
(KB974470)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=88f4189f-71fe-404a-869e-3f76692acf94)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7b70108b-7f59-4898-ab4e-76be990de878)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e81f30b7-ef05-4488-b62a-d330e17129cf)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3d16c5bf-ee5c-4220-9755-5cb92eac2aae)  
(Basso)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=30e5410d-0942-4964-9037-52330488efda)  
(KB974291)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72fe9066-2397-439d-82fb-2b7f9d2bcce8)  
(KB974469)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a4f42085-1cb9-4b8d-a931-85be71fdf06d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a221451a-cb4e-4a43-a225-4b1e86e87525)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8962f0b6-f346-4e88-9d83-4d15b699dd9d)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3e0f0b1c-ca5d-43fc-9770-73396a5f191c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4aac0e3e-9b49-4a4a-ab17-707ff03b4d9b)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78ac8b97-8327-4ae1-8bb0-6cf227f3968f)  
(KB953297)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614a92ee-0512-4ccc-b6b8-32ebcec8e6a4)  
(KB974470)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Come sopra
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3e0f0b1c-ca5d-43fc-9770-73396a5f191c)  
(Moderato)
</td>
<td style="border:1px solid black;">
Come sopra
</td>
</tr>
<tr>
<th colspan="13">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
Nessuno
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit
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
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=89d1fb78-68cd-48dd-afc2-15a79ebe9fde)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=b64bcc14-38a7-45b9-8f85-acc573777506)  
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
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=ad6f06d5-27db-445d-a8b2-c42adc90afc0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=35b85783-90df-4f67-a3cb-02351432133e)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64
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
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=10d9f7ac-65f4-437c-91cc-171632c69b0e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=809e29f3-ec68-4a2b-b04e-11759dd16001)  
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
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=70cd0270-77e9-492a-82d9-798364640c10)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=97010f2c-6c10-4fda-84fd-6c8749968db5)  
(Importante)
</td>
</tr>
<tr>
<th colspan="13">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-050**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-051**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-052**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-054**](http://go.microsoft.com/fwlink/?linkid=163979)
</td>
<td style="border:1px solid black;">
[**MS09-055**](http://technet.microsoft.com/security/bulletin/ms09-055)
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
</td>
<td style="border:1px solid black;">
[**MS09-053**](http://go.microsoft.com/fwlink/?linkid=164004)
</td>
<td style="border:1px solid black;">
[**MS09-056**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-057**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-058**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-059**](http://technet.microsoft.com/it-it/security/default.aspx)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
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
Nessuno
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
Windows Server 2008 R2 per sistemi x64
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
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f50307d6-7869-4996-9ff7-23f87d08994b)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=bcd2b944-6852-48f2-820b-cce7d195e391)\*\*  
(Basso)
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
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=ce78c019-ec08-4ec6-abec-334f5ec5cb76)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=597ac3a7-e02d-49a5-9b8e-d097e867acea)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
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
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=9b6a28ae-b3f2-42b0-8209-e3950ec37abb)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=85e76e55-3766-4ffe-9a18-8655de935b7c)  
(Basso)
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
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=6442a77a-3c0d-4beb-b2d2-2885376c2135)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=abc94857-37d8-4bb8-ad9e-46e687fca40e)  
(Importante)
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS09-061**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Note per MS09-062**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS09-059**

<sup>[1]</sup>Questo sistema operativo risulta interessato solo quando è stato installato KB968389, protezione estesa per l'autenticazione (vedere [Advisory Microsoft sulla sicurezza 973811](http://technet.microsoft.com/security/advisory/973811)). Per ulteriori informazioni, vedere la voce Domande frequenti sull'aggiornamento per la protezione in [MS09-059](http://technet.microsoft.com/it-it/security/default.aspx).

#### Suite e software Microsoft Office

 
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
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-060**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP
</td>
<td style="border:1px solid black;">
[Microsoft Outlook 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=04878c2c-eb97-426f-be08-89036a6799db)  
(KB973702)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b4ac7fbe-dd19-4940-a576-89a6b7ed602d)<sup>[2]</sup>
(KB974811)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office Outlook 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=79e2b2e8-d5e8-4014-b489-720af2b5083d)  
(KB973705)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=48752ab4-5928-476d-a8bc-e998d188b1f7)<sup>[3]</sup>
(KB972580)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office Outlook 2007 Service Pack 1 e Microsoft Office Outlook 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d39234a3-c62c-44ba-a626-3179a183ca09)  
(KB972363)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office System 2007 Service Pack 1 e Microsoft Office System 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98d7c4ab-f8ca-4806-a609-453fb29b02ec)\[4\]  
(KB972581)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Altro software Microsoft Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-060**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2002 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=920ee70b-c5c1-47b5-8f33-938ffe14eea4)  
(KB975365)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Visualizzatore di Microsoft Office Visio
</td>
<td style="border:1px solid black;">
Visualizzatore di Microsoft Visio 2002<sup>[1]</sup>
(Critico)  
Visualizzatore di Microsoft Office Visio 2003<sup>[1]</sup>
(Critico)  
[Visualizzatore di Microsoft Office Visio 2007 Service Pack 1 e Visualizzatore di Microsoft Office Visio 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d20004c5-dd01-459e-8120-5f127e20c085)  
(KB973709)  
(Critico)
</td>
<td style="border:1px solid black;">
[Visualizzatore di Microsoft Office Visio 2007 Service Pack 1 e Visualizzatore di Microsoft Office Visio 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98d7c4ab-f8ca-4806-a609-453fb29b02ec)\[4\]  
(KB972581)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Project
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Project 2002 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b4ac7fbe-dd19-4940-a576-89a6b7ed602d)<sup>[2]</sup>
(KB974811)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Word Viewer, Microsoft Office Excel Viewer e Microsoft PowerPoint Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Word Viewer 2003 Service Pack 3 e Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=48752ab4-5928-476d-a8bc-e998d188b1f7)<sup>[3]</sup>
(KB972580)  
(Importante)  
[Microsoft Office Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98d7c4ab-f8ca-4806-a609-453fb29b02ec)\[4\]  
(KB972581)  
(Importante)  
[PowerPoint Viewer 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98d7c4ab-f8ca-4806-a609-453fb29b02ec)\[4\]  
(KB972581)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=98d7c4ab-f8ca-4806-a609-453fb29b02ec)\[4\]  
(KB972581)  
Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Works 8.5](http://www.microsoft.com/downloads/details.aspx?familyid=6f96de9a-62d8-428f-9567-51d55c129be6)  
(KB973636)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS09-060**

<sup>[1]</sup>Microsoft consiglia agli utenti del Visualizzatore di Microsoft Visio 2002 e Microsoft Visio 2003 di effettuare l'aggiornamento al Visualizzatore di Microsoft Office Visio 2007 Service Pack 2.

**Note per MS09-062**

<sup>[2]</sup>Questi aggiornamenti sono identici.

<sup>[3]</sup>Questi aggiornamenti sono identici.

\[4\]Questi aggiornamenti sono identici.

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
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
SQL Server 2000 Reporting Services Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR  
Non applicabile  
Aggiornamento QFE:  
[SQL Server 2000 Reporting Services Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=33554f96-5af7-4683-a537-9db293b67b8d)  
(KB970899)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d971a262-1dfb-498c-a4f3-59fdc1b85d23)<sup>[1]</sup>
(KB970895)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=76d3d653-e9a0-48bc-afae-d3553f7b9235)<sup>[1]</sup>
(KB970896)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d971a262-1dfb-498c-a4f3-59fdc1b85d23)<sup>[1]</sup>
(KB970895)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=76d3d653-e9a0-48bc-afae-d3553f7b9235)<sup>[1]</sup>
(KB970896)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d971a262-1dfb-498c-a4f3-59fdc1b85d23)<sup>[1]</sup>
(KB970895)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=76d3d653-e9a0-48bc-afae-d3553f7b9235)<sup>[1]</sup>
(KB970896)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR  
[SQL Server 2005 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0d878f4b-71e8-4170-9a14-1bce684811ce)<sup>[2]</sup>
(KB970892)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e6f307c1-8b21-406e-9c6f-b1a3a1e9a98f)<sup>[2]</sup>
(KB970894)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 x64 Edition Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 x64 Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0d878f4b-71e8-4170-9a14-1bce684811ce)<sup>[2]</sup>
(KB970892)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 x64 Edition Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e6f307c1-8b21-406e-9c6f-b1a3a1e9a98f)<sup>[2]</sup>
(KB970894)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 per sistemi Itanium Service Pack 3
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0d878f4b-71e8-4170-9a14-1bce684811ce)<sup>[2]</sup>
(KB970892)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e6f307c1-8b21-406e-9c6f-b1a3a1e9a98f)<sup>[2]</sup>
(KB970894)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS09-062**

<sup>[1]</sup>I clienti di SQL Server 2005 Service Pack 2 con una dipendenza dai prodotti Sharepoint di Reporting Services devono installare anche il componente aggiuntivo di [Microsoft SQL Server 2005 Reporting Services per il Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=%20f4d4d0ae-e5d4-4ed1-8d78-7137578161ce&displaylang=en) dall'Area download Microsoft.

<sup>[2]</sup>I clienti di SQL Server 2005 Service Pack 3 con una dipendenza dai prodotti Sharepoint di Reporting Services devono installare anche il componente aggiuntivo di [Microsoft SQL Server 2005 Reporting Services per il Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=%20648766ac-2a35-4238-a3f4-c26d7077f2a9&displaylang=en) dall'Area download Microsoft.

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
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 2](http://www.microsoft.com/silverlight/get-started/install/default.aspx)<sup>[1]</sup> installato su MAC  
(KB970363)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Silverlight
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 2](http://www.microsoft.com/silverlight/get-started/install/default.aspx)<sup>[1]</sup> installato in tutte le versioni dei client Microsoft Windows  
(KB970363)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 2](http://www.microsoft.com/silverlight/get-started/install/default.aspx)<sup>[1]</sup> installato in tutte le versioni dei server Microsoft Windows\*\*  
(KB970363)  
(Moderato)
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
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9e3b52d3-b211-4d62-891c-ae8f2e4ffc6c)  
(KB971022)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio 2005 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e186aeed-e9d7-4a02-84b3-bbed116ca060)  
(KB971023)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2008
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2008](http://www.microsoft.com/downloads/details.aspx?familyid=4fa10c93-ce20-43df-a725-ef4c77353747)  
(KB972221)  
(Nessun livello di gravità<sup>[2]</sup>)
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
[Microsoft Visual Studio 2008 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b904dee8-8a26-43f8-8ca9-86ad12cfdb52)  
(KB972222)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual FoxPro 8.0 Service Pack 1 installato in Microsoft Windows 2000 Service Pack 4  
(KB971104)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 8.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e5d0d515-4b36-4025-bc6f-1c5cdf09e1af)  
installato in Windows 2000 Service Pack 4  
(KB971104)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual FoxPro 9.0 Service Pack 2 installato in Microsoft Windows 2000 Service Pack 4  
(KB971105)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 9.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2a930f56-59ac-49a6-830f-bfae7c540ec7)  
installato in Windows 2000 Service Pack 4  
(KB971105)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Report Viewer
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-061**](http://go.microsoft.com/fwlink/?linkid=160527)
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Report Viewer 2005 Service Pack 1 Redistributable Package
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Report Viewer 2005 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=0dfaf300-2b53-4678-a779-0d805ddfe538)  
(KB971117)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Report Viewer 2008 Redistributable Package
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Report Viewer 2008 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=42ed040f-cf94-4754-b0b3-c8016fbcbe22)  
(KB971118)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Report Viewer 2008 Redistributable Package Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Report Viewer 2008 Redistributable Package Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6aaa74bd-a46e-4478-b4e1-2063d18d2d42)  
(KB971119)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Platform SDK Redistributable: GDI+
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Platform SDK Redistributable: GDI+](http://www.microsoft.com/downloads/details.aspx?familyid=6a63ab9c-df12-4d41-933c-be590feaa05a)  
(KB975337)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
</tr>
</table>
 
**Note per MS09-061**

<sup>[1]</sup>Questo download effettua l'aggiornamento di Microsoft Silverlight 2 a Microsoft Silverlight 3, che risolve la vulnerabilità descritta nel bollettino.

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Note per MS09-062**

<sup>[2]</sup>I livelli di gravità non sono applicabili a questo aggiornamento perché Microsoft non ha individuato alcun vettore di attacco per le vulnerabilità trattate in questo bollettino e specifiche di questo software. Tuttavia, questo aggiornamento per la protezione viene offerto agli sviluppatori che utilizzano il software affinché possano rilasciare le versioni aggiornate delle proprie applicazioni.

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
Microsoft Forefront Security
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-062**](http://go.microsoft.com/fwlink/?linkid=161342)
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
Microsoft Forefront Client Security 1.0
</td>
<td style="border:1px solid black;">
[Microsoft Forefront Client Security 1.0](http://www.microsoft.com/downloads/details.aspx?familyid=c0ce624c-8df3-4223-8a7a-5cba4ac334a8)  
installato in Windows 2000 Service Pack 4  
(KB975962)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS09-062**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Note** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx101321101040.aspx?pid=cl100570421040).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860(en-us).aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/systemcenter/configmgr/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/mapp/partners.mspx).

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

-   [Matthieu Suiche](http://www.msuiche.net/) del [Netherlands Forensics Institute](http://www.nederlandsforensischinstituut.nl/) per aver segnalato un problema descritto nel bollettino MS09-050
-   Ivan Fratric di [Zero Day Initiative](http://www.zerodayinitiative.com/) e Jun Xie di [McAfee Avert Labs](http://www.avertlabs.com/) per aver segnalato per aver segnalato un problema descritto nel bollettino MS09-051
-   Vinay Anantharaman di [Adobe Systems, Inc](http://www.adobe.com/) per aver segnalato un problema descritto nel bollettino MS09-051
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-052
-   Skylined di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS09-054
-   Mark Dowd di [IBM ISS X-Force](http://www.iss.net/) per aver segnalato un problema descritto nel bollettino MS09-054
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-054.
-   Sam Thomas di eshu.co.uk, che collabora con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-054
-   Ian Wright e Jean-Luc Giraud di [Citrix](http://www.citrix.com/) per aver collaborato con Microsoft su un problema descritto nel bollettino MS09-056
-   Dan Kaminsky di [IOActive](http://www.ioactive.com/) per aver segnalato due problemi descritti nel bollettino MS09-056
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-057
-   Tavis Ormandy e Neel Mehta di [Google Inc.](http://www.google.com/) per aver segnalato due problemi descritti nel bollettino MS09-058
-   [NSFocus Security Team](http://www.nsfocus.com/) per aver segnalato un problema descritto nel bollettino MS09-058
-   David Dewey di [IBM ISS X-Force](http://www.iss.net/) per aver segnalato un problema descritto nel bollettino MS09-060
-   Ryan Smith di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato due problemi descritti nel bollettino MS09-060
-   [Pavel Minaev](http://int19h.org/) per aver segnalato un problema descritto nel bollettino MS09-061
-   Jeroen Frijters di [Sumatra](http://www.sumatra.nl/) per aver segnalato un problema descritto nel bollettino MS09-061
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-062
-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino MS09-062
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-062
-   Ivan Frantic di [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-062
-   Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato due problemi descritti nel bollettino MS09-062
-   Carlo Di Dato (Shinnai) per aver segnalato un problema descritto nel bollettino MS09-062
-   Marsu Pilami di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-062
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS09-062

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/?ln=itcommon/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (13 ottobre 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (14 ottobre 2009): È stato corretto il collegamento per Windows XP x64 Edition Service Pack 2 per MS09-055.
-   V1.2 (18 ottobre 2009): È stato rivisto il Riepilogo del bollettino MS09-054 con lo scopo di fornire indicazioni agli utenti Firefox.
-   V2.0 (28 ottobre 2009): Sono stati aggiunti il Visualizzatore di Microsoft Office Visio 2007, il Visualizzatore di Microsoft Office Visio 2007 Service Pack 1 e il Visualizzatore di Microsoft Office Visio 2007 Service Pack 2 come software interessati per MS09-062 e sono state aggiunte delle note per MS09-062 per i clienti di SQL Server 2005 con una dipendenza dai prodotti Sharepoint di Reporting Services.
-   V3.0 (2 novembre 2009): È stato rivisto per comunicare la disponibilità di una correzione rapida per MS09-054 che risolve i problemi di compatibilità tra le applicazioni. I clienti che hanno già installato questo aggiornamento potrebbero installare la correzione rapida dall'articolo della Microsoft Knowledge Base 976749.
-   V3.1 (4 novembre 2009): Sono stati rimossi i riferimenti non corretti alla versione originale del Visualizzatore di Microsoft Office Visio 2007 come software interessato in MS09-060 e MS09-062.
-   V4.0 (10 novembre 2009): Il bollettino è stato rivisto per comunicare il rilascio dell'aggiornamento per Gestione compressione audio in Microsoft Windows 2000 Service Pack 4 in MS09-051 per risolvere un problema di rilevamento. Si tratta di una modifica che riguarda esclusivamente il rilevamento; non sono state effettuate modifiche ai file binari. I clienti che hanno già aggiornato i propri sistemi non devono reinstallare questo aggiornamento.
-   V4.1 (12 gennaio 2010): Microsoft Expression Web, Microsoft Expression Web 2, Microsoft Office Groove 2007 e Microsoft Office Groove 2007 Service Pack 1 sono stati rimossi come software interessato nel bollettino MS09-062.
-   V4.2 (22 giugno 2010): È stato rimosso .NET Framework 1.1 Service Pack 1 come componente interessato in Windows 7 e Windows Server 2008 R2 per MS09-061.

*Built at 2014-04-18T01:50:00Z-07:00*
