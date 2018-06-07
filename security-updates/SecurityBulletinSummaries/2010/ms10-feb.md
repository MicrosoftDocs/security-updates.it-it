---
TOCTitle: 'MS10-FEB'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - febbraio 2010'
ms:assetid: 'ms10-feb'
ms:contentKeyID: 61240045
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-feb(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - febbraio 2010
==================================================================

Data di pubblicazione: martedì 9 febbraio 2010

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a febbraio 2010.

Con il rilascio dei bollettini del mese di febbraio 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 febbraio 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 10 febbraio 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di febbraio](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032427679&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-006">MS10-006</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel client SMB possono consentire l'esecuzione di codice in modalità remota (978251)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ha inviato una risposta SMB appositamente predisposta ad una richiesta SMB avviata dal client. Per sfruttare queste vulnerabilità, un utente malintenzionato deve convincere l'utente ad avviare una connessione SMB a un server SMB dannoso.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-007">MS10-007</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del gestore della shell di Windows può consentire l'esecuzione di codice in modalità remota (975713)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità riscontrabile in Microsoft Windows 2000, Windows XP e Windows Server 2003 che è stata segnalata privatamente. Le altre versioni di Windows non sono interessate da questo aggiornamento per la protezione. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un'applicazione, come un browser Web, invia dati appositamente predisposti alla funzione dell'API ShellExecute tramite il gestore della shell di Windows.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-008">MS10-008</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit ActiveX (978262)</strong><br />
<br />
Questo aggiornamento della protezione risolve una vulnerabilità segnalata privatamente per il software di Microsoft. Questo aggiornamento per la protezione è considerato di livello critico per tutte le edizioni supportate di Microsoft Windows 2000 e Windows XP, di livello importante per tutte le edizioni supportate di Windows Vista e Windows 7, di livello moderato per tutte le edizioni supportate di Windows Server 2003 e di livello basso per tutte le edizioni supportate di Windows Server 2008 e Windows Server 2008 R2.<br />
<br />
Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta che crea un'istanza di un controllo ActiveX con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Questo aggiornamento contiene anche i kill bit per quattro controlli ActiveX di terze parti.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-009">MS10-009</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Windows TCP/IP possono consentire l'esecuzione di codice in modalità remota (974145)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota in caso di invio di pacchetti appositamente predisposti a un computer in cui è attivato IPv6. Un utente malintenzionato può tentare di sfruttare la vulnerabilità creando pacchetti ICMPv6 appositamente predisposti e inviandoli a un sistema in cui è attivato IPv6. La vulnerabilità può essere sfruttata solo se l'utente malintenzionato è on-link.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-013">MS10-013</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft DirectShow può consentire l'esecuzione di codice in modalità remota (977935)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft DirectShow che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file AVI appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-003">MS10-003</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office (MSO) può consentire l'esecuzione di codice in modalità remota (978214)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Office che può consentire l'esecuzione di codice in modalità remota se un utente apre un file Office appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-004">MS10-004</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (975416)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sei vulnerabilità di Microsoft Office PowerPoint segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di PowerPoint appositamente predisposto. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-010">MS10-010</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Server 2008 Hyper-V può consentire un attacco di tipo Denial of Service (977894)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft, che è stata riscontrata in Windows Server 2008 Hyper-V e in Windows Server 2008 R2 Hyper-V. Tale vulnerabilità può consentire un attacco di tipo Denial of Service se una sequenza non valida di istruzioni in linguaggio macchina viene eseguita da un utente autenticato in una delle macchine virtuali guest ospitate dal server Hyper-V. Per sfruttare tale vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di accedere in locale a una macchina virtuale guest. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-011">MS10-011</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel sottosistema runtime client/server di Windows può consentire l'acquisizione di privilegi più elevati (978037)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità del sottosistema runtime client/server di Microsoft Windows (CSRSS) che è stata segnalata privatamente ed è riscontrabile in Microsoft Windows 2000, Windows XP e Windows Server 2003. Le altre versioni di Windows non sono interessate. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed avvia un'applicazione appositamente predisposta progettata per continuare lo sfruttamento anche dopo che l'utente malintenzionato si è disconnesso. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-012">MS10-012</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel server SMB possono consentire l'esecuzione di codice in modalità remota (971468)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato crea un pacchetto SMB appositamente predisposto e lo invia a un sistema interessato. Le procedure consigliate e le configurazioni predefinite standard dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale attraverso queste vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-014">MS10-014</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Kerberos può consentire un attacco di tipo Denial of Service (977290)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Tale vulnerabilità può consentire un attacco di tipo Denial of Service se una richiesta appositamente predisposta di rinnovo del ticket viene inviata al dominio Kerberos Windows da un utente che si è autenticato in un'area di autenticazione Kerberos non Windows. La condizione di Denial of Service può persistere fino a quando non viene riavviato il controller di dominio.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-015">MS10-015</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (977165)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Windows. Tali vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato ha accesso al sistema e poi esegue un'applicazione appositamente predisposta. Per sfruttare queste vulnerabilità, l'utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-005">MS10-005</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Paint può consentire l'esecuzione di codice in modalità remota (978706)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Paint che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente utilizza Microsoft Paint per visualizzare un file di immagine JPEG appositamente predisposto. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Moderato</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                                     | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                 | Note fondamentali                                                                                                                  |  
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|  
| [MS10-006](http://go.microsoft.com/fwlink/?linkid=178850) | Vulnerabilità legata alla race condition dei client SMB                                                        | [CVE-2010-0017](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0017) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Un vettore di attacco remoto può consentire attacchi di tipo DoS; un vettore di attacco locale può consentire attacchi di tipo EoP |  
| [MS10-011](http://go.microsoft.com/fwlink/?linkid=179798) | Vulnerabilità legata all'acquisizione locale di privilegi più elevati in CSRSS                                 | [CVE-2010-0023](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0023) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'utente malintenzionato e la vittima devono accedere alla stessa console                                                          |  
| [MS10-007](http://go.microsoft.com/fwlink/?linkid=179067) | Vulnerabilità legata alla convalida dell'URL                                                                   | [CVE-2010-0027](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0027) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata all'overflow degli heap LinkedSlideAtom di PowerPoint                                     | [CVE-2010-0030](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0030) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata all'indicizzazione non valida della matrice OEPlaceholderAtom 'placementId' di PowerPoint | [CVE-2010-0031](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0031) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata a un errore di tipo use-after-free nella matrice OEPlaceholderAtom di PowerPoint          | [CVE-2010-0032](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0032) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata all'overflow dello stack dei record TextBytesAtom del Visualizzatore di PowerPoint        | [CVE-2010-0033](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0033) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | La vulnerabilità interessa solamente il Visualizzatore di PowerPoint 2003                                                          |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata all'overflow dello stack dei record TextCharsAtom del Visualizzatore di Office PowerPoint | [CVE-2010-0034](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0034) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | La vulnerabilità interessa solamente il Visualizzatore di PowerPoint 2003                                                          |  
| [MS10-012](http://go.microsoft.com/fwlink/?linkid=155976) | Vulnerabilità legata alla mancata entropia per l'autenticazione NTLM di SMB                                    | [CVE-2010-0231](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0231) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-015](http://go.microsoft.com/fwlink/?linkid=179062) | Vulnerabilità legata al gestore delle eccezioni del kernel di Windows                                          | [CVE-2010-0232](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0232) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-003](http://go.microsoft.com/fwlink/?linkid=178812) | Vulnerabilità legata al sovraccarico del buffer in MSO.DLL                                                     | [CVE-2010-0243](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0243) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-013](http://go.microsoft.com/fwlink/?linkid=167321) | Vulnerabilità legata all'overflow degli heap in DirectShow                                                     | [CVE-2010-0250](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0250) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                          |  
| [MS10-006](http://go.microsoft.com/fwlink/?linkid=178850) | Vulnerabilità legata al danneggiamento del pool di client SMB                                                  | [CVE-2010-0016](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0016) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                          |  
| [MS10-012](http://go.microsoft.com/fwlink/?linkid=155976) | Vulnerabilità legata all'overflow dei nomi percorso SMB                                                        | [CVE-2010-0020](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0020) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                          |  
| [MS10-012](http://go.microsoft.com/fwlink/?linkid=155976) | Vulnerabilità legata al danneggiamento della memoria SMB                                                       | [CVE-2010-0021](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0021) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                          |  
| [MS10-005](http://go.microsoft.com/fwlink/?linkid=180620) | Vulnerabilità legata all'overflow dei valori integer in MS Paint                                               | [CVE-2010-0028](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0028) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Lo sfruttamento della vulnerabilità richiede una significativa interazione da parte dell'utente                                    |  
| [MS10-004](http://go.microsoft.com/fwlink/?linkid=163639) | Vulnerabilità legata all'overflow del buffer per la gestione dei percorsi dei file di PowerPoint               | [CVE-2010-0029](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0029) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                          |  
| [MS10-015](http://go.microsoft.com/fwlink/?linkid=179062) | Vulnerabilità legata alla condizione double free del kernel di Windows                                         | [CVE-2010-0233](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0233) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                          |  
| [MS10-009](http://go.microsoft.com/fwlink/?linkid=167190) | Vulnerabilità legata all'annuncio router ICMPv6                                                                | [CVE-2010-0239](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0239) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Lo sfruttamento della vulnerabilità richiede che l'utente malintenzionato sia on-link rispetto all'host di destinazione            |  
| [MS10-009](http://go.microsoft.com/fwlink/?linkid=167190) | Vulnerabilità legata alla frammentazione MDL delle intestazioni                                                | [CVE-2010-0240](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0240) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | La vulnerabilità richiede un driver di rete di terze parti                                                                         |  
| [MS10-009](http://go.microsoft.com/fwlink/?linkid=167190) | Vulnerabilità legata alle informazioni di instradamento ICMPv6                                                 | [CVE-2010-0241](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0241) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Lo sfruttamento della vulnerabilità richiede che l'utente malintenzionato sia on-link rispetto all'host di destinazione            |  
| [MS10-012](http://go.microsoft.com/fwlink/?linkid=155976) | Vulnerabilità del puntatore NULL di SMB                                                                        | [CVE-2010-0022](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0022) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                                                                          |  
| [MS10-010](http://go.microsoft.com/fwlink/?linkid=179066) | Vulnerabilità legata alla convalida del set di istruzioni per Hyper-V                                          | [CVE-2010-0026](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0026) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | La vulnerabilità consente che si verifichi una condizione di tipo "solo DoS"                                                       |  
| [MS10-014](http://go.microsoft.com/fwlink/?linkid=181196) | Vulnerabilità legata alla risoluzione del riferimento di un puntatore NULL in Kerberos                         | [CVE-2010-0035](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0035) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Condizione "solo DoS"; sfruttamento possibile solamente in controller di dominio con configurazione non predefinita                |  
| [MS10-009](http://go.microsoft.com/fwlink/?linkid=167190) | Vulnerabilità legata al riconoscimento selettivo TCP/IP                                                        | [CVE-2010-0242](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0242) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                                                                          |
  
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
<th colspan="12">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=80b49bab-6c2f-48a8-a901-ca3f76e4fe6b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=92234237-a8eb-4ce4-bc5e-cd86feb7dbd3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=543dc6a7-fa76-4ba9-81e4-25fdf2013548)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=ba110440-10ce-40a0-884a-8b9afd45a3e3)  
(KB977914)  
(Critico)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=16787c93-2c95-4c13-8492-be1db9d18146)  
(KB975560)  
(Critico)  
[Quartz in DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=59a8bc19-02bb-4800-bac1-464f59e1cb7b)<sup>[1]</sup>
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=456185b5-57d1-4fa5-a4a9-5b2006ede3ad)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=267ce982-54a0-418f-ad52-e4963610f714)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=56a9afba-a6ee-4fb9-ba85-e51d9f94de27)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=ed8ac6a5-c8bb-4ed4-8994-810e9a1863c3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=e5861705-8f49-45cb-8a92-cf052ccf4134)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="12">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
Nessuno
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
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f6c4472e-385c-4412-bda9-c2e615e50713)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b8e7bf17-a037-4200-9ae2-2280b19766a4)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7bcf3945-0552-478e-b7f3-bbca97dd1b5d)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=a9beb2bd-e5f6-43f9-bbcc-a2afee5e5ceb)  
(KB977914)  
(Critico)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=7ab53be3-3f42-4e61-a2bc-3ed41d8736ff)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b9234b40-1b1c-498b-90d4-0bff347b36ee)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=8f7adee3-e68e-41b3-b835-d84691774f31)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e2b348f5-ec8d-4782-bb03-5de550adea77)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b2e70df6-7728-4fc3-8df7-8ddb9ba5202f)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=63e15ff0-73b3-46c9-96f8-c18977d35a10)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8d83f30-9cd7-4d6b-b2b9-65d0a483cb9c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=25ef97e8-e76e-44c2-953c-f94cbac552cf)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=dedc3010-a989-45f7-b9d4-f7079db3e572)  
(KB977914)  
(Critico)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=7543e819-cd36-4e89-9850-60f00c50999d)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1f83bf7a-e16c-404a-89bd-f65843938299)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=91ee57f2-81e5-49bd-bdfc-d3e385efc8a5)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e534d00c-6ddc-4eb3-9464-5db6e90afa3e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f8c4acc8-c2f4-41f7-9b32-e7bd791e0155)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="12">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
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
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=feb8c145-7c30-45fa-a6f0-8b6453ddd521)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5cb2e203-18fb-4887-a1c9-289d86b8ba11)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29ff72f7-1663-4f35-a794-2dfe3c17b39c)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=cc5150d7-070e-4a87-9c02-d050a8cb2204)  
(KB977914)  
(Critico)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=983c5484-6321-4765-97ec-8d42d42d1f70)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2c8c4eec-255e-41d5-b1e6-f0204edcb46f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3d18cbc4-ac48-458c-8aa3-90708fd854ff)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=738e2fda-96fc-413d-a5c7-74b1fac1d6b3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=defd8603-ed9b-42f9-a539-2b6a690e9575)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c1efbe73-fc87-4e6a-8b36-81f125a27aec)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=36d88c1b-814c-4371-9ed2-d4576f419fc3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=90360537-9311-45e2-8047-9a971f90c3c3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d4a97bb7-4f74-4884-9a6e-7a4df9c540fb)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=db13e99b-2f2a-4474-8d6e-271b025bd07f)  
(KB977914)  
(Critico)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=7dc20252-6091-407b-befc-c25e8f5d3fb0)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=de0186f6-27a2-4226-b8eb-f2912710f072)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d63c95e-311a-446f-8852-dffd217a89f6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f8ad539d-8191-4864-977b-ad4e31c04ba0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9873c962-9d3d-46ef-b54b-2a50696fb6b2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9143e435-f0d6-464b-9273-4d1f38f8ff3a)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=622442b0-cffe-4fc2-94a8-edff9d71ecd3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d695ca9f-a1db-4c0f-94b6-7112861c28da)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b84f0be4-6d11-4b07-bb3c-2c76ae9ceea8)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Filtro AVI](http://www.microsoft.com/downloads/details.aspx?familyid=aec66173-e2c6-4c39-8d60-8fbef6d7b764)  
(KB977914)  
(Importante)  
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=b1a7533a-913f-4054-b579-489a257bae5f)  
(KB975560)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=87732f7a-9339-43bc-a4e8-3da849f35b70)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ee7f8cc4-f7fd-4dc7-808c-436204ee80cb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d549c927-add7-4d83-bfc7-15dc35663dfb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c3c21225-8534-4c7f-96b6-20a743dcea74)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ee603435-26af-4ab9-9f22-92734346dc0a)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="12">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
Nessuno
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1902fc93-0f4b-4261-9da3-17d1931daf2e)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2c897ddd-f441-41d4-b5b4-d794cfc96e6b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=71f03946-622c-4403-b94f-f6a3de18a8c3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=7130ce0f-df38-4c96-ac54-cdbff35f03e7)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=16494dac-553a-4de9-b751-0d6b51cb43f0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2761c7b4-d472-4f00-949b-af3ebafdc08d)  
(Importante)
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
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7c2f89b5-a3b3-42cd-857d-923fe8b8f1da)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f349f7aa-d020-4e0d-a35f-518a63ec92df)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=519815fd-707d-476f-9e29-7b03b7a17af5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=de7b7c8f-bd0a-4e13-bd58-d95507a6274b)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cec582b3-e37f-448e-a5c3-6abdcee9e57c)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=38b40dab-6b4d-434b-9997-12ef70d6bbcc)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="12">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=09e19263-18ba-495e-bcf7-719e957204a7)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9a85b1bf-7427-47d0-9e1b-21dbe824a62c)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bc451228-3de4-427c-b42f-91f204c708b8)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=5ac0a948-0bdc-4c10-9b88-16a5d7092e47)\*\*  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=597b2310-2cd8-4d0f-8248-781eb8b7450a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=75327470-0f14-4cdd-bcb7-64684c61c267)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=21e87558-9bd2-4aa9-aaa5-7fd26a5b60e6)\*  
(Importante)
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
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=180c2313-5e3e-4d84-87cd-64048f51e0f6)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fde218c3-90ab-4664-852d-25ca55835054)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3a889152-5d7c-4a3e-b4f1-c6507b739ca0)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=362fea40-649b-4471-aad7-db29edd0ac10)\*\*  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3463a63c-e88a-4036-ab60-f84d4bf4191a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=67119fb6-e517-46f4-ab0b-2351cdc3d670)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d0f8f81-fc10-450a-a653-06f89acba9fa)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0b93047d-f2c6-403b-9200-c251898bc1e0)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=614eaf7e-95aa-4f8f-910c-1980e1f14d11)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5b6e9451-df38-4626-bb1d-4fc160d7a40e)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1cd1882b-8e55-47ea-a82a-68bb59a500a7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=effa638b-cfc1-4777-8219-7b433ed5e717)  
(KB975560)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f90fc0c8-babe-4224-be07-614ea7ddf102)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cd6b234b-8e96-4128-a77a-645a0882996a)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="12">
Windows 7
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=a589431a-93dc-42cd-a74e-d9c1e3452fef)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=ec6d996f-dffa-45ad-9467-e96a4ac63e5f)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=4ec49aa2-81df-4e65-80da-6201394c4089)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=122fc003-0651-4ad2-a5c8-a21536defad8)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=66f14bb4-40fc-4ae3-9baf-429b7106cd91)  
(Importante)
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
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=3c1edcf8-d304-45c4-9818-1cd86383b3fe)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=b3265576-04c1-48b1-8ce9-128843c58cf5)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=a8a2519c-3b89-4987-9473-920adafc78cb)  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=3e096468-db6c-45c6-bee5-eaeaa63500b5)  
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
<th colspan="12">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-006**](http://go.microsoft.com/fwlink/?linkid=178850)
</td>
<td style="border:1px solid black;">
[**MS10-007**](http://go.microsoft.com/fwlink/?linkid=179067)
</td>
<td style="border:1px solid black;">
[**MS10-008**](http://go.microsoft.com/fwlink/?linkid=179106)
</td>
<td style="border:1px solid black;">
[**MS10-009**](http://go.microsoft.com/fwlink/?linkid=167190)
</td>
<td style="border:1px solid black;">
[**MS10-013**](http://go.microsoft.com/fwlink/?linkid=167321)
</td>
<td style="border:1px solid black;">
[**MS10-010**](http://go.microsoft.com/fwlink/?linkid=179066)
</td>
<td style="border:1px solid black;">
[**MS10-011**](http://go.microsoft.com/fwlink/?linkid=179798)
</td>
<td style="border:1px solid black;">
[**MS10-012**](http://go.microsoft.com/fwlink/?linkid=155976)
</td>
<td style="border:1px solid black;">
[**MS10-014**](http://go.microsoft.com/fwlink/?linkid=181196)
</td>
<td style="border:1px solid black;">
[**MS10-015**](http://go.microsoft.com/fwlink/?linkid=179062)
</td>
<td style="border:1px solid black;">
[**MS10-005**](http://go.microsoft.com/fwlink/?linkid=180620)
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
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=ecb06350-47a7-48eb-825f-3e8f89c5ca8e)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=cda31c54-8b81-4185-a623-64480ad4b73c)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=a9811baa-1500-4c73-940b-57f8c5456891)\*\*  
(KB975560)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=3214b347-d901-4aac-85ce-676e4602de87)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=dc757b6d-f0f8-4e71-ab6f-1417233eedf9)\*  
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
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=badd6cab-7738-4401-a68c-c15414388601)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=43fa4e26-160f-4aa3-a03d-b98a79666a18)  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Quartz](http://www.microsoft.com/downloads/details.aspx?familyid=2ed23bf5-6217-413c-a7ba-eccc82139d68)  
(KB975560)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d5b0b1eb-24f3-47ec-aba1-c1b95400189e)  
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
</table>
 
**Nota per MS10-013**

<sup>[1]</sup>L'aggiornamento previsto per DirectX 9.0 interessa anche DirectX 9.0a, DirectX 9.0b e DirectX 9.0c in Microsoft Windows 2000.

**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

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
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-003**](http://go.microsoft.com/fwlink/?linkid=178812)
</td>
<td style="border:1px solid black;">
[**MS10-004**](http://go.microsoft.com/fwlink/?linkid=163639)
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
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=47553f45-fa10-40e5-8267-9d42ff560a62)  
(KB977896)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=cfc697b4-2ceb-4030-86c5-be9bc8bfd07c)  
(KB973143)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2291ae24-fa39-4ad8-a7d0-12726b68ad96)  
(KB976881)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office per Mac
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-003**](http://go.microsoft.com/fwlink/?linkid=178812)
</td>
<td style="border:1px solid black;">
[**MS10-004**](http://go.microsoft.com/fwlink/?linkid=163639)
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=7c985595-00c5-44b8-81c3-59d9967220f8)<sup>[1]</sup>
(KB979674)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=7c985595-00c5-44b8-81c3-59d9967220f8)<sup>[1]</sup>
(KB979674)  
(Importante)
</td>
</tr>
</table>
 
**Nota per Microsoft Office per Mac**

<sup>[1]</sup>A causa del modello di servizio cumulativo per Microsoft Office 2004 per Mac, questi aggiornamenti sono identici.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Note** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx010402221040.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

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

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Damian Frizza di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS10-003
-   Carsten Eiram di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS10-004
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato tre problemi descritti nel bollettino MS10-004
-   SkD, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-004
-   Cody Pierce di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-004
-   Tielei Wang di ICST-ERCIS (Engineering Research Center of Info Security, Institute of Computer Science & Technology, Peking University/China), che collabora con [Secunia](http://secunia.com/), per aver segnalato un problema descritto nel bollettino MS10-005
-   Laurent Gaffié di [stratsec](http://www.stratsec.net/) per aver segnalato due problemi descritti nel bollettino MS10-006
-   Brett Moore, che collabora con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS10-007
-   [Lostmon Lords](http://lostmon.blogspot.com/) per aver segnalato un problema descritto nel bollettino MS10-007
-   Shaun Colley di [NGS Software](http://www.ngssoftware.com/) per aver segnalato un problema descritto nel bollettino MS10-008
-   Sumit Gwalani, Drew Hintz e Neel Mehta di [Google Security Team](http://www.google.com/) per aver segnalato tre problemi descritti nel bollettino MS10-009
-   Jan Bottorff per aver segnalato un problema descritto nel bollettino MS10-010
-   Matthew ‘j00 ru' Jurczyk e Gynvael Coldwind di [Hispasec](http://www.hispasec.com/) per aver segnalato un problema descritto nel bollettino MS10-011
-   Joshua Morin di [Codenomicon](http://www.codenomicon.com/) per aver segnalato un problema descritto nel bollettino MS10-012
-   Florian Rienhardt di [BSI](http://www.bsi.bund.de/) per aver segnalato un problema descritto in MS10-012
-   Hernan Ochoa per aver segnalato un problema descritto nel bollettino MS10-012
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS10-013
-   Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-015

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 febbraio 2010): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
