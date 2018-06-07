---
TOCTitle: 'MS13-MAY'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Maggio 2013'
ms:assetid: 'ms13-may'
ms:contentKeyID: 61240086
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-may(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Maggio 2013
================================================================

Data di pubblicazione: martedì 14 maggio 2013 | Aggiornamento: mercoledì 22 maggio 2013

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a maggio 2013.

Con il rilascio dei bollettini sulla sicurezza di maggio 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 maggio 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 15 maggio 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di maggio](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538728&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538728&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato**.

 
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2829530)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve undici vulnerabilità di Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299892">MS13-038</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento per la protezione di Internet Explorer (2847204)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Internet Explorer. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293363">MS13-039</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in HTTP.sys può consentire un attacco di tipo Denial of Service (2829254)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia un pacchetto HTTP appositamente predisposto ad un client o server Windows interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296485">MS13-040</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework possono consentire lo spoofing (2836440)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente e una vulnerabilità divulgata pubblicamente<strong></strong>relative a .NET Framework. La più grave delle vulnerabilità può consentire lo spoofing se un'applicazione .NET riceva un file XML appositamente predisposto. Sfruttando tale vulnerabilità, un utente malintenzionato può modificare i contenuti di un file XML senza annullare la convalida della firma del file e ottenere l'accesso alle funzioni endpoint come se fosse un utente autenticato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Spoofing</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293445">MS13-041</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Lync può consentire l'esecuzione di codice in modalità remota (2834695)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Lync. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato condivide contenuti appositamente predisposti, ad esempio un file o un programma, come presentazione in Lync o Communicator, quindi induce un utente ad accettare l'invito a visualizzare o condividere il contenuto presentabile. In tutti questi casi, non è possibile obbligare gli utenti a visualizzare o condividere il file o il programma controllati dall'utente malintenzionato. L'utente malintenzionato deve invece convincere gli utenti a compiere un'azione, in genere inducendoli ad accettare l'invito, in Lync o Communicator, a visualizzare o condividere il contenuto presentabile.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Lync</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Publisher possono consentire l'esecuzione di codice in modalità remota (2830397)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve undici vulnerabilità di Microsoft Office segnalate privatamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Publisher appositamente predisposto con una versione interessata di Microsoft Publisher. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287107">MS13-043</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Word può consentire l'esecuzione di codice in modalità remota (2830399)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice se un utente apre un file appositamente predisposto o visualizza in anteprima un messaggio di posta elettronica appositamente predisposto in una versione interessata del software di Microsoft Office. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293446">MS13-044</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Visio può consentire l'intercettazione di informazioni personali (2834692)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. Questa vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre un file di Visio appositamente predisposto. Si noti che questa vulnerabilità non consente a un utente malintenzionato di eseguire codice o acquisire direttamente diritti utente più elevati, ma può essere utilizzata per produrre informazioni utili al fine di compromettere ulteriormente il sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=280675">MS13-045</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Essentials può consentire l'intercettazione di informazioni personali (2813707)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Windows Essentials che è stata segnalata privatamente. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre Windows Writer utilizzando un URL appositamente predisposto. Un utente malintenzionato che ha sfruttato con successo la vulnerabilità potrebbe sovrascrivere le impostazioni proxy di Writer di Windows e sovrascrivere dei file accessibili all'utente sul sistema di destinazione. In uno scenario di attacco dal Web, un sito Web potrebbe contenere un collegamento appositamente predisposto per sfruttare questa vulnerabilità. Un utente malintenzionato dovrebbe convincere gli utenti a visitare il sito Web e aprire il collegamento appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows Essentials</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296427">MS13-046</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei</strong> <strong>driver in modalità kernel possono consentire l'acquisizione di privilegi più elevati (2840221)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale.</td>
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
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0811">CVE-2013-0811</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali dell'array JSON</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1297">CVE-2013-1297</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1306">CVE-2013-1306</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1307">CVE-2013-1307</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1308">CVE-2013-1308</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1309">CVE-2013-1309</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1310">CVE-2013-1310</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1311">CVE-2013-1311</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1312">CVE-2013-1312</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-2551">CVE-2013-2551</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=294283">MS13-037</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3140">CVE-2013-3140</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299892">MS13-038</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1347">CVE-2013-1347</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi che tentano di sfruttare questa vulnerabilità attraverso Internet Explorer 8.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293363">MS13-039</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service di HTTP.sys</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1305">CVE-2013- 1305</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296485">MS13-040</a></td>
<td style="border:1px solid black;">Vulnerabilità legata allo spoofing della firma digitale XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1336">CVE-2013-1336</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata allo spoofing.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296485">MS13-040</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione dell'autenticazione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1337">CVE-2013-1337</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293445">MS13-041</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota in Lync</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1302">CVE-2013-1302</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'allocazione di valori negativi in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1316">CVE-2013-1316</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1317">CVE-2013-1317</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ai puntatori di interfaccia danneggiati in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1318">CVE-2013-1318</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione dei valori restituiti in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1319">CVE-2013-1319</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di buffer in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1320">CVE-2013-1320</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida dei valori restituiti in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1321">CVE-2013-1321</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla verifica di intervalli non validi in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1322">CVE-2013-1322</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione dei valori NULL non corretti in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1323">CVE-2013-1323</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ai valori integer con segno</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1327">CVE-2013-1327</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione dei puntatori in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1328">CVE-2013-1328</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287106">MS13-042</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'underflow di buffer in Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1329">CVE-2013-1329</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=287107">MS13-043</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della forma di Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1335">CVE-2013- 1335</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293446">MS13-044</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione di entità esterne in XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1301">CVE-2013-1301</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=280675">MS13-045</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione URI errata in Windows Essentials</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0096">CVE-2013-0096</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296427">MS13-046</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al doppio recupero del sottosistema del kernel grafico DirectX</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1332">CVE-2013-1332</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296427">MS13-046</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1333">CVE-2013-1333</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296427">MS13-046</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione di finestre Win32K</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1334">CVE-2013-1334</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
</tbody>
</table>
  
Software interessato  
--------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma o componente elencato è riportato anche il livello di gravità dell'aggiornamento software.
  
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2829530)  
(Critico)  
Internet Explorer 7  
(2829530)  
(Critico)  
Internet Explorer 8  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804577)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2829361)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2829530)  
(Critico)  
Internet Explorer 7  
(2829530)  
(Critico)  
Internet Explorer 8  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804577)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2829361)  
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2829530)  
(Moderato)  
Internet Explorer 7  
(2829530)  
(Moderato)  
Internet Explorer 8  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804577)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2829530)  
(Moderato)  
Internet Explorer 7  
(2829530)  
(Moderato)  
Internet Explorer 8  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804577)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2829530)  
(Moderato)  
Internet Explorer 7  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804577)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2829361)  
(Nessuno livello di gravità)
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
**Nessuno**
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
Internet Explorer 7  
(2829530)  
(Critico)  
Internet Explorer 8  
(2829530)  
(Critico)  
Internet Explorer 9  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804580)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2830290)  
(Importante)  
Windows Vista Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2829530)  
(Critico)  
Internet Explorer 8  
(2829530)  
(Critico)  
Internet Explorer 9  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804580)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2830290)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2829530)  
(Moderato)  
Internet Explorer 8  
(2829530)  
(Moderato)  
Internet Explorer 9  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804580)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2830290)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2829530)  
(Moderato)  
Internet Explorer 8  
(2829530)  
(Moderato)  
Internet Explorer 9  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804580)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2830290)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2804580)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2830290)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2829361)  
(Nessuno livello di gravità)
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2829530)  
(Critico)  
Internet Explorer 9  
(2829530)  
(Critico)  
Internet Explorer 10  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2804579)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2830290)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2829361)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2829530)  
(Critico)  
Internet Explorer 9  
(2829530)  
(Critico)  
Internet Explorer 10  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Critico)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2804579)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2830290)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2829361)  
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2829530)  
(Moderato)  
Internet Explorer 9  
(2829530)  
(Moderato)  
Internet Explorer 10  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)  
Internet Explorer 9  
(2847204)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2804579)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2830290)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2847204)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2804579)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2830290)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<th colspan="6">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
**Nessuno**
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
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2829254)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2804584)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804583)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2830290)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2829254)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2804584)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804583)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2830290)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
**Nessuno**
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
Windows Server 2012
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2829530)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2829254)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2804584)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804583)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2830290)  
(Importante)  
Windows Server 2012  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<th colspan="6">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows RT
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2829530)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows RT  
(2829254)  
(Moderato)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5  
(2804583)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT  
(2830290)  
(Importante)  
Windows RT  
(2829361)  
(Nessuno livello di gravità)
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
[**MS13-037**](http://go.microsoft.com/fwlink/?linkid=294283)
</td>
<td style="border:1px solid black;">
[**MS13-038**](http://go.microsoft.com/fwlink/?linkid=299892)
</td>
<td style="border:1px solid black;">
[**MS13-039**](http://go.microsoft.com/fwlink/?linkid=293363)
</td>
<td style="border:1px solid black;">
[**MS13-040**](http://go.microsoft.com/fwlink/?linkid=296485)
</td>
<td style="border:1px solid black;">
[**MS13-046**](http://go.microsoft.com/fwlink/?linkid=296427)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2830290)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2830290)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2829361)  
(Nessuno livello di gravità)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2804579)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2804576)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804582)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2830290)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
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
(2829254)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2804584)  
(Importante)  
Microsoft .NET Framework 4.5  
(2804583)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2830290)  
(Importante)  
Windows Server 2012 (installazione Server Core)  
(2829361)  
(Nessuno livello di gravità)
</td>
</tr>
</table>
 
**Nota per MS13-040**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-042**](http://go.microsoft.com/fwlink/?linkid=287106)
</td>
<td style="border:1px solid black;">
[**MS13-043**](http://go.microsoft.com/fwlink/?linkid=287107)
</td>
<td style="border:1px solid black;">
[**MS13-044**](http://go.microsoft.com/fwlink/?linkid=293446)
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
Microsoft Publisher 2003 Service Pack 3  
(2810047)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Word 2003 Service Pack 3  
(2810046)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Publisher 2007 Service Pack 3  
(2597971)  
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
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Publisher 2010 Service Pack 1 (edizioni a 32 bit)  
(2553147)  
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
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Publisher 2010 Service Pack 1 (edizioni a 64 bit)  
(2553147)  
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
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Word Viewer  
(2817361)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Visio 2003 Service Pack 3  
(2810062)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Visio 2007 Service Pack 3  
(2596595)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 32 bit)  
(2810068)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 64 bit)  
(2810068)  
(Importante)
</td>
</tr>
</table>
 

#### Software e piattaforme delle comunicazioni Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Lync
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-041**](http://go.microsoft.com/fwlink/?linkid=293445)
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
Microsoft Communicator 2007 R2
</td>
<td style="border:1px solid black;">
Microsoft Communicator 2007 R2  
(2827753)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 (32-bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (32-bit)  
(2827750)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64-bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64-bit)  
(2827750)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)  
(2827752)  
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
(2827751)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync Server 2013  
(Web Components Server)
</td>
<td style="border:1px solid black;">
Microsoft Lync Server 2013  
(Web Components Server)  
(2827754)  
(Importante)
</td>
</tr>
</table>
 

#### Strumenti e software Microsoft per gli utenti

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Windows Essentials
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-045**](http://go.microsoft.com/fwlink/?linkid=280675)
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
Windows Essentials 2011
</td>
<td style="border:1px solid black;">
Windows Essentials 2011  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Essentials 2012
</td>
<td style="border:1px solid black;">
Windows Essentials 2012  
(2813707)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS13-001"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, vedere [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/default).

**SystemCenter Configuration Manager**

Gestione aggiornamenti software di System Center Configuration Manager semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con System Center Configuration Manager, gli amministratori IT possono distribuire gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in System Center Configuration Manager rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. Gestione aggiornamenti software di System Center Configuration Manager si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni su System Center Configuration Manager, visitare il sito [Risorse tecniche di System Center](http://technet.microsoft.com/systemcenter/bb980621).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager; vedere anche la sezione precedente, **System Center Configuration Manager**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/systemcenter/bb545936).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc749197), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Per il rilascio dei bollettini che avviene il secondo martedì di ogni mese, Microsoft ha rilasciato una versione aggiornata dello Strumento di rimozione software dannoso di Microsoft Windows in Windows Update, Microsoft Update, Windows Server Update Services e nell'Area download. Non è disponibile alcuna versione dello Strumento di rimozione software dannoso di Microsoft Windows per i rilasci di bollettini sulla sicurezza straordinari.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS13-037**

-   Jose Antonio Vazquez Gonzalez, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-0811)
-   Yosuke Hasegawa e Masahiro Yamada per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali nell'array JSON (CVE-2013-1297)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1306)
-   Scott Bell di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1306)
-   Ivan Fratric di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1307)
-   [Aniway.Aniway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1308)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1309)
-   Yuhong Bao per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1310)
-   Scott Bell di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1311)
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1312)
-   [VUPEN Security](http://www.vupen.com) (Pwn2Own 2013), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità di tipo use-after-free in Internet Explorer (CVE-2013-2551)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-3140)
-   Masato Kinugawa per aver collaborato con noi alle modifiche al sistema di difesa contenute in questo bollettino
-   [VUPEN Security](http://www.vupen.com) (Pwn2Own 2013), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver collaborato con noi alle modifiche al sistema di difesa contenute in questo bollettino

**MS13-038**

-   Daniel Caselden di [FireEye](http://www.fireeye.com/) per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1347)
-   [iSIGHT Partners](http://www.isightpartners.com/) per aver collaborato con Microsoft sulla vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-1347)

**MS13-039**

-   Marek Kroemeke, 22733db72ab3ed94b5f8a1ffcde850251fe6f466, AKAT-1 che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità ad attacchi di tipo Denial of Service di HTTP.sys (CVE-2013-1305)

**MS13-040**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata allo spoofing della firma digitale XML (CVE-2013-1336)

**MS13-042**

-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver collaborato con noi alle varie vulnerabilità legate all'esecuzione di codice in modalità remota in Microsoft Publisher (CVE-2013-1316, CVE-2013-1317, CVE-2013-1318, CVE-2013-1319, CVE-2013-1320, CVE-2013-1321, CVE-2013-1322, CVE-2013-1323, CVE-2013-1327, CVE-2013-1328, e CVE-2013-1329)

**MS13-043**

-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato una vulnerabilità legata al danneggiamento della forma di Word (CVE-2013-1335)

**MS13-044**

-   Timur Yunusov di [Positive Technologies](http://www.ptsecurity.com/) per aver segnalato la vulnerabilità legata alla risoluzione delle entità XML esterne (CVE-2013-1301)

**MS13-045**

-   Andrea Micalizzi, che collabora con il team [SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html) di Beyond Security, per aver segnalato la vulnerabilità legata alla gestione non corretta di URI in Windows Essentials (CVE-2013-0096)

**MS13-046**

-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al doppio recupero del sottosistema del kernel grafico DirectX (CVE-2013-1332)
-   [Qihoo 360 Security Center](http://www.360.cn/) per aver segnalato la vulnerabilità legata al sovraccarico del buffer Win32k (CVE-2013-1333)
-   Un ricercatore anonimo, che collabora con [iDefense VCP](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata alla gestione della finestra Win32k (CVE-2013-1334)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 maggio 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (22 maggio 2013): Per MS13-037, è stato corretto il numero di vulnerabilità ed esposizione ai rischi comuni CVE-2013-3140. La modifica è esclusivamente informativa.

*Built at 2014-04-18T01:50:00Z-07:00*
