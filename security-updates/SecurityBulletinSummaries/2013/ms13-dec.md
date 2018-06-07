---
TOCTitle: 'MS13-DIC'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Dicembre 2013'
ms:assetid: 'ms13-dec'
ms:contentKeyID: 61240080
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-dec(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Riepilogo dei bollettini Microsoft sulla sicurezza - Dicembre 2013
==================================================================

Data di pubblicazione: 10 dicembre 2013

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in dicembre 2013.

Con il rilascio dei bollettini sulla sicurezza di dicembre 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 5 dicembre 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini l'11 dicembre 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i webcast dei bollettini sulla sicurezza di dicembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032557386&ampculture=en-us).

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
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>ID bollettino</strong></td>
<td style="border:1px solid black;"><strong>Titolo del bollettino e riepilogo</strong></td>
<td style="border:1px solid black;"><strong>Livello di gravità massimo e impatto della vulnerabilità</strong></td>
<td style="border:1px solid black;"><strong>Necessità di riavvio</strong></td>
<td style="border:1px solid black;"><strong>Software interessato</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344108">MS13-096</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel componente Microsoft Graphics può consentire l'esecuzione di codice in modalità remota (2908005)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows, Microsoft Office e Microsoft Lync. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza contenuto che include file TIFF appositamente predisposti.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft Office,<br />
Microsoft Lync</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2898785)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità in Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325389">MS13-098</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows può consentire l'esecuzione di codice in modalità remota (2893294)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente o un'applicazione esegue o installa un file firmato PE (Portable Executable) appositamente predisposto in un sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344112">MS13-099</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella libreria oggetti di Microsoft Scripting Runtime può consentire l'esecuzione di codice in modalità remota (2909158)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato convince un utente a visitare un sito Web appositamente predisposto o un sito Web che ospita contenuto appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329830">MS13-105</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Exchange Server possono consentire l'esecuzione di codice in modalità remota (2915705)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità divulgate pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Exchange Server. La più grave di tali vulnerabilità è presente nelle funzionalità WebReady Document Viewing e Data Loss Prevention di Microsoft Exchange Server. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota nel contesto di protezione dell'account Servizio locale se un utente malintenzionato invia un messaggio di posta elettronica che contiene un file appositamente predisposto a un utente su un server Exchange interessato. L'account LocalService dispone di privilegi minimi sul sistema locale e presenta credenziali anonime sulla rete.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Exchange</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329771">MS13-100</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft SharePoint Server possono consentire l'esecuzione di codice in modalità remota (2904244)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente nel software Microsoft Office Server. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente malintenzionato autenticato invia il contenuto di una pagina appositamente predisposta a un server SharePoint. Un utente malintenzionato che ha sfruttato con successo queste vulnerabilità può eseguire codice arbitrario nel contesto di protezione dell'account del servizio W3WP sul sito SharePoint di destinazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft SharePoint</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2880430)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di queste vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede a un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344110">MS13-102</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel client LRPC può consentire l'acquisizione di privilegi più elevati (2898715)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato simula un server LRPC e invia un messaggio di porta LPC appositamente predisposto a un client LRPC. Un utente malintenzionato in grado di sfruttare la vulnerabilità può quindi installare programmi, visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti di amministratore completi. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329969">MS13-103</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in ASP.NET SignalR può consentire l'acquisizione di privilegi più elevati (2905244)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in ASP.NET SignalR. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato visualizza codice JavaScript appositamente predisposto sul browser di un utente designato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Strumenti per gli sviluppatori Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=330934">MS13-104</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office può consentire l'intercettazione di informazioni personali (2909976)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Office che può consentire l'intercettazione di informazioni personali qualora un utente tenti di aprire un file di Office ospitato su un sito Web dannoso. Sfruttando questa vulnerabilità, un utente malintenzionato può venire a conoscenza di token di accesso utilizzati per autenticare l'utente corrente su un sito server SharePoint o un altro sito Microsoft Office designato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329967">MS13-106</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in un componente condiviso di Microsoft Office può consentire l'elusione della funzione di protezione<br />
(2905238)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in un componente condiviso di Microsoft Office attualmente sfruttata. La vulnerabilità può consentire l'elusione della funzione di protezione se un utente visualizza una pagina Web appositamente predisposta in un browser Web in grado di creare istanze di componenti COM, quale Internet Explorer. In uno scenario di attacco basato sull'esplorazione Web, un utente malintenzionato, sfruttando questa vulnerabilità, potrebbe eludere la funzione di protezione ASLR (Address Space Layout Randomization), che protegge gli utenti da un'ampia gamma di vulnerabilità. L'elusione della funzione di protezione non consente da sola l'esecuzione di codice arbitrario. Tuttavia, un utente malintenzionato potrebbe utilizzare questa vulnerabilità legata all'elusione di ASLR in combinazione con un'altra vulnerabilità, ad esempio l'esecuzione di codice in modalità remota, per trarre vantaggio dall'elusione della funzionalità ASLR ed eseguire codice arbitrario.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Elusione della funzione di protezione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
 
  
Exploitability Index  
--------------------
  
<span id="sectionToggle1"></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
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
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>ID bollettino</strong></td>
<td style="border:1px solid black;"><strong>Titolo della vulnerabilità</strong></td>
<td style="border:1px solid black;"><strong>ID CVE</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability per la versione più recente del software</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability per la versione meno recente del software</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</strong></td>
<td style="border:1px solid black;"><strong>Note fondamentali</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344108">MS13-096</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nel componente Microsoft Graphics</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3906">CVE-2013-3906</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità nei prodotti Microsoft Office.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5045">CVE-2013-5045</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5046">CVE-2013-5046</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5047">CVE-2013-5047</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5048">CVE-2013-5048</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5049">CVE-2013-5049</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5051">CVE-2013-5051</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344111">MS13-097</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5052">CVE-2013-5052</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325389">MS13-098</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida della firma mediante WinVerifyTrust</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3900">CVE-2013-3900</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344112">MS13-099</a></td>
<td style="border:1px solid black;">Vulnerabilità di tipo Use-After-Free nella libreria oggetti di Microsoft Scripting Runtime</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5056">CVE-2013-5056</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329771">MS13-100</a></td>
<td style="border:1px solid black;">Vulnerabilità legate ai contenuti delle pagine SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5059">CVE-2013-5059</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3899">CVE-2013-3899</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3902">CVE-2013-3902</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3903">CVE-2013-3903</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al doppio recupero del driver classe-porta</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3907">CVE-2013-3907</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325387">MS13-101</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5058">CVE-2013-5058</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=344110">MS13-102</a></td>
<td style="border:1px solid black;">Vulnerabilità di buffer overrun del client LRPC </td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3878">CVE-2013-3878</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329969">MS13-103</a></td>
<td style="border:1px solid black;">Vulnerabilità di tipo XSS in SignalR</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5042">CVE-2013-5042</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=330934">MS13-104</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'assunzione del controllo del token</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5054">CVE-2013-5054</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.<br />
<br />
Microsoft è a conoscenza di attacchi mirati limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329830">MS13-105</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla disattivazione di MAC</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1330">CVE-2013-1330</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329830">MS13-105</a></td>
<td style="border:1px solid black;">Oracle Outside In contiene più vulnerabilità sfruttabili</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5763">CVE-2013-5763</a><br />
<br />
e<br />
<br />
<a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5791">CVE-2013-5791</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Queste vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329830">MS13-105</a></td>
<td style="border:1px solid black;">Vulnerabilità XSS OWA</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5072">CVE-2013-5072</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329967">MS13-106</a></td>
<td style="border:1px solid black;">Vulnerabilità HXDS ASLR</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5057">CVE-2013-5057</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati limitati che tentano di sfruttare questa vulnerabilità.</td>
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

### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows XP**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2898785)  
(Critico)  
Internet Explorer 7   
(2898785)  
(Critico)  
Internet Explorer 8   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7  
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2893984)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2898715)  
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
Internet Explorer 6   
(2898785)  
(Critico)  
Internet Explorer 7   
(2898785)  
(Critico)  
Internet Explorer 8   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.6  
(2892076)  
(Critico)  
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2893984)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2898715)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows Server 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
Windows Server 2003 Service Pack 2

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2898785)  
(Moderato)  
Internet Explorer 7  
(2898785)  
(Importante)  
Internet Explorer 8  
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.6   
(2892076)  
(Critico)  
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2893984)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2898715)  
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
Internet Explorer 6   
(2898785)  
(Moderato)  
Internet Explorer 7  
(2898785)  
(Importante)  
Internet Explorer 8  
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.6   
(2892076)  
(Critico)  
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2893984)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2898715)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2898785)  
(Moderato)  
Internet Explorer 7  
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.6   
(2892076)  
(Critico)  
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2893984)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2898715)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows Vista**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
Windows Vista Service Pack 2  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2898785)  
(Critico)  
Internet Explorer 8  
(2898785)  
(Critico)  
Internet Explorer 9   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2893984)  
(Moderato)  
Windows Vista Service Pack 2  
(2887069)  
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
Windows Vista x64 Edition Service Pack 2  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2898785)  
(Critico)  
Internet Explorer 8  
(2898785)  
(Critico)  
Internet Explorer 9   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2893984)  
(Moderato)  
Windows Vista x64 Edition Service Pack 2  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows Server 2008**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2898785)  
(Importante)  
Internet Explorer 8  
(2898785)  
(Importante)  
Internet Explorer 9   
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2893984)  
(Moderato)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2887069)  
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
Windows Server 2008 per sistemi x64 Service Pack 2  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2898785)  
(Importante)  
Internet Explorer 8  
(2898785)  
(Importante)  
Internet Explorer 9   
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2893984)  
(Moderato)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2887069)  
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
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2893984)  
(Moderato)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows 7**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2898785)  
(Critico)  
Internet Explorer 9   
(2898785)  
(Critico)  
Internet Explorer 10   
(2898785)  
(Critico)  
Internet Explorer 11   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2893984)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2887069)  
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
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2898785)  
(Critico)  
Internet Explorer 9   
(2898785)  
(Critico)  
Internet Explorer 10   
(2898785)  
(Critico)  
Internet Explorer 11   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2893984)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows Server 2008 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2008 R2 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2898785)  
(Importante)  
Internet Explorer 9   
(2898785)  
(Importante)  
Internet Explorer 10   
(2898785)  
(Importante)  
Internet Explorer 11   
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2893984)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2887069)  
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
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2893984)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows 8 e Windows 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
**Nessuno**

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
Internet Explorer 10   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2893984)  
(Moderato)  
Windows 8 per sistemi a 32 bit  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi x64

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2893984)  
(Moderato)  
Windows 8 per sistemi x64  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows Server 2012 e Windows Server 2012 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2012

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2893984)  
(Moderato)  
Windows Server 2012  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2898785)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Windows RT e Windows RT 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT  
(2893984)  
(Moderato)  
Windows RT  
(2887069)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT 8.1

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2898785)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="7">
**Opzione di installazione Server Core**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-097**](http://go.microsoft.com/fwlink/?linkid=344111)

</td>
<td style="border:1px solid black;">
[**MS13-098**](http://go.microsoft.com/fwlink/?linkid=325389)

</td>
<td style="border:1px solid black;">
[**MS13-099**](http://go.microsoft.com/fwlink/?linkid=344112)

</td>
<td style="border:1px solid black;">
[**MS13-101**](http://go.microsoft.com/fwlink/?linkid=325387)

</td>
<td style="border:1px solid black;">
[**MS13-102**](http://go.microsoft.com/fwlink/?linkid=344110)

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2893984)  
(Moderato)

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
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2901674)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.7   
(2892075)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2893984)  
(Moderato)

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
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2893984)  
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
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

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
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(2893294)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Script 5.8   
(2892074)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(2893984)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
</table>
 
**Nota per MS13-096**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="4">
**Microsoft Office 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-104**](http://go.microsoft.com/fwlink/?linkid=330934)

</td>
<td style="border:1px solid black;">
[**MS13-106**](http://go.microsoft.com/fwlink/?linkid=329967)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3 (2850047)  
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
<td style="border:1px solid black;" colspan="4">
**Microsoft Office 2007**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-104**](http://go.microsoft.com/fwlink/?linkid=330934)

</td>
<td style="border:1px solid black;">
[**MS13-106**](http://go.microsoft.com/fwlink/?linkid=329967)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3  
(2817641)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3  
(2850022)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Microsoft Office 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-104**](http://go.microsoft.com/fwlink/?linkid=330934)

</td>
<td style="border:1px solid black;">
[**MS13-106**](http://go.microsoft.com/fwlink/?linkid=329967)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2817670)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2850016)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(2817670)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(2850016)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2817670)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2850016)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(2817670)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(2850016)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Microsoft Office 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-104**](http://go.microsoft.com/fwlink/?linkid=330934)

</td>
<td style="border:1px solid black;">
[**MS13-106**](http://go.microsoft.com/fwlink/?linkid=329967)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)  
(2850064)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)  
(2850064)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft Office 2013 RT  
(2850064)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Altro software Office**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

</td>
<td style="border:1px solid black;">
[**MS13-104**](http://go.microsoft.com/fwlink/?linkid=330934)

</td>
<td style="border:1px solid black;">
[**MS13-106**](http://go.microsoft.com/fwlink/?linkid=329967)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3

</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2817641)  
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
<td style="border:1px solid black;">
Microsoft Word Viewer

</td>
<td style="border:1px solid black;">
Microsoft Word Viewer  
(2850047)  
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
<td style="border:1px solid black;">
Microsoft Excel Viewer

</td>
<td style="border:1px solid black;">
Microsoft Excel Viewer  
(2817641)  
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
<td style="border:1px solid black;">
Microsoft PowerPoint 2010 Viewer Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft PowerPoint 2010 Viewer Service Pack 1  
(2817670)  
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
<td style="border:1px solid black;">
Microsoft PowerPoint 2010 Viewer Service Pack 2

</td>
<td style="border:1px solid black;">
Microsoft PowerPoint 2010 Viewer Service Pack 2  
(2817670)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
</table>
 
**Nota per MS13-096**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft SharePoint Server 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-105**](http://go.microsoft.com/fwlink/?linkid=329830)

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013 (coreserverloc)  
(2850058)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Exchange Server 2007**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-105**](http://go.microsoft.com/fwlink/?linkid=329830)

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2007 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Exchange Server 2007 Service Pack 3  
(2903911)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Exchange Server 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-105**](http://go.microsoft.com/fwlink/?linkid=329830)

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 2  
(2903903)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Exchange Server 2010 Service Pack 3  
(2905616)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Exchange Server 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-105**](http://go.microsoft.com/fwlink/?linkid=329830)

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
</tr>
<tr>
<td style="border:1px solid black;">
Aggiornamento cumulativo 2 di Microsoft Exchange Server 2013

</td>
<td style="border:1px solid black;">
Aggiornamento cumulativo 2 di Microsoft Exchange Server 2013  
(2880833)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Aggiornamento cumulativo 3 di Microsoft Exchange Server 2013

</td>
<td style="border:1px solid black;">
Aggiornamento cumulativo 3 di Microsoft Exchange Server 2013  
(2880833)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
</table>
 
**Nota per MS13-100**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

### Microsoft Office Services e Web Apps

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft SharePoint Server 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
Microsoft SharePoint Server 2010 Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft Business Productivity Servers  
(2553298)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Microsoft Business Productivity Servers  
(2553298)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft SharePoint Server 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
Microsoft SharePoint Server 2013

</td>
<td style="border:1px solid black;">
Microsoft Business Productivity Servers  
(2837629)  
(Importante)  
Excel Services  
(2837631)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office Web Apps 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-100**](http://go.microsoft.com/fwlink/?linkid=329771)

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
Microsoft Office Web Apps 2013

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2013  
(2910228)  
(Importante)

</td>
</tr>
</table>
 
**Nota per MS13-100**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

### Software e piattaforme delle comunicazioni Microsoft

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Lync 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

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
Microsoft Lync 2010 (32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (32 bit)  
(2899397)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64 bit)  
(2899397)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello utente)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello utente)  
(2899393)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)  
(2899395)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Lync 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-096**](http://go.microsoft.com/fwlink/?linkid=344108)

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
Microsoft Lync 2013 (32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2013 (32 bit)  
(2850057)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (32 bit)  
(2850057)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2013 (64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync 2013 (64 bit)  
(2850057)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013  
(64 bit)  
(2850057)  
(Importante)

</td>
</tr>
</table>
 
**Nota per MS13-096**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**ASP.NET**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-103**](http://go.microsoft.com/fwlink/?linkid=329969)

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
ASP.NET SignalR

</td>
<td style="border:1px solid black;">
ASP.NET SignalR 1.1.x   
(2903919)  
(Importante)  
ASP.NET SignalR 2.0.x   
(2903919)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Visual Studio Team Foundation Server**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS13-103**](http://go.microsoft.com/fwlink/?linkid=329969)

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
Microsoft Visual Studio Team Foundation Server 2013

</td>
<td style="border:1px solid black;">
Microsoft Visual Studio Team Foundation Server 2013   
(2903566)  
(Importante)

</td>
</tr>
</table>
 
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span id="sectionToggle3"></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

-   Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.
-   Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.
-   I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183). 

Ringraziamenti
--------------

<span id="sectionToggle4"></span>
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS13-096**

-   Haifei Li di McAfee Labs IPS Team per aver segnalato la vulnerabilità legata al danneggiamento della memoria nel componente Microsoft Graphics (CVE-2013-3906)

**MS13-097**

-   James Forshaw di Context Information Security per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer (CVE-2013-5045)
-   James Forshaw di Context Information Security per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer (CVE-2013-5046)
-   Abdul-Aziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-5047)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-5048)
-   Jose Antonio Vazquez Gonzalez, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-5049)
-   Atte Kettunen di [OUSPG](https://www.ee.oulu.fi/research/ouspg/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-5051)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-5052)
-   Alex Inführ per aver collaborato con noi alle modifiche al sistema di difesa del filtro XSS di Internet Explorer contenute in questo bollettino

**MS13-098**

-   Kingsoft Internet Security Center @ [Kingsoft Internet Security Software Co. Ltd](http://www.ijinshan.com/) per aver segnalato la vulnerabilità legata alla convalida della firma mediante WinVerifyTrust (CVE-2013-3900)

**MS13-101**

-   Renguang Yuan di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Win32k (CVE-2013-3899)
-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Win32k (CVE-2013-3899)
-   Ling Chuan Lee di [F13 Laboratory](http://www.f13-labs.net/) per aver segnalato la vulnerabilità legata all'analisi dei caratteri TrueType (CVE-2013-3903)
-   Nicolas Economou di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato la vulnerabilità legata all'overflow di valori integer in Win32k (CVE-2013-5058)

**MS13-102**

-   Renguang Yuan di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità di buffer overrun del client LRPC (CVE-2013-3878)

**MS13-104**

-   Noam Liran di [Adallom](http://www.adallom.com/) per aver segnalato la vulnerabilità legata all'assunzione del controllo del token (CVE-2013-5054)

**MS13-105**

-   [Minded Security](https://www.mindedsecurity.com/), per conto di [Criteo](http://www.criteo.com/), per aver segnalato la vulnerabilità XSS OWA (CVE-2013-5072)

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

-   V1.0 (10 dicembre 2013): Pubblicazione del riepilogo dei bollettini.

 

*Pagina generata 09-5-2014 17:27Z-07:00.*
