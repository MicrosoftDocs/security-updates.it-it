---
TOCTitle: 'MS14-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza, ottobre 2014'
ms:assetid: 'ms14-oct'
ms:contentKeyID: 63172025
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms14-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Riepilogo dei bollettini Microsoft sulla sicurezza, ottobre 2014
================================================================

Data di pubblicazione: 14 ottobre 2014

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a ottobre 2014.

Con il rilascio dei bollettini sulla sicurezza di ottobre 2014, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 ottobre 2014. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 15 ottobre 2014 alle 11:00 ora del Pacifico (USA e Canada). Per visualizzare il webcast mensile e per collegamenti a webcast aggiuntivi dei bollettini sulla sicurezza, vedere [Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/dn756352).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2987107)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattordici vulnerabilità in Internet Explorer segnalate privatamente. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513095">MS14-057</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework possono consentire l'esecuzione di codice in modalità remota (3000414)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft .NET Framework. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia una richiesta URI contenente caratteri internazionali a un'applicazione Web .NET. Nelle applicazioni .NET 4.0, la funzionalità vulnerabile (iriParsing) è disattivata per impostazione predefinita; per sfruttare la vulnerabilità, è necessario che un'applicazione attivi esplicitamente questa funzionalità. Nelle applicazioni .NET 4.5, l'opzione iriParsing è abilitata per impostazione predefinita e non può essere disabilitata.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513104">MS14-058</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei driver in modalità kernel può consentire l'esecuzione di codice in modalità remota (3000061)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato riesce a convincere un utente ad aprire un documento appositamente predisposto o a visitare un sito Web che contiene caratteri TrueType incorporati. In tutti questi casi, comunque, non è in alcun modo possibile obbligare gli utenti ad eseguire queste azioni. L'utente malintenzionato dovrebbe convincere gli utenti ad aprire il file, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507673">MS14-059</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in ASP.NET MVC può consentire l'elusione della funzione di protezione (2990942)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di ASP.NET MVC. La vulnerabilità può consentire l'elusione della funzione di protezione se un utente malintenzionato riesce a convincere un utente a fare clic su un collegamento appositamente predisposto o a visitare una pagina Web con contenuto appositamente predisposto per sfruttare la vulnerabilità. In uno scenario di attacco dal Web, un utente malintenzionato potrebbe pubblicare un sito Web predisposto per sfruttare tale vulnerabilità tramite un browser Web, e convincere un utente a visualizzarlo. L'utente malintenzionato può inoltre servirsi di siti Web manomessi e di siti Web che accettano o pubblicano contenuti o annunci pubblicitari inviati da altri utenti. Questi siti Web possono includere contenuti appositamente predisposti in grado di sfruttare la vulnerabilità. Tuttavia, in nessuno di questi casi un utente malintenzionato può obbligare gli utenti a visualizzare il contenuto controllato dall'utente malintenzionato. L'utente malintenzionato deve invece convincere gli utenti a compiere un'azione, in genere inducendoli a fare clic su un collegamento contenuto in un messaggio di posta elettronica o in un messaggio di Instant Messenger che li reindirizza al sito Web dell'utente malintenzionato oppure ad aprire un allegato inviato mediante un messaggio di posta elettronica.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Elusione della funzione di protezione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Strumenti per gli sviluppatori Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513097">MS14-060</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows OLE può consentire l'esecuzione di codice in modalità remota (3000869)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file Microsoft Office che contiene un oggetto OLE appositamente predisposto. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può eseguire codice arbitrario nel contesto dell'utente corrente. Se l'utente corrente è connesso con privilegi di amministrazione, l'utente malintenzionato riuscirebbe quindi a installare programmi o a visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513106">MS14-061</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità in Microsoft Word e nelle applicazioni Web di Office può consentire l'esecuzione di codice in modalità remota (3000434)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota nel caso in cui un utente malintenzionato riesce a convincere un utente ad aprire un file di Microsoft Word appositamente predisposto. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Se l'utente corrente è connesso con privilegi di amministrazione, l'utente malintenzionato riuscirebbe quindi a installare programmi o a visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Microsoft Office Services,<br />
Microsoft Office Web Apps</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513107">MS14-062</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Accodamento messaggi può consentire l'acquisizione di privilegi più elevati (2993254)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato invia una richiesta di controllo input/output (IOCTL) appositamente predisposta al servizio di Accodamento messaggi. Lo sfruttamento di questa vulnerabilità può portare ad un accesso completo al sistema interessato. Per impostazione predefinita, il componente Accodamento messaggi non è installato nell'edizione interessata del sistema operativo e può essere attivato solo da un utente con privilegi amministrativi. Sono pertanto esposti a questa vulnerabilità solo i clienti che attivano manualmente il componente Accodamento messaggi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513102">MS14-063</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel driver di partizione del disco FAT32 può consentire l'acquisizione di privilegi più elevati (2998579)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Esiste una vulnerabilità relativa all'acquisizione di privilegi più elevati nel modo in cui il driver di sistema Windows FASTFAT interagisce con le partizioni del disco FAT32. Sfruttando questa vulnerabilità, un utente malintenzionato può eseguire codice arbitrario con privilegi elevati.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
 
  
Exploitability Index  
--------------------
  
<span id="sectionToggle1"></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colonne seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4123">CVE-2014-4123</a></td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati tramite l'elusione del sandbox di IE.<br />
<br />
Microsoft è a conoscenza di attacchi limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4124">CVE-2014-4124</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4126">CVE-2014-4126</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4127">CVE-2014-4127</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4128">CVE-2014-4128</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4129">CVE-2014-4129</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4130">CVE-2014-4130</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4132">CVE-2014-4132</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4133">CVE-2014-4133</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4134">CVE-2014-4134</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4137">CVE-2014-4137</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4138">CVE-2014-4138</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione di ASLR in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4140">CVE-2014-4140</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513092">MS14-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4141">CVE-2014-4141</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513095">MS14-057</a></td>
<td style="border:1px solid black;">Vulnerabilità relativa all'acquisizione di privilegi più elevati in .NET ClickOnce</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4073">CVE-2014-4073</a></td>
<td style="border:1px solid black;">2 - Sfruttamento meno probabile</td>
<td style="border:1px solid black;">2 - Sfruttamento meno probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513095">MS14-057</a></td>
<td style="border:1px solid black;">Vulnerabilità relativa all'esecuzione di codice in modalità remota in .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4121">CVE-2014-4121</a></td>
<td style="border:1px solid black;">2 - Sfruttamento meno probabile</td>
<td style="border:1px solid black;">2 - Sfruttamento meno probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513095">MS14-057</a></td>
<td style="border:1px solid black;">Vulnerabilità ASLR in .NET</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4122">CVE-2014-4122</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513104">MS14-058</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k.sys</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4113">CVE-2014-4113</a></td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati.<br />
<br />
Microsoft è a conoscenza di attacchi limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513104">MS14-058</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota durante l'analisi di caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4148">CVE-2014 -4148</a></td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507673">MS14-059</a></td>
<td style="border:1px solid black;">Vulnerabilità XSS in MVC</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4075">CVE-2014-4075</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513097">MS14-060</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota in Windows OLE</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4114">CVE-2014-4114</a></td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513106">MS14-061</a></td>
<td style="border:1px solid black;">Vulnerabilità relativa al formato di file Microsoft Word </td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4117">CVE-2014-4117</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513107">MS14-062</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi di scrittura arbitraria MQAC</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4971">CVE-2014-4971</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=513102">MS14-063</a></td>
<td style="border:1px solid black;">Vulnerabilità relativa all'acquisizione di privilegi più elevati nel driver della partizione del disco Microsoft Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4115">CVE-2014-4115</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">2 - Sfruttamento meno probabile</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati.</td>
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
**Windows Server 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
**Nessuno**

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
Internet Explorer 6  
(2987107)  
(Moderato)  
Internet Explorer 7  
(2987107)  
(Moderato)  
Internet Explorer 8  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2972105)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979574)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2993254)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2998579)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2987107)  
(Moderato)  
Internet Explorer 7  
(2987107)  
(Moderato)  
Internet Explorer 8  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2972105)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979574)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2993254)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2998579)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium

</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2987107)  
(Moderato)  
Internet Explorer 7  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2972105)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979574)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2993254)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2998579)  
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
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
**Nessuno**

</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2987107)  
(Critico)  
Internet Explorer 8  
(2987107)  
(Critico)  
Internet Explorer 9  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2968292)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972098)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979568)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(3000869)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2998579)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2987107)  
(Critico)  
Internet Explorer 8  
(2987107)  
(Critico)  
Internet Explorer 9  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2968292)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972098)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979568)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(3000869)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2998579)  
(Importante)

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
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2987107)  
(Moderato)  
Internet Explorer 8  
(2987107)  
(Moderato)  
Internet Explorer 9  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2968292)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972098)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979568)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(3000869)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2998579)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2987107)  
(Moderato)  
Internet Explorer 8  
(2987107)  
(Moderato)  
Internet Explorer 9  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2968292)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972098)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979568)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(3000869)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2998579)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2968292)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972098)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2979568)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(3000869)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2998579)  
(Importante)

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
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
**Nessuno**

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
Internet Explorer 8  
(2987107)  
(Critico)  
Internet Explorer 9  
(2987107)  
(Critico)  
Internet Explorer 10  
(2987107)  
(Critico)  
Internet Explorer 11  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2968294)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2972100)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2979570)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(3000869)  
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
Windows 7 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2987107)  
(Critico)  
Internet Explorer 9  
(2987107)  
(Critico)  
Internet Explorer 10  
(2987107)  
(Critico)  
Internet Explorer 11  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2968294)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2972100)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2979570)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(3000869)  
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
<td style="border:1px solid black;" colspan="7">
**Windows Server 2008 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2008 R2 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2987107)  
(Moderato)  
Internet Explorer 9  
(2987107)  
(Moderato)  
Internet Explorer 10  
(2987107)  
(Moderato)  
Internet Explorer 11  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2968294)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2972100)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2979570)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(3000869)  
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
Windows Server 2008 R2 per sistemi Itanium Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2968294)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2972100)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2979570)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(3000869)  
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
<td style="border:1px solid black;" colspan="7">
**Windows 8 e Windows 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
**Nessuno**

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
Internet Explorer 10  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968295)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972101)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979571)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2978042)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979577)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(3000869)  
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
Windows 8 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968295)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972101)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979571)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2978042)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979577)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(3000869)  
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
Windows 8.1 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968296)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972103)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979573)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2978041)  
(Critico)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2979576)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(3000869)  
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
Windows 8.1 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968296)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972103)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979573)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2978041)  
(Critico)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2979576)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(3000869)  
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
<td style="border:1px solid black;" colspan="7">
**Windows Server 2012 e Windows Server 2012 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2012

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968295)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972101)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979571)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2978042)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979577)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(3000869)  
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
Windows Server 2012 R2

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2987107)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968296)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972103)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979573)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2978041)  
(Critico)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2979576)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(3000869)  
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
<td style="border:1px solid black;" colspan="7">
**Windows RT e Windows RT 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
**Nessuno**

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
Internet Explorer 10  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2978042)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979577)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows RT  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT  
(3000869)  
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
Windows RT 8.1

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2987107)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5.1/4.5.2  
(2978041)  
(Critico)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2979576)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(3000869)  
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
<td style="border:1px solid black;" colspan="7">
**Opzione di installazione Server Core**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-056**](http://go.microsoft.com/fwlink/?linkid=513092)

</td>
<td style="border:1px solid black;">
[**MS14-057**](http://go.microsoft.com/fwlink/?linkid=513095)

</td>
<td style="border:1px solid black;">
[**MS14-058**](http://go.microsoft.com/fwlink/?linkid=513104)

</td>
<td style="border:1px solid black;">
[**MS14-060**](http://go.microsoft.com/fwlink/?linkid=513097)

</td>
<td style="border:1px solid black;">
[**MS14-062**](http://go.microsoft.com/fwlink/?linkid=513107)

</td>
<td style="border:1px solid black;">
[**MS14-063**](http://go.microsoft.com/fwlink/?linkid=513102)

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2998579)  
(Importante)

</td>
</tr>
<tr>
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
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(3000061)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2998579)  
(Importante)

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
Microsoft .NET Framework 3.5.1  
(2968294)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2972100)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2979570)  
(Importante)  
Microsoft .NET Framework 4  
(2972106)  
(Critico)  
Microsoft .NET Framework 4  
(2979575)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972107)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979578)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(3000061)  
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968295)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972101)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979571)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2978042)  
(Critico)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2979577)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(3000061)  
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2968296)  
(Importante)  
Microsoft .NET Framework 3.5  
(2972103)  
(Critico)  
Microsoft .NET Framework 3.5  
(2979573)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2978041)  
(Critico)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2979576)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(3000061)  
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
</tr>
</table>
 
 

### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**ASP.NET MVC**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-059**](http://go.microsoft.com/fwlink/?linkid=507673)

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
ASP.NET MVC 2.0

</td>
<td style="border:1px solid black;">
ASP.NET MVC 2.0  
(2993939)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
ASP.NET MVC 3.0

</td>
<td style="border:1px solid black;">
ASP.NET MVC 3.0  
(2993937)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
ASP.NET MVC 4.0

</td>
<td style="border:1px solid black;">
ASP.NET MVC 4.0  
(2993928)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
ASP.NET MVC 5.0

</td>
<td style="border:1px solid black;">
ASP.NET MVC 5.0  
(2992080)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
ASP.NET MVC 5.1

</td>
<td style="border:1px solid black;">
ASP.NET MVC 5.1  
(2994397)  
(Importante)

</td>
</tr>
</table>
 
 

### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office 2007**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Microsoft Office 2007 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3  
(2883031)  
(Importante)  
Microsoft Word 2007 Service Pack 3  
(2883032)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2883008)  
(Importante)  
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2883013)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(2883008)  
(Importante)  
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2883013)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2883008)  
(Importante)  
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2883013)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(2883008)  
(Importante)  
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2883013)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office per Mac**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Microsoft Office per Mac 2011

</td>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011  
(3004865)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Altro software Office**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Pacchetto di compatibilità Microsoft Office Service Pack 3

</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2883031)  
(Importante)

</td>
</tr>
</table>
 
**Nota per MS14-061**

Questi bollettini occupano più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

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
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Word Automation Services  
(2883098)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Word Automation Services  
(2883098)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office Web Apps 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-061**](http://go.microsoft.com/fwlink/?linkid=513106)

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
Microsoft Office Web Apps 2010

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2010  
(2889827)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2010 Service Pack 1  
(2889827)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2010 Service Pack 2  
(2889827)  
(Importante)

</td>
</tr>
</table>
 
**Nota per MS14-061**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span id="sectionToggle3"></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.

Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.

I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183). 

Ringraziamenti
--------------

<span id="sectionToggle4"></span>
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS14-056**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer (CVE-2014-4123)
-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in Internet Explorer (CVE-2014-4124)
-   Rohit Mothe, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4126)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4127)
-   Omair, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4128)
-   Jason Kratzer per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4128)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4129)
-   Sky, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4130)
-   Zhibin Hu di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4132)
-   José A. Vázquez di Yenteasy - Security Research, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4132)
-   Zhibin Hu di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4133)
-   Zhibin Hu di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4134)
-   Liu Long di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4137)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4138)
-   John Villamil (@day6reak) per aver segnalato la vulnerabilità legata all'elusione di ASLR in Internet Explorer (CVE-2014-4140)
-   Peter 'corelanc0d3r' Van Eeckhoutte di [Corelan](http://www.corelangcv.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4141)

**MS14-057**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in .NET ClickOnce (CVE-2014-4073)

**MS14-058**

-   [CrowdStrike Intelligence Team](http://www.crowdstrike.com/) per aver collaborato con noi sulla vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k.sys (CVE-2014-4113)
-   [FireEye, Inc.](http://www.fireeye.com/) per aver collaborato con noi sulla vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k.sys (CVE-2014-4113)
-   [FireEye, Inc.](http://www.fireeye.com/) per aver collaborato con noi sulla vulnerabilità legata all'acquisizione di privilegi più elevati durante l'analisi dei caratteri TrueType (CVE-2014-4148)

**MS14-060**

-   [iSIGHT Partners](http://www.isightpartners.com/) per aver segnalato la vulnerabilità relativa all'esecuzione del codice in modalità remota in OLE Windows (CVE-2014-4114)

**MS14-061**

-   3S Labs, in collaborazione con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità relativa al formato di file Microsoft Word (CVE-2014-4117)

**MS14-063**

-   Marcin 'Icewall' Noga di [Cisco Talos](http://www.sourcefire.com/solutions/research) per aver segnalato la vulnerabilità relativa all'acquisizione di privilegi più elevati nel driver della partizione disco Windows (CVE-2014-4115)

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

-   V1.0 (14 ottobre 2014): Pubblicazione del riepilogo dei bollettini.

*Pagina generata 13-10-2014 14:39Z-07:00.*
