---
TOCTitle: 'MS10-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2010'
ms:assetid: 'ms10-sep'
ms:contentKeyID: 61240053
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2010
===================================================================

Data di pubblicazione: martedì 14 settembre 2010 | Aggiornamento: mercoledì 26 ottobre 2011

**Versione:** 6.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a settembre 2010.

Con il rilascio dei bollettini del mese di settembre 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 9 settembre 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 15 settembre 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032454433&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Per il bollettino straordinario sulla sicurezza aggiunto alla versione 3.0 del presente riepilogo dei bollettini, MS10-070, Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questo bollettino il 28 settembre 2010, alle 13:00 ora del Pacifico (USA e Canada). [Registrazione immediata per il webcast del 28 settembre alle 13:00](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032464130&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza.

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=200505">MS10-061</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel servizio Spooler di stampa può consentire l'esecuzione di codice in modalità remota (2347290)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente nel servizio Spooler di stampa. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia una richiesta di stampa appositamente predisposta a un sistema vulnerabile che presenta uno spooler di stampa con interfaccia esposta tramite RPC. Per impostazione predefinita, le stampanti non sono condivise in nessun sistema operativo Windows attualmente supportato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190884">MS10-062</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel codec MPEG-4 può consentire l'esecuzione di codice in modalità remota (975558)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità nel codec MPEG-4 che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file multimediale appositamente predisposto o se riceve un flusso di contenuti appositamente predisposto da un sito Web o da un'applicazione che fornisce contenuti Web. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=200378">MS10-063</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Unicode Scripts Processor può consentire l'esecuzione di codice in modalità remota (2320113)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Unicode Scripts Processor. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un documento o una pagina Web appositamente predisposti, con un'applicazione che supporta caratteri Embedded OpenType. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=200727">MS10-064</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Outlook può consentire l'esecuzione di codice in modalità remota (2315011)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre o visualizza in anteprima un messaggio di posta elettronica appositamente predisposto utilizzando una versione interessata di Microsoft Outlook collegata ad un server Exchange in modalità online. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=199537">MS10-065</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Internet Information Services (IIS) possono consentire l'esecuzione di codice in modalità remota (2267960)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relativa a Internet Information Services (IIS). La più grave di tali vulnerabilità può consentire l'esecuzione di codice in modalità remota se un client invia una richiesta HTTP appositamente predisposta al server. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=197105">MS10-066</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Remote Procedure Call può consentire l'esecuzione di codice in modalità remota (982802)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ha inviato una risposta RPC appositamente predisposta ad una richiesta RPC avviata dal client. Un utente malintenzionato che sfrutti questa vulnerabilità potrebbe eseguire codice non autorizzato e acquisire il controllo completo del sistema interessato. Un utente malintenzionato deve convincere l'utente ad avviare una connessione RPC a un server dannoso controllato dall'utente malintenzionato. Un utente malintenzionato non può sfruttare questa vulnerabilità in modalità remota senza l'interazione dell'utente.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=197102">MS10-067</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei convertitori di testo di WordPad può consentire l'esecuzione di codice in modalità remota (2259922)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file appositamente predisposto con WordPad. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190509">MS10-068</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Local Security Authority Subsystem Service può consentire l'acquisizione di privilegi più elevati (983539)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Active Directory, in Active Directory Application Mode (ADAM) e in Active Directory Lightweight Directory Service (AD LDS). La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato autenticato invia messaggi LDAP (Lightweight Directory Access Protocol) appositamente predisposti a un server LSASS in ascolto. Per poter sfruttare questa vulnerabilità, un utente malintenzionato deve disporre di un account membro nel dominio Windows di destinazione. Tuttavia, non è necessario che l'utente malintenzionato abbia una workstation unita al dominio Windows.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=197093">MS10-069</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel sottosistema runtime client/server di Windows può consentire l'acquisizione di privilegi più elevati (2121546)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato ha accesso a un sistema interessato che è configurato con le impostazioni locali del sistema cinese, giapponese o coreano. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può quindi installare programmi, visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=202409">MS10-070</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in ASP.NET può consentire l'intercettazione di informazioni personali (2418042)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di ASP.NET Framework. Tale vulnerabilità può consentire l'intercettazione di informazioni personali. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può leggere i dati, come lo stato visualizzazione, codificato dal server. Questa vulnerabilità può essere utilizzata anche per manomettere i dati, che, se sfruttati con successo, possono servire per decrittografare e manomettere i dati codificati dal server. Le versioni di Microsoft .NET Framework precedenti a Microsoft .NET Framework 3.5 Service Pack 1 non sono interessate dall'aspetto relativo all'intercettazione dei contenuti file di questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft .NET Framework</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare** **questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                                               | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                                                          |  
|-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|  
| [MS10-062](http://go.microsoft.com/fwlink/?linkid=190884) | Vulnerabilità legata al codec MPEG-4                                                                                     | [CVE-2010-0818](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0818) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'esecuzione di codice risulta meno probabile in Windows Vista grazie a fattori attenuanti heap aggiuntivi |  
| [MS10-068](http://go.microsoft.com/fwlink/?linkid=190509) | Vulnerabilità legata all'overflow degli heap in LSASS                                                                    | [CVE-2010-0820](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0820) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                  |  
| [MS10-069](http://go.microsoft.com/fwlink/?linkid=197093) | Vulnerabilità legata all'acquisizione locale di privilegi più elevati in CSRSS                                           | [CVE-2010-1891](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1891) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                  |  
| [MS10-067](http://go.microsoft.com/fwlink/?linkid=197102) | Vulnerabilità legata al danneggiamento della memoria nel convertitore di testo di WordPad per Word 97                    | [CVE-2010-2563](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2563) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                  |  
| [MS10-066](http://go.microsoft.com/fwlink/?linkid=197105) | Vulnerabilità legata al danneggiamento della memoria RPC                                                                 | [CVE-2010-2567](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2567) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                  |  
| [MS10-061](http://go.microsoft.com/fwlink/?linkid=200505) | Vulnerabilità legata all'impersonificazione del servizio Spooler di stampa                                               | [CVE-2010-2729](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2729) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet**                               |  
| [MS10-070](http://go.microsoft.com/fwlink/?linkid=202409) | Vulnerabilità legata all'attacco padding oracle di ASP.NET                                                               | [CVE-2010-3332](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3332) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet**                               |  
| [MS10-065](http://go.microsoft.com/fwlink/?linkid=199537) | Vulnerabilità legata all'elusione dell'autenticazione tramite directory                                                  | [CVE-2010-2731](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2731) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                                 |  
| [MS10-063](http://go.microsoft.com/fwlink/?linkid=200378) | Vulnerabilità legata al danneggiamento della memoria del motore di analisi dei caratteri Uniscribe                       | [CVE-2010-2738](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2738) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                  |  
| [MS10-064](http://go.microsoft.com/fwlink/?linkid=200727) | Vulnerabilità legata all'overflow del buffer basato su heap in Outlook                                                   | [CVE-2010-2728](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2728) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                  |  
| [MS10-065](http://go.microsoft.com/fwlink/?linkid=199537) | Vulnerabilità legata all'overflow del buffer per le intestazioni delle richieste                                         | [CVE-2010-2730](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2730) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                  |  
| [MS10-065](http://go.microsoft.com/fwlink/?linkid=199537) | Vulnerabilità legata ad attacchi di tipo Denial of Service in IIS dovuta alla ripetizione dei parametri di una richiesta | [CVE-2010-1899](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1899) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta solo di una vulnerabilità ad attacchi di tipo Denial of Service                                  |
  
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
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=93faba6b-0a85-4acc-b527-a012bbf56b13)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2084a01c-2a91-4650-8665-7053015f2083)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a1d47f30-c1fc-4b9d-8829-3bad1224006a)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=555864c3-9114-4988-8526-7bf545a27706)  
(KB2124261)  
(Importante)  
Autenticazione IIS:  
[Internet Information Services 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=ae55787e-4a5c-48d5-aedf-0abada514938)  
(KB2290570)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7ad0f2cf-03dc-49a0-a16e-17fed0c01cc6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fc4369ec-864a-42ae-a850-b006872241fe)  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=6554f98f-4dc5-4784-b92c-b0aae1fa22ca)  
(KB982000)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=20091358-7127-4ace-bf96-4319461ad305)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3d31fd37-eb58-4169-b6b9-4cf854524e46)  
(KB2418241)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d284237b-e4d9-460a-98f0-7a18252f5780)  
(KB2416468)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9f7f3737-056d-44bd-b644-51093b5b501b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=284a0e80-fd03-4909-b354-0478f04585a1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b27f310f-6ecc-4abb-8944-9fc24c66e077)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=0b28bfac-783d-4c89-988b-4123c0343855)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3349b12b-621e-48bc-9c57-489c7a56920d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7567986a-261d-4def-9fa5-c667994c7844)  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=5bc00f9a-3028-4c9d-be06-f2b78fa444c4)  
(KB982000)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=107eb958-b60f-40ae-a785-5d5b4d13d8c6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3d31fd37-eb58-4169-b6b9-4cf854524e46)  
(KB2418241)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d284237b-e4d9-460a-98f0-7a18252f5780)  
(KB2416468)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3d79680b-c071-462f-9cea-551fbd42edf0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0a942985-081f-455c-bf9d-4345392c91b0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7ff7de2f-3e37-4aff-a8e4-5ed21b83575c)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=29e6cf4f-446b-461c-82f7-cfa8478cf739)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f8b3004b-07db-4638-a9b7-224ff829081c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3290e7ee-1e4a-464c-abfd-17fc4108601e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=3fe6e78c-c60a-4903-9273-27b37e129f0a)  
(KB981550)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=c42731f1-6393-42ed-b59f-5310c832fdc4)  
(KB982000)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fd46ba66-8ca1-4aa2-b91b-9e5861a173f7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=71f0daad-e2df-421c-9818-58e1e40cdb65)  
(KB2416451)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3d31fd37-eb58-4169-b6b9-4cf854524e46)  
(KB2418241)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d284237b-e4d9-460a-98f0-7a18252f5780)  
(KB2416468)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=073b3305-4a81-4ef8-b6aa-e53b31a936b4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=284a0e80-fd03-4909-b354-0478f04585a1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8382c1f2-e16d-475c-a8a0-e378696808f1)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=750e4a79-11bf-4726-9eb4-5dd3d029a717)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=612b2096-bd82-47ca-8b99-454c2f158d39)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b21570cc-4f90-4ed8-b901-a34584d44a63)  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=22412eed-33cd-4dfc-8ef7-b74dcd7c5faf)  
(KB981550)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=79fb639d-2cc1-4bea-9df6-c67ed95890e3)  
(KB982000)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ff5976e0-579c-4e6e-a225-c0d3913cdc85)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3d31fd37-eb58-4169-b6b9-4cf854524e46)  
(KB2418241)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d284237b-e4d9-460a-98f0-7a18252f5780)  
(KB2416468)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ca35a520-c4da-41bb-abcc-d5bc534ff19a)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=be7b3310-ffb7-4528-9c9e-aebe14d264d6)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=f6841057-1745-44e9-a16a-c180dd941ddf)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1f04f151-330a-4b6c-826e-76def35daa73)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c9c4427d-54c8-4f3c-9a94-818196cd5180)  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=cab75c8a-0d12-4a91-82b2-9f9b70610f67)  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=e450ca08-1d75-4419-ad9f-c5e5efb55cd5)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3d31fd37-eb58-4169-b6b9-4cf854524e46)  
(KB2418241)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=d284237b-e4d9-460a-98f0-7a18252f5780)  
(KB2416468)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
Nessuno
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
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=028977fd-0f39-42d4-9fee-0d90a2931cfd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=84629c25-7827-40c1-86fb-7ffa247202a0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ac1b0260-3802-45d4-985e-ac827d784e4f)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=75059175-9c59-45d5-81ce-09b964640e5f)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Solo Windows Vista Service Pack 2:  
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=853a71f3-fb0d-43af-a2b8-45bf8ca1a588)  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)  
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=7ad59265-9dca-4731-ac09-46c162c1832a)  
(KB2416469)  
(Importante)  
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac1c77df-34d5-48d4-9a9d-33dc017ffe93)  
(KB2416474)  
(Importante)  
Solo Windows Vista Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2, Microsoft .NET Framework 3.5 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=45aa5666-3454-443c-a224-2076215fef04)  
(KB2416470)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c68b9337-883d-4e98-ba0a-90b5cad46184)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=36e2a74b-e5c6-47d5-9cd9-b9171be63c7d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ebfdcd6d-413e-4359-8863-e992327a607f)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=9864c590-10a7-4971-a717-924ed0d6cace)  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition Service Pack 2:  
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=566f468b-22b6-400a-a656-ae64cfcb52df)  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=7ad59265-9dca-4731-ac09-46c162c1832a)  
(KB2416469)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac1c77df-34d5-48d4-9a9d-33dc017ffe93)  
(KB2416474)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2, Microsoft .NET Framework 3.5 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=45aa5666-3454-443c-a224-2076215fef04)  
(KB2416470)  
(Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
Nessuno
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
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e2e788de-8400-4bf6-b96b-a915154aa20a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fdfc393e-a54d-44dd-ba45-c2a550ffd2a1)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b679fe0c-5498-4fc5-84c8-0cd24b625907)\*  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=d798dc8e-ae64-4a1d-abda-f58cf69779d8)\*  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=1452befe-b7b8-4131-b36f-dded2bd16d5e)\*  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)\*\*  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)\*\*  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)\*\*  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)\*\*<sup>[1]</sup>
(KB2416472)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=7ad59265-9dca-4731-ac09-46c162c1832a)\*\*  
(KB2416469)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac1c77df-34d5-48d4-9a9d-33dc017ffe93)\*\*  
(KB2416474)  
(Importante)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2, Microsoft .NET Framework 3.5 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=45aa5666-3454-443c-a224-2076215fef04)\*\*  
(KB2416470)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e08d4f49-5a13-4e1d-b0a7-27b314c2edb5)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1b7af424-6286-4a80-827c-c4df4f92fe43)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e1b38b87-24f6-4aaa-afa9-40f4015d6694)\*  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=e29f01dc-b00d-4c12-a13e-63aa0b09d919)\*  
(KB2124261)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=38eb875f-1869-401b-b7d3-9f18f4ba4f24)\*  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)\*\*  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)\*\*  
(KB2418240)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)\*\*  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)\*\*<sup>[1]</sup>
(KB2416472)  
(Importante)  
Windows Server 2008 solo per sistemi x64:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=7ad59265-9dca-4731-ac09-46c162c1832a)\*\*  
(KB2416469)  
(Importante)  
Windows Server 2008 solo per sistemi x64:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac1c77df-34d5-48d4-9a9d-33dc017ffe93)\*\*  
(KB2416474)  
(Importante)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2, Microsoft .NET Framework 3.5 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=45aa5666-3454-443c-a224-2076215fef04)\*\*  
(KB2416470)  
(Importante)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2:  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=00d95a85-f3e8-464d-a10c-85c6d91b4aae)\*\*  
(KB2418240)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=098537d5-bf6e-4e04-ad33-1cde697e062f)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ceb856e8-f4a6-4229-bd26-b1a763d7d443)  
(KB981322)  
(Critico)
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=d595c8d2-90b1-46e4-bb9f-60efd0bf3a02)  
(KB2124261)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7990e61-21fd-4942-9dfe-af7961cb0282)  
(KB2416447)  
(Importante)  
[Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ae42d6cc-6d4e-425a-9b4f-379f66fc506a)  
(KB2416473)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)  
Windows Server 2008 per sistemi Itanium soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=7ad59265-9dca-4731-ac09-46c162c1832a)  
(KB2416469)  
(Importante)  
Windows Server 2008 per sistemi Itanium soltanto:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac1c77df-34d5-48d4-9a9d-33dc017ffe93)  
(KB2416474)  
(Importante)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2, Microsoft .NET Framework 3.5 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=45aa5666-3454-443c-a224-2076215fef04)  
(KB2416470)  
(Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
<td style="border:1px solid black;">
Nessuno
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
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=34619e9e-1f00-40e4-be6f-5bbf5e3c801b)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=5b2d42da-4dbc-4fbb-be22-09ca7dec5aa3)  
(KB2124261)  
(Importante)  
IIS FastCGI:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=c843afd9-b6f2-48de-91cc-1c0d481c2be4)  
(KB2271195)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=454fc025-bfa2-4552-9522-3585f523ecb2)  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5e7dcf51-74f1-43cc-aece-0cd5df05ddb7)  
(KB2416471)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
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
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=dbb747a5-658d-44cf-bd49-425d1700157f)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=66b64374-95e4-4b99-80e6-98dc63cd272b)  
(KB2124261)  
(Importante)  
IIS FastCGI:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=5f0c0454-cbb6-47ed-9227-98aa45b8cbdb)  
(KB2271195)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=b15ad533-3cf1-4dcf-847c-05ebffb84e26)  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5e7dcf51-74f1-43cc-aece-0cd5df05ddb7)  
(KB2416471)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472) (Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
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
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472) (Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-061**](http://go.microsoft.com/fwlink/?linkid=200505)
</td>
<td style="border:1px solid black;">
[**MS10-062**](http://go.microsoft.com/fwlink/?linkid=190884)
</td>
<td style="border:1px solid black;">
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-065**](http://go.microsoft.com/fwlink/?linkid=199537)
</td>
<td style="border:1px solid black;">
[**MS10-066**](http://go.microsoft.com/fwlink/?linkid=197105)
</td>
<td style="border:1px solid black;">
[**MS10-067**](http://go.microsoft.com/fwlink/?linkid=197102)
</td>
<td style="border:1px solid black;">
[**MS10-068**](http://go.microsoft.com/fwlink/?linkid=190509)
</td>
<td style="border:1px solid black;">
[**MS10-069**](http://go.microsoft.com/fwlink/?linkid=197093)
</td>
<td style="border:1px solid black;">
[**MS10-070**](http://go.microsoft.com/fwlink/?linkid=202409)
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
<td style="border:1px solid black;">
Nessuno
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
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=11e20088-1be2-4166-9c97-234b7e9f1c4f)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=21458cce-f67e-4e95-a067-8311afefc261)\*  
(KB2124261)  
(Importante)  
IIS FastCGI:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=9578b1de-f2c1-4b37-9d82-69e929cab6f3)\*  
(KB2271195)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=54f36389-8be4-4a0c-9640-dc32addac9d7)\*  
(KB981550)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5e7dcf51-74f1-43cc-aece-0cd5df05ddb7)\*  
(KB2416471)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
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
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)\*<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d8c635f8-8978-44bf-b457-e07368f08ef4)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
IIS ASP:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=3b8f3fd1-1ef4-4e9f-9bce-0c68f10519d1)  
(KB2124261)  
(Importante)  
IIS FastCGI:  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=21adf80d-267f-47cd-9c03-4b4854ba159f)  
(KB2271195)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5e7dcf51-74f1-43cc-aece-0cd5df05ddb7)  
(KB2416471)  
(Importante)  
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
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
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=6ce703b7-08a5-4eff-a062-d5dc720908f6)<sup>[1]</sup>
(KB2416472)  
(Importante)
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS10-063**

Vedere ulteriori categorie software nella sezione Software interessato e percorsi per il download, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS10-070**

<sup>[1]</sup>**.NET Framework 4.0 Client Profile non interessato.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4.0 e .NET Framework 4.0 Client Profile. .Net NET Framework 4.0 Client Profile è un sottoinsieme di .NET Framework 4.0. La vulnerabilità risolta in questo aggiornamento interessa solo .NET Framework 4.0 e non .NET Framework 4.0 Client Profile. Per ulteriori informazioni, vedere: [Installare .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

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
[**MS10-063**](http://go.microsoft.com/fwlink/?linkid=200378)
</td>
<td style="border:1px solid black;">
[**MS10-064**](http://go.microsoft.com/fwlink/?linkid=200727)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0b56f85f-d39b-410a-857a-799a5d714de7)  
(KB2288608)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d5e85841-9dea-4776-9e0e-3cd272066f37)  
(KB2293422)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=bb7783b1-b396-4254-b317-f2292b305cfc)  
(KB2288613)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ec8ed81e-05d0-4c20-b5fb-ebc72230a8bd)  
(KB2293428)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=44c5bccf-66dd-4796-9089-e6171d8c9785)  
(KB2288621)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6009d507-135c-4ce8-a830-925134f214dc)  
(KB2288953)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS10-063**

Vedere ulteriori categorie software nella sezione Software interessato e percorsi per il download, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

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

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/it-it/windowsserver/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/collaboration/mapppartners.aspx).

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

-   Sergey Golovanov, Alexander Gostev, Maxim Golovkin e Alexey Monastyrsky di [Kaspersky Lab](http://www.kaspersky.com/) e Vitaly Kiktenko e Alexander Saprykin di [Design and Test Lab](http://www.dnt-lab.com/) per aver segnalato un problema descritto nel bollettino MS10-061
-   Liam O Morchu di [Symantec](http://www.symantec.com/index.jsp) per aver segnalato un problema descritto nel bollettino MS10-061
-   Matthew Watchinski di [Sourcefire VRT](http://www.sourcefire.com/services/sf_vrt.html) per aver segnalato un problema descritto nel bollettino MS10-062
-   Carsten Book di per aver segnalato un problema descritto nel bollettino MS10-063
-   Marc Schoenefeld del Red Hat Security Response Team per aver segnalato un problema descritto nel bollettino MS10-063
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver segnalato informazioni che hanno portato a una modifica dell'Exploitability Index per CVE-2010-2738 nel bollettino MS10-063
-   Dyon Balding di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS10-064
-   Jinsik Shim per aver segnalato un problema descritto nel bollettino MS10-065
-   Travis Raybold di Rubicon West per aver segnalato un problema descritto nel bollettino MS10-065
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS10-066
-   S0lute di [iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS10-067
-   [IBM Giappone](http://www.ibm.com/jp/ja/) per aver segnalato un problema descritto nel bollettino MS10-069

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 settembre 2010): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (22 settembre 2010): È stato alzato il livello di valutazione dell'Exploitability Index per CVE-2010-2738, abbassato per CVE-2010-2730 ed è stata rivista la nota fondamentale dell'Exploitability Index per CVE-2010-0818.
-   V3.0 (28 settembre 2010): È stato aggiunto il bollettino Microsoft sulla sicurezza MS10-070, Una vulnerabilità in ASP.NET può consentire l'intercettazione di informazioni personali (2418042). È stato inoltre aggiunto il collegamento al webcast del bollettino relativo al presente bollettino straordinario sulla sicurezza.
-   V4.0 (30 settembre 2010): Questo riepilogo dei bollettini è stato rivisto per comunicare che gli aggiornamenti per MS10-070 sono ora disponibili attraverso tutti i canali di distribuzione, inclusi Windows Update e Microsoft Update. Inoltre, sono stati rivisti i dettagli degli aggiornamenti KB2418240, KB2418241, KB2416470 e KB2416474 per MS10-070.
-   V4.1 (3 novembre 2010): Per MS10-070, è stata aggiunta una nota alla tabella Software interessato per chiarire che .NET Framework 4.0 Client Profile non è interessato.
-   V5.0 (14 dicembre 2010): Questo riepilogo dei bollettini è stato rivisto per comunicare che per MS10-070 sono disponibili i nuovi pacchetti di aggiornamento per .NET Framework 4.0 (KB2416472) per correggere un problema nell'installazione che potrebbe impedire la corretta installazione di altri aggiornamenti e/o prodotti. I clienti che hanno già aggiornato i propri sistemi non devono eseguire ulteriori operazioni.
-   V6.0 (22 febbraio 2011): Per MS10-070, una modifica di rilevamento offre ora i pacchetti di aggiornamento .NET Framework 4.0 di Microsoft (KB2416472) ai clienti che installano .NET Framework 4.0 di Microsoft dopo aver installato Windows 7 per i sistemi a 32 bit Service Pack 1, Windows 7 per i sistemi x64 Service Pack 1, Windows Server 2008 R2 per i sistemi x64 Service Pack 1 o Windows Server 2008 R2 per i sistemi Itanium Service Pack 1. I clienti che con successo hanno aggiornato già i loro sistemi non devono effettuare alcuna operazione.
-   V6.1 (26 ottobre 2011): per MS10-070 è stata corretta l'applicabilità dell'installazione Server Core per .NET Framework 4 in Windows Server 2008 R2 per i sistemi x64.

*Built at 2014-04-18T01:50:00Z-07:00*
