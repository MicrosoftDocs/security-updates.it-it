---
TOCTitle: 'MS10-APR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - aprile 2010'
ms:assetid: 'ms10-apr'
ms:contentKeyID: 61240042
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-apr(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - aprile 2010
================================================================

Data di pubblicazione: martedì 13 aprile 2010 | Aggiornamento: martedì 13 luglio 2010

**Versione:** 4.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati ad aprile 2010.

Con il rilascio dei bollettini del mese di aprile 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente l'8 aprile 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 14 aprile 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di aprile](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032427721&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-019">MS10-019</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Windows possono consentire l'esecuzione di codice in modalità remota (981210)</strong><br />
<br />
Questo aggiornamento risolve due vulnerabilità segnalate privatamente nella verifica Authenticode di Windows che possono consentire l'esecuzione di codice in modalità remota. Sfruttando queste vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel client SMB possono consentire l'esecuzione di codice in modalità remota (980232)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e diverse vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ha inviato una risposta SMB appositamente predisposta ad una richiesta SMB avviata dal client. Per sfruttare queste vulnerabilità, un utente malintenzionato deve convincere l'utente ad avviare una connessione SMB a un server SMB appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-025">MS10-025</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei Servizi Microsoft Windows Media può consentire l'esecuzione di codice in modalità remota (980858)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nei Servizi Windows Media in esecuzione su Microsoft Windows 2000 Server. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia un pacchetto con informazioni di trasporto appositamente predisposto a un sistema Microsoft Windows 2000 Server che esegue i Servizi Windows Media. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte. I Servizi Windows Media rappresentano un componente facoltativo di Microsoft Windows 2000 Server e non sono installati per impostazione predefinita.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-026">MS10-026</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel codec MPEG Layer-3 Microsoft può consentire l'esecuzione di codice in modalità remota (977816)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità dei codec audio MPEG Layer-3 Microsoft che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file AVI appositamente predisposto che contiene un flusso audio MPEG Layer-3. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-027">MS10-027</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Windows Media Player può consentire l'esecuzione di codice in modalità remota (979402)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Windows Media Player che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se Windows Media Player apre contenuti multimediali appositamente predisposti ospitati su un sito Web dannoso. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-021">MS10-021</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (979683)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente in Microsoft Windows. La più grave delle vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso localmente ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-022">MS10-022</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in VBScript può consentire l'esecuzione di codice in modalità remota (981169)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in VBScript su Microsoft Windows che può consentire l'esecuzione di codice in modalità remota. Questo aggiornamento per la protezione è considerato di livello importante per Microsoft Windows 2000, Windows XP e Windows Server 2003. Su Windows Server 2008, Windows Vista, Windows 7 e Windows Server 2008 R2, non è possibile sfruttare il codice vulnerabile. Tuttavia, poiché il codice è presente, questo aggiornamento funge da sistema di difesa e non presenta alcun livello di gravità.<br />
<br />
La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un sito Web dannoso visualizza una finestra di dialogo appositamente predisposta ed un utente preme il tasto F1, il che causa l'avvio della Guida di Windows con un file creato specificatamente dall'utente malintenzionato. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-023">MS10-023</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Office Publisher può consentire l'esecuzione di codice in modalità remota (981160)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Office Publisher che può consentire l'esecuzione di codice in modalità remota se un utente apre un file Publisher appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-024">MS10-024</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Exchange e del servizio SMTP di Windows possono consentire un attacco di tipo Denial of Service (981832)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Exchange e nel servizio SMTP di Windows. La più grave di tali vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia una risposta DNS appositamente predisposta a un computer che esegue il servizio SMTP. Per impostazione predefinita, il componente SMTP non è installato in Windows Server 2003, Windows Server 2003 x64 Edition o Windows XP Professional x64 Edition.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft Exchange</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-028">MS10-028</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Visio possono consentire l'esecuzione di codice in modalità remota (980094)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Office Visio. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-029">MS10-029</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel componente Windows ISATAP possono consentire attacchi di spoofing (978338)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Questo aggiornamento per la protezione è considerato di livello moderato per Windows XP, Windows Server 2003, Windows Vista e Windows Server 2008. Windows 7 e Windows Server 2008 R2 non sono vulnerabili poiché questi sistemi operativi includono la funzionalità distribuita da questo aggiornamento per la protezione.<br />
<br />
Questa vulnerabilità può consentire a un utente malintenzionato di accedere a un indirizzo IPv4 tramite spoofing ignorando i dispositivi di filtraggio che si basano sull'indirizzo IPv4 di origine. L'aggiornamento per la protezione risolve la vulnerabilità modificando il modo in cui lo stack TCP/IP di Windows controlla l'indirizzo IPv6 di origine in un pacchetto ISATAP con tunnel.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Moderato</a><br />
Spoofing</td>
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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-021">MS10-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'allocazione della memoria del kernel di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0236">CVE-2010-0236</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-021">MS10-021</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla creazione del collegamento simbolico del kernel di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0237">CVE-2010-0237</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-028">MS10-028</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria di convalida attributo Visio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0254">CVE-2010-0254</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-027">MS10-027</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota di Media Player</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0268">CVE-2010-0268</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-025">MS10-025</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer basato su stack dei servizi Windows Media</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0478">CVE-2010-0478</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-023">MS10-023</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer nell'elaborazione della casella di testo di conversione file di Microsoft Office Publisher</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0479">CVE-2010-0479</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-026">MS10-026</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow dello stack del decodificatore audio MPEG Layer-3</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0480">CVE-2010-0480</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-022">MS10-022</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla pressione del tasto per la Guida di VBScript</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0483">CVE-2010-0483</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità<br />
<br />
Per Windows Server 2008, Windows 7 e Windows Server 2008 R2:<br />
<a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Questa vulnerabilità è stata segnalata pubblicamente, come descritto nell'<a href="http://technet.microsoft.com/security/advisory/981169">Advisory Microsoft sulla sicurezza 981169</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-028">MS10-028</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria di calcolo dell'indice Visio</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0256">CVE-2010-0256</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla transazione del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0270">CVE-2010-0270</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi della risposta del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0476">CVE-2010-0476</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-019">MS10-019</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida della firma mediante WinVerifyTrust</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0486">CVE-2010-0486</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-019">MS10-019</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla convalida di Cabview corrotto</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0487">CVE-2010-0487</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risposta incompleta del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3676">CVE-2009-3676</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Questa vulnerabilità è stata segnalata pubblicamente, come descritto nell'<a href="http://technet.microsoft.com/security/advisory/977544">Advisory Microsoft sulla sicurezza 977544</a>.<br />
<br />
L'impatto probabile è un attacco di tipo Denial of Service.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-024">MS10-024</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al record MX del server SMTP</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0024">CVE-2010-0024</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">L'impatto probabile è un attacco di tipo Denial of Service</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'allocazione della memoria del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0269">CVE-2010-0269</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-020">MS10-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alle dimensioni del messaggio del client SMB</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0477">CVE-2010-0477</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">L'impatto probabile è un attacco di tipo Denial of Service</td>
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
</tr>
<tr>
<th colspan="10">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=d7538166-35ee-4c6b-be8c-e83a1fc6cd77)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=13846177-f25f-4dd4-9fe9-ac43e1d4d73d)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=67ccac04-e5c8-4381-9d1a-9b676dd516a6)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=73b3d681-26bb-49c1-849e-1f72484cb978)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=f6394fc2-b9d0-46cf-9265-a0d4aeb1448f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=c0b8b362-a321-4ac9-be98-15c71bb7a043)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=c5f4577e-7546-40e9-8bcd-be11c1b260a6)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=421be318-f217-4d12-b7a5-833093189073)<sup>[1]</sup>
(KB981350)  
(Importante)  
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=421be318-f217-4d12-b7a5-833093189073)  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=d5fc47a4-cecb-4817-aafb-45f335061be3)  
(KB981349)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=88a0e872-01de-495b-8eec-d105a970daa7)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="10">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=2a01ddf0-f3ea-47c8-ada2-e69f6c1b5f96)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=6c3ac102-2107-4726-98be-4fbf6b858bfb)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=dec38c02-3d4a-41c5-8954-e57f56b8fa5b)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=b1582a74-4a7b-4540-beb1-7c89c86eae87)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 9 Series per Windows XP Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5c748c6d-84d1-45a9-8a33-9372eb5504d5)  
(Critico)  
[Windows Media Player 9 Series per Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9e4277b4-2dc5-4163-a6aa-7e07dd32b721)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=142710fd-9cd4-4dd0-aaba-2aace03c008f)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=aa8ff157-a7b3-4787-80c9-5bc453f0f1c9) in Windows XP Service Pack 2  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=cb21d276-65e9-4c8f-96e3-cf6dc36d0133)  
(KB981349)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=ba7ef6e5-80ba-4281-a611-6e5be008c1b4)  
(KB981332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=de447b76-ec89-426b-ac54-3ae3855d1159)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9dc3e1c2-2e9d-4d86-9fce-446c409ad613)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=9bbff00c-f8f4-4a44-98f2-18a868986ae1)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e64e487e-2727-4396-b0c9-6eaf000214d2)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c5a21239-a9a3-4ec5-9de8-7d2fc16fc6b8)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=8afca317-a647-44aa-a771-5d85cd5d62ea)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3c0cb02e-3484-4cdf-8c64-c697ad3e2889)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=896c738d-4058-440f-8d4f-16c678610cd1)  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=d7e8b930-8708-4f0b-b22b-961c2cbc2673)  
(KB981349)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=153fd9c1-0f8e-4492-87d1-f0381e7feb23)  
(KB981332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4f9a696d-2712-4777-a642-e78a38336e8a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d872bd77-f491-4706-8ff5-081ac0bf3d6f)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
Nessuno
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
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=0e7e3deb-f078-4953-9642-675ec69267f2)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=7ae9b1d0-0dbe-4abd-b315-10cea4ceccd7)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1189304f-d626-426d-960c-a86dc2d2b528)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=9f89746c-181e-4177-a851-ec1826e78b6d)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0a7ea2d0-61ce-4b68-ad82-d917b1a56f9d)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=28b035b8-d56e-4e93-b811-9a82cf1d4ba9)  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=a142a553-85fc-40e0-9426-8d58f6a4333c)  
(KB981349)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=72754e1b-3d09-4b9d-8794-689c45a37f66)  
(KB981332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f781e9e4-87d4-4243-9d44-256424d75fec)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cd007a6c-04b3-490c-aff4-d5af3e69d477)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=99a3f6da-728f-421c-ab41-c4c4751934a4)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=1709fd4e-d7c6-4cbb-8b71-a96b8d6eee58)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=52e4f66b-b76c-46a1-aeff-74efa21fc743)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=b97e7ea1-a163-4ce4-8cbc-5f933773c4b2)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1fc66f54-260a-4219-a0b4-056ba9dd0abe)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=339ddf48-8949-4857-9ef6-1ddcc7c5f8b8)  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=a489b4e3-78d2-411b-b27c-5987b8fc91d1)  
(KB981349)  
(Importante)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=72c3013b-f72f-422b-8a89-2246dea4b378)  
(KB981332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=644ff070-237b-4a73-b2e2-9fffdafa3927)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=19cfddfe-e8da-4564-9730-babfae4a3ebb)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=06832599-1e9b-4792-8c7b-7b5b3a3d6277)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=811a2b28-655d-4b5d-821e-5a90d556dba3)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b2b6d8b1-63cc-459c-b5fa-1355386273c8)  
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
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=8dcb8be8-fb78-4518-aa7e-f8b17f7dfb86)  
(Importante)
</td>
<td style="border:1px solid black;">
[VBScript 5.6](http://www.microsoft.com/downloads/details.aspx?familyid=9a8bee82-5f7f-490e-a1eb-481f6d4fc4f5)  
(KB981350)  
(Importante)  
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=7d542ac6-8a5b-4dd7-8688-2b5feb563636)  
(KB981349)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=56c8238d-8b04-4aa5-8719-40550cd7325c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=916f1b09-e79e-4347-9fbc-c0cf07de397d)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="10">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
Nessuno
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
[Verifica della firma Authenticode 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=a52225a7-6005-4f2b-8291-db20558f23f8)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=6145e2b2-36fd-4360-bd5b-2bd11890fc52)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=25eeaeb3-c0a3-4a02-9912-acd0342648ba)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=0e7140bb-42d3-48b3-9f4b-d55b17770de8)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista](http://www.microsoft.com/downloads/details.aspx?familyid=86d7b054-af4f-4d8a-9873-cb5246466374)  
(Importante)  
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=86d7b054-af4f-4d8a-9873-cb5246466374)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=ee5c42c6-16bb-48bf-95c2-c188bb17d04b)  
(KB981349)  
(Nessun livello di gravità<sup>[2]</sup>)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=f2a37dbf-4a95-4e8d-a474-ecacd9aee690)  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=196055a6-15d1-4da8-b33d-501e69bf5176)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=9ba7468c-23a4-4994-9a5a-22e96ef586f3)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=5b7efa82-0feb-413a-9f8e-212e7432cd99)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=394c1caa-97e4-47a3-9aac-a4a88508bd31)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=b885aef4-3a5d-4c3e-bef6-5efef2965752)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=7c84aa24-6331-427a-969c-27f7d39db3d7)  
(Importante)  
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c84aa24-6331-427a-969c-27f7d39db3d7)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=ea5c5e9c-0ecd-47bc-912d-5adc00d1aa21)  
(KB981349)  
(Nessun livello di gravità<sup>[2]</sup>)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=79093796-4ea9-4c6c-92cc-3fd63c5db918)  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c1d1622-1b67-438d-aae4-1a3954974a36)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=97ffeec8-8b6d-4a30-97b0-4bff2ba5e91d)\*  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=f111735b-68b0-4bcc-9dd8-818a5eca3400)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=51c9c420-4507-4911-a8f5-82331a696882)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=8e9c04c9-898f-4ed2-949d-f4343cc0d9f6)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=25e3ce7f-53a0-4049-a65c-011d2143c4c2)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=dbe89813-0a45-463b-928c-1e58f7bb596a)\*\*  
(KB981349)  
(Nessun livello di gravità<sup>[2]</sup>)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=527d6376-efc9-436b-835b-219d38bb28f0)\*\*  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e29ead69-000a-4982-a25c-f3981eda381a)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=61ece7bc-e9fa-4ede-ba7d-9e5a4c64b9be)\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=49f9f740-023a-4291-becf-838a1d282321)\*  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=91c08251-0085-44cb-9e9c-9a1a84374caf)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=61c26a1f-c885-4474-9843-204c41628889)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Codec MPEG Layer-3](http://www.microsoft.com/downloads/details.aspx?familyid=d6f2e1ae-48d3-4d2c-b329-32cff00afee5)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b99e54d-955b-4a06-9a04-b2f4596efd72)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=9db62357-557d-40cd-9826-b7baa6c9de65)\*\*  
(KB981349)  
(Nessun livello di gravità<sup>[2]</sup>)  
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=0c384dbc-21b7-4cbc-b68f-ced971d9b791)\*\*  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8f922e64-e3a6-46fe-9a81-b2813ea6a330)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=72e7c7ea-55ef-457b-a03a-49aa9dea2e84)\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=bd60779a-8bb1-4107-a344-9b09a50e96ff)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=eb116688-1d6e-4e20-948e-1d347af5d985)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bcf8b919-08a9-487f-8dfd-3ca24328c4f3)  
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
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1f9746d-61a2-406f-b707-60646bd5b5bb)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.7](http://www.microsoft.com/downloads/details.aspx?familyid=84c5aaae-9417-42a1-834f-22c1ad46a12f)  
(KB981349)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8c48302c-a1d6-41bc-ad24-7ce7332d4842)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="10">
Windows 7
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=8d4a6c65-e171-4570-8f3f-118f06910baf)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=f0dbac52-0f0e-40bc-9371-17fa594424d5)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=389184c5-9001-497d-bdf4-81f97ecb617f)  
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
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=ff58d80c-33ce-4d9e-aaa5-0b1841458931)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=c3f76835-0053-4e53-a451-14255e7a4fc0)  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
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
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=cf8c6721-05c2-4680-93b4-be36f09c6d15)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=b23efe7d-bca4-4d49-9104-6ae39dc5daa9)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=f3495dae-71f3-421d-a191-d26965f26ad1)  
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
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7f1dc055-2ec9-407a-9e69-da12338587e3)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=998164b7-4b8c-468b-8d39-f242633c8838)  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-019**](http://technet.microsoft.com/security/bulletin/ms10-019)
</td>
<td style="border:1px solid black;">
[**MS10-020**](http://technet.microsoft.com/security/bulletin/ms10-020)
</td>
<td style="border:1px solid black;">
[**MS10-025**](http://technet.microsoft.com/security/bulletin/ms10-025)
</td>
<td style="border:1px solid black;">
[**MS10-026**](http://technet.microsoft.com/security/bulletin/ms10-026)
</td>
<td style="border:1px solid black;">
[**MS10-027**](http://technet.microsoft.com/security/bulletin/ms10-027)
</td>
<td style="border:1px solid black;">
[**MS10-021**](http://technet.microsoft.com/security/bulletin/ms10-021)
</td>
<td style="border:1px solid black;">
[**MS10-022**](http://technet.microsoft.com/security/bulletin/ms10-022)
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
</td>
<td style="border:1px solid black;">
[**MS10-029**](http://technet.microsoft.com/security/bulletin/ms10-029)
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
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
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=94dfdaae-8464-4de6-a401-7eb70b3bb34f)\*  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=a2979c02-2a80-4b84-bf6c-4798064bdf28)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=cd1a046e-915d-4904-b753-5a24be10c504)\*  
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
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=28389c1d-2a12-4bef-a59b-726bb6449c8b)\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=c4039d40-a0c7-4183-ab50-04f690d1c5dc)\*\*  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=eb27cd2b-d514-4405-8650-259a42e35155)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Verifica della firma Authenticode 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=40f622d2-48e7-4eb2-9430-bbd218cb5208)  
(KB978601)  
(Critico)  
[Estensione shell Cabinet File Viewer 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=5e416d4b-5de7-4688-80c6-245de159e0ce)  
(KB979309)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=541e9e2f-ec1d-42b2-aae5-481c0d435169)  
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
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d4ea3984-5183-47f1-814e-29cb6c90ae06)  
(Moderato)
</td>
<td style="border:1px solid black;">
[VBScript 5.8](http://www.microsoft.com/downloads/details.aspx?familyid=8174463c-5c5e-4095-90c8-fd1e898d4ba5)  
(KB981332)  
(Nessun livello di gravità<sup>[2]</sup>)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Note per MS10-022**

<sup>[1]</sup>Questo aggiornamento per la protezione aggiorna l'installazione di VBScript dalla versione 5.1 alla 5.6.

<sup>[2]</sup>Livelli di gravità non sono applicabili a quest'aggiornamento perché la vulnerabilità trattata in questo bollettino non interessa questo software. Tuttavia, agli utenti di questo software Microsoft viene consigliato di applicare l'aggiornamento per la protezione come misura preventiva per difendersi da eventuali nuovi vettori identificabili in futuro.

**Nota per MS10-024**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

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
[**MS10-023**](http://technet.microsoft.com/security/bulletin/ms10-023)
</td>
<td style="border:1px solid black;">
[**MS10-028**](http://technet.microsoft.com/security/bulletin/ms10-028)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP
</td>
<td style="border:1px solid black;">
[Microsoft Office Publisher 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=943b3830-70d5-46c5-bffc-1b494434b5f7)  
(KB980466)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Visio 2002 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2d563cbc-d8f7-486b-8c54-25d168085376)  
(KB979364)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office Publisher 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7c2f4610-77bb-4d72-847b-1a06c523b137)  
(KB980469)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Visio 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=803a7ea0-a9da-46dd-9548-0177d3774be7)  
(KB979356)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office Publisher 2007 Service Pack 1 e Microsoft Office Publisher 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=10ca2f71-0ab2-4344-b7fd-bbbd6a783a96)  
(KB980470)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Visio 2007 Service Pack 1 e Microsoft Office Visio 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=56fe020f-4444-4a43-aa98-e99a622f6a69)  
(KB979365)  
(Importante)
</td>
</tr>
</table>
 

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
Microsoft Exchange Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-024**](http://technet.microsoft.com/security/bulletin/ms10-024)
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
Microsoft Exchange Server 2000
</td>
<td style="border:1px solid black;">
[Microsoft Exchange Server 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e47c90a0-c9c8-43b7-bec7-34107ddde294)  
(KB976703)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Exchange Server 2003
</td>
<td style="border:1px solid black;">
[Microsoft Exchange Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bc8391f8-5335-496b-ad4c-bae38509be4a)  
(KB976702)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Exchange Server 2007
</td>
<td style="border:1px solid black;">
[Microsoft Exchange Server 2007 Service Pack 1 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=6a894b4e-12b6-4a91-9555-d813956b6aac)  
(KB981407)  
(Nessun livello di gravità<sup>[1]</sup>)  
[Microsoft Exchange Server 2007 Service Pack 2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=b8f7f872-16d5-49d6-9867-adc01351c06f)  
(KB981383)  
(Nessun livello di gravità<sup>[1]</sup>)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Exchange Server 2010
</td>
<td style="border:1px solid black;">
[Microsoft Exchange Server 2010 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7dcf2390-dff7-4e3a-acca-03f4d43fb79a)  
(KB981401)  
(Nessun livello di gravità<sup>[1]</sup>)
</td>
</tr>
</table>
 
**Note per MS10-024**

<sup>[1]</sup>Livelli di gravità non sono applicabili a quest'aggiornamento perché la vulnerabilità trattata in questo bollettino non interessa questo software. Tuttavia, agli utenti di questo software Microsoft viene consigliato di applicare questo aggiornamento, che include un sistema di difesa per ottenere una maggiore entropia delle porte di origine per le transazioni DNS avviate dal servizio SMTP.

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

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860(en-us).aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/systemcenter/configmgr/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx)).

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

-   Mark Rabinovich di [Visuality Systems Ltd](http://www.visualitynq.com/). per aver segnalato un problema descritto nel bollettino MS10-020
-   Laurent Gaffié di [stratsec](http://www.stratsec.net/) per aver segnalato tre problemi descritti nel bollettino MS10-020
-   Matthew 'j00 ru' Jurczyk e Gynvael Coldwind di [Hispasec](http://www.hispasec.com/)[Virustotal](http://www.virustotal.com/) per aver segnalato cinque problemi descritti nel bollettino MS10-021
-   Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato due problemi descritti nel bollettino MS10-021
-   Martin Tofall di [Obsidium Software](http://www.obsidium.de/) per aver segnalato un problema descritto nel bollettino MS10-021
-   Lionel d'Hauenens, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-023
-   Fabien Perigaud di [CERT-LEXSI](http://cert.lexsi.com/) per aver segnalato un problema descritto nel bollettino MS10-025
-   Fabien Perigaud di [CERT-LEXSI](http://cert.lexsi.com/), il [VUPEN Vulnerability Research Team](http://www.vupen.com/), il Vulnerability Research Team, [TELUS Security Labs](http://telussecuritylabs.com/), [Core Security Technologies](http://www.coresecurity.com/) e il [NSFOCUS Security Team](http://www.nsfocus.com/) per la loro collaborazione e per aver fornito dettagli su un problema di qualità nell'aggiornamento per la protezione originale per il bollettino MS10-025
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS10-026
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-027
-   Bing Liu di [FortiGuard Labs](http://www.fortiguard.com/) di Fortinet per aver segnalato due problemi descritti nel bollettino MS10-028
-   Gabi Nakibly di National EW Research & Simulation Center (presso Rafael) Haifa per aver segnalato un problema descritto nel bollettino MS10-029

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/?ln=itcommon/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (13 aprile 2010): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (14 aprile 2010): È stato corretto il requisito di riavvio per MS10-025 nella sezione **Riepiloghi**. Inoltre, è stata corretta la notazione sui Server Core, per Windows Server 2008 e Windows Server 2008 R2, da applicare solo all'aggiornamento KB978601 di MS10-019.
-   V2.0 (21 aprile 2010): Il bollettino è stato rivisto per informare i clienti che l'aggiornamento per la protezione originale per MS10-025 non proteggeva i sistemi dalla vulnerabilità descritta nel bollettino. Microsoft consiglia di applicare una delle soluzioni alternative descritte nel bollettino MS10-025 per contrastare l'impatto sui sistemi interessati finché non viene messo a disposizione un nuovo aggiornamento per la protezione.
-   V3.0 (27 aprile 2010): È stato rivisto il bollettino per offrire l'aggiornamento per la protezione appena rilasciato per MS10-025.
-   V4.0 (13 luglio 2010): È stato rivisto il bollettino per offrire l'aggiornamento per la protezione rilasciato nuovamente per Windows Server 2008 e Windows Server 2008 R2 per MS10-024.

*Built at 2014-04-18T01:50:00Z-07:00*
