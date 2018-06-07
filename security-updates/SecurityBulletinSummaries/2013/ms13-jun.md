---
TOCTitle: 'MS13-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2013'
ms:assetid: 'ms13-jun'
ms:contentKeyID: 61240084
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2013
================================================================

Data di pubblicazione: martedì 11 giugno 2013

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a giugno 2013.

Con il rilascio dei bollettini sulla sicurezza di giugno 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 6 giugno 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 12 giugno 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538733&culture=it-it). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538733&culture=it-it).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299498">MS13-047</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2838727)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve diciannove vulnerabilità in Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301748">MS13-048</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel kernel di Windows può consentire l'intercettazione di informazioni personali (2839229)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'intercettazione di informazioni personali se un utente malintenzionato accede a un sistema ed esegue un'applicazione appositamente predisposta o convince un utente connesso in locale a eseguire un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. Si noti che questa vulnerabilità non consente a un utente malintenzionato di eseguire codice o acquisire direttamente diritti utente più elevati, ma può essere utilizzata per produrre informazioni utili al fine di compromettere ulteriormente il sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301749">MS13-049</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei driver in modalità kernel può consentire un attacco di tipo Denial of Service (2845690)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire un attacco di tipo Denial of Service se un utente malintenzionato invia pacchetti appositamente predisposti al server. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299243">MS13-050</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità</strong> <strong>nei componenti dello spooler di stampa di Windows può consentire l'acquisizione di privilegi più elevati (2839894)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'acquisizione di privilegi più elevati quando un utente malintenzionato autenticato cancella una connessione alla stampante. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=296303">MS13-051</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office può consentire l'esecuzione di codice in modalità remota (2839571)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un documento Office appositamente predisposto che utilizza una versione interessata del software Microsoft Office o le anteprime oppure apre un messaggio di posta elettronica appositamente predisposto in Outlook mentre utilizza Microsoft Word come lettore di email. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
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
  
| ID bollettino                                             | Titolo della vulnerabilità                                                    | ID CVE                                                                           | Valutazione dell'Exploitability per la versione più recente del software                                              | Valutazione dell'Exploitability per la versione meno recente del software                                             | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali                                                                          |  
|-----------------------------------------------------------|-------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3110](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3110) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3111](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3111) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3112](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3112) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3113](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3113) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3114](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3114) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3116](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3116) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3117](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3117) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3118](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3118) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                       | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3119](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3119) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3120](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3120) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                       | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3121](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3121) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| MS13-047                                                  | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3122](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3122) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| MS13-047                                                  | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3123](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3123) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3124](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3124) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3125](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3125) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                       | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3139](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3139) | Non applicabile                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | Questa è una misura di difesa in profondità per il software più recente.                   |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3141](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3141) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-047](http://go.microsoft.com/fwlink/?linkid=299498) | Vulnerabilità legata al danneggiamento della memoria in internet Explorer     | [CVE-2013-3142](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3142) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                  |  
| [MS13-048](http://go.microsoft.com/fwlink/?linkid=301748) | Vulnerabilità legata all'intercettazione di informazioni personali nel kernel | [CVE-2013-3136](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3136) | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | Permanente                                                                       | Questa vulnerabilità riguarda l'intercettazione di informazioni personali.                 |  
| [MS13-049](http://go.microsoft.com/fwlink/?linkid=301749) | Vulnerabilità legata all'overflow di valori integer in TCP/IP                 | [CVE-2013-3138](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3138) | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | Permanente                                                                       | Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.                      |  
| [MS13-050](http://go.microsoft.com/fwlink/?linkid=299243) | Vulnerabilità legata allo spooler di stampa                                   | [CVE-2013-1339](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1339) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                  |  
| [MS13-051](http://go.microsoft.com/fwlink/?linkid=296303) | Vulnerabilità legata all'overflow del buffer in Office                        | [CVE-2013-1331](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1331) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità. |
  
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
<th colspan="5">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2838727)  
(Critico)  
Internet Explorer 7  
(2838727)  
(Critico)  
Internet Explorer 8  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2839229)  
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
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2838727)  
(Critico)  
Internet Explorer 7  
(2838727)  
(Critico)  
Internet Explorer 8  
(2838727)  
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
<th colspan="5">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2838727)  
(Moderato)  
Internet Explorer 7  
(2838727)  
(Moderato)  
Internet Explorer 8  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2839229)  
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
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2838727)  
(Moderato)  
Internet Explorer 7  
(2838727)  
(Moderato)  
Internet Explorer 8  
(2838727)  
(Moderato)
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
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2838727)  
(Moderato)  
Internet Explorer 7  
(2838727)  
(Moderato)
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
<th colspan="5">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2838727)  
(Critico)  
Internet Explorer 8  
(2838727)  
(Critico)  
Internet Explorer 9  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2839229)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2838727)  
(Critico)  
Internet Explorer 8  
(2838727)  
(Critico)  
Internet Explorer 9  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2838727)  
(Moderato)  
Internet Explorer 8  
(2838727)  
(Moderato)  
Internet Explorer 9  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2839229)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2838727)  
(Moderato)  
Internet Explorer 8  
(2838727)  
(Moderato)  
Internet Explorer 9  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2839894)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2838727)  
(Critico)  
Internet Explorer 9  
(2838727)  
(Critico)  
Internet Explorer 10  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2839229)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2839894)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2838727)  
(Critico)  
Internet Explorer 9  
(2838727)  
(Critico)  
Internet Explorer 10  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2838727)  
(Moderato)  
Internet Explorer 9  
(2838727)  
(Moderato)  
Internet Explorer 10  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2839894)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2839229)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2845690)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2839894)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2845690)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2838727)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2845690)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
(2838727)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows RT  
(2845690)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT  
(2839894)  
(Importante)
</td>
</tr>
<tr>
<th colspan="5">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-047**](http://go.microsoft.com/fwlink/?linkid=299498)
</td>
<td style="border:1px solid black;">
[**MS13-048**](http://go.microsoft.com/fwlink/?linkid=301748)
</td>
<td style="border:1px solid black;">
[**MS13-049**](http://go.microsoft.com/fwlink/?linkid=301749)
</td>
<td style="border:1px solid black;">
[**MS13-050**](http://go.microsoft.com/fwlink/?linkid=299243)
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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2839229)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2839894)  
(Importante)
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
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2839894)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2845690)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2839894)  
(Importante)
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
(2845690)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2839894)  
(Importante)
</td>
</tr>
</table>
 

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-051**](http://go.microsoft.com/fwlink/?linkid=296303)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3  
(2817421)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011  
(2848689)  
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

**MS13-047**

-   Scott Bell di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3110)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3111)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3112)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3113)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3114)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3116)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3117)
-   [Omair](http://krash.in/), che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3118)
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3119)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di[HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3120)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3121)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3122)
-   [Aniway.Aniway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in Internet Explorer (CVE-2013-3123)
-   [Omair](http://krash.in/), che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3124)
-   Amol Naik, che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3124)
-   [Omair](http://krash.in/), che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3125)
-   Amol Naik, che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3125)
-   [Aniway.Aniway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al debug dello script in Internet Explorer (CVE-2013-3126)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3141)
-   Toan Pham Van, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3142)

**MS13-048**

-   [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata all'intercettazione di informazioni nel kernel (CVE-2013-3136)

**MS13-051**

-   Andrew Lyons e Neel Mehta di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata all'overflow del buffer in Office (CVE-2013-1331)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 giugno 2013): Pubblicazione del riepilogo dei bollettini.
-   

*Built at 2014-04-18T01:50:00Z-07:00*
