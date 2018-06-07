---
TOCTitle: 'MS12-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2012'
ms:assetid: 'ms12-oct'
ms:contentKeyID: 61240076
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms12-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2012
=================================================================

Data di pubblicazione: martedì 9 ottobre 2012 | Aggiornamento: martedì 23 ottobre 2012

**Versione:** 1.3

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in ottobre 2012.

Con il rilascio dei bollettini sulla sicurezza di ottobre 2012, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 4 ottobre 2012. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 10 ottobre 2012 alle 11:00 Ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522558&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522558&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260965">MS12-064</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Word possono consentire l'esecuzione di codice in modalità remota (2742319)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Office. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota se un utente apre o visualizza in anteprima un file RTF appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263959">MS12- 065</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Works</strong> <strong>può consentire l'esecuzione di codice in modalità remota</strong> <strong>(2754670)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Works. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file di Microsoft Word appositamente predisposto usando Microsoft Works. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260957">MS12-066</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità legata alla disinfezione del contenuto HTML può consentire l'acquisizione di privilegi più elevati (2741517)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Office, nelle piattaforme delle comunicazioni Microsoft, nel software dei server Microsoft e in Microsoft Office Web Apps. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato invia contenuto appositamente predisposto a un utente.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft,<br />
Microsoft Lync</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=259736">MS12-067</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nell'analisi di FAST Search Server 2010 for SharePoint possono consentire l'esecuzione di codice in modalità remota (2742321)</strong><br />
<br />
Questo aggiornamento per la protezione risolve alcune vulnerabilità divulgate pubblicamente in Microsoft FAST Search Server 2010 per SharePoint. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota nel contesto di protezione di un account utente con un token limitato. FAST Search Server per SharePoint è interessato da questo problema solo quando è attivato Advanced Filter Pack. Per impostazione predefinita, Advanced Filter Pack è disattivato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257912">MS12-068</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del kernel di Windows può consentire l'acquisizione di privilegi più elevati (2724197)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in tutte le versioni supportate di Microsoft Windows eccetto Windows 8 e Windows Server 2012. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP, Windows Server 2003, Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2.<br />
<br />
La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263962">MS12-069</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Kerberos può consentire un attacco di tipo Denial of Service (2743555)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia una richiesta di sessione appositamente predisposta al server Kerberos. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale. È consigliabile che i sistemi connessi a Internet abbiano un numero minimo di porte esposte.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263997">MS12-070</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in SQL Server può consentire l'acquisizione di privilegi più elevati (2754849)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft SQL Server nei sistemi che eseguono SQL Server Reporting Services (SSRS). Questa è una vulnerabilità di cross-site scripting (XSS) che potrebbe consentire l'acquisizione di privilegi più elevati, consentendo a un utente malintenzionato di eseguire comandi non autorizzati sul sito SSRS nel contesto dell'utente designato. Un utente malintenzionato potrebbe sfruttare questa vulnerabilità inviando un collegamento appositamente predisposto all'utente e convincendolo a fare clic sul collegamento. Un utente malintenzionato può anche pubblicare un sito Web contenente una pagina Web progettata per sfruttare la vulnerabilità. Inoltre, i siti Web manomessi e quelli che accettano o ospitano contenuti o annunci pubblicitari forniti dagli utenti potrebbero presentare contenuti appositamente predisposti per sfruttare questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft SQL Server</td>
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
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione meno recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260965">MS12-064</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della sezione PAPX di Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0182">CVE-2012-0182</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260965">MS12-064</a></td>
<td style="border:1px solid black;">Vulnerabilità di tipo Use-After-Free nella proprietà listid dei file RTF</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2528">CVE-2012-2528</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263959">MS12- 065</a></td>
<td style="border:1px solid black;">Vulnerabilità legata agli heap in Works</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2550">CVE-2012-2550</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260957">MS12-066</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla disinfezione del contenuto HTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2520">CVE-2012-2520</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=259736">MS12-067</a></td>
<td style="border:1px solid black;">Advanced Filter Pack for FAST Search Server 2010 for SharePoint contiene più vulnerabilità sfruttabili</td>
<td style="border:1px solid black;">Oracle Outside In contiene più vulnerabilità sfruttabili</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">*Vulnerabilità multiple, vedere il bollettino MS12-067 per ulteriori dettagli.<br />
<br />
Queste vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=257912">MS12-068</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer nel kernel di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2529">CVE-2012-2529</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263962">MS12-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento di un puntatore NULL in Kerberos</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2551">CVE-2012-2551</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=263997">MS12-070</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al filtro XSS riflesso</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2552">CVE-2012-2552</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
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

 
<table style="border:1px solid black;">
<tr>
<th colspan="3">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6aa1e4b3-273a-49ff-8086-0d2c16dd14f3)  
(KB2724197)  
(Importante)
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
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3c509cc0-63a1-4cc7-b7f9-cc9f0f12b378)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6c7dd00a-a983-477b-88b1-dc16f1b5e42a)  
(KB2724197)  
(Importante)
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
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eaac4dae-62e6-4020-8b4d-a95e7e0e11f1)  
(KB2724197)  
(Importante)
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
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=315cc115-1496-471f-8887-f334a1ca8246)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=828ca8a2-777c-4b41-8d97-caed894a37cb)  
(KB2724197)  
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
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=731d67dc-e028-42e4-8ef3-454f74835593)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=526f786b-7aef-4a1f-b03d-587baadf3f5b)  
(KB2724197)  
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
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5697076c-541f-42b7-8dc3-e8bd4a25fda8)  
(KB2724197)  
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
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6216b875-c7a6-4d62-8062-49996ac7a478)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=593a29c3-c459-4a39-9f25-016a5268fc7d)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=4ffa9c0e-26b1-4309-bfb4-fa5374f28d6c)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=593a29c3-c459-4a39-9f25-016a5268fc7d)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4ffa9c0e-26b1-4309-bfb4-fa5374f28d6c)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=2d273f99-3460-4e84-9f2d-2a349bfc7ce6)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=d5584b7d-434f-49fc-9c30-ef16c40d475f)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2d273f99-3460-4e84-9f2d-2a349bfc7ce6)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d5584b7d-434f-49fc-9c30-ef16c40d475f)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=848af16d-c5f7-4a70-b6a9-39f4e7999f1f)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=d7210047-788c-4b33-953d-e3134f52f897)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=848af16d-c5f7-4a70-b6a9-39f4e7999f1f)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d7210047-788c-4b33-953d-e3134f52f897)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ded1f351-022a-463c-9f5f-84b6081e6173)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=7dc47f1d-8af8-4f31-9f96-3ae226632723)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ded1f351-022a-463c-9f5f-84b6081e6173)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7dc47f1d-8af8-4f31-9f96-3ae226632723)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-068**](http://go.microsoft.com/fwlink/?linkid=257912)
</td>
<td style="border:1px solid black;">
[**MS12-069**](http://go.microsoft.com/fwlink/?linkid=263962)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=526f786b-7aef-4a1f-b03d-587baadf3f5b) (installazione Server Core)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5697076c-541f-42b7-8dc3-e8bd4a25fda8) (installazione Server Core)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 (installazione Server Core)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=848af16d-c5f7-4a70-b6a9-39f4e7999f1f) (installazione Server Core)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=d7210047-788c-4b33-953d-e3134f52f897) (installazione Server Core)  
(KB2743555)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=848af16d-c5f7-4a70-b6a9-39f4e7999f1f) (installazione Server Core)  
(KB2724197)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d7210047-788c-4b33-953d-e3134f52f897) (installazione Server Core)  
(KB2743555)  
(Importante)
</td>
</tr>
</table>
 

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12- 065**](http://go.microsoft.com/fwlink/?linkid=263959)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
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
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e49eadec-0fe1-43ce-9c25-a92aad17d940)  
(KB2687483)  
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
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Word 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=be58b650-ee4f-405e-ab3c-c28aca48345b)<sup>[1]</sup>
(KB2687315)  
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
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Word 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=be58b650-ee4f-405e-ab3c-c28aca48345b)<sup>[1]</sup>
(KB2687315)  
(Critico)
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
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=27e07115-d569-438c-b95f-203e444d4408)  
(KB2553488)  
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
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=30f9efac-3ecd-48a6-adcf-922f4d4d18d4)  
(KB2553488)  
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
<th colspan="4">
Altro software Microsoft Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12- 065**](http://go.microsoft.com/fwlink/?linkid=263959)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Word Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=1e392ff8-92e9-408d-bb14-1e0a6b4b6c9d)  
(KB2687485)  
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
Pacchetto di compatibilità Microsoft Office Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=301446f7-991e-4abd-a06e-4a854f05ac84)  
(KB2687314)  
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
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=301446f7-991e-4abd-a06e-4a854f05ac84)  
(KB2687314)  
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
Microsoft InfoPath 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a0989a9f-3a7a-4343-9dd0-b2d694a0813b)  
(KB2687439)  
(Importante)  
[Microsoft InfoPath 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29330e1a-6bac-4c54-98ef-b9a831801247)  
(KB2687440)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft InfoPath 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a0989a9f-3a7a-4343-9dd0-b2d694a0813b)  
(KB2687439)  
(Importante)  
[Microsoft InfoPath 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=29330e1a-6bac-4c54-98ef-b9a831801247)  
(KB2687440)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft InfoPath 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=724b12b9-84bf-4102-912e-56aa9ee0878c)  
(KB2687436)  
(Importante)  
[Microsoft InfoPath 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=b0be62c6-4eae-458e-8cf5-754742393e4c)  
(KB2687417)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft InfoPath 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft InfoPath 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=17b36fa3-9964-480a-bff8-b028619c5dfd)  
(KB2687436)  
(Importante)  
[Microsoft InfoPath 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=6e5a7817-345e-4b75-aeca-94f74691c0e0)  
(KB2687417)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works 9
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Works 9](http://www.microsoft.com/downloads/details.aspx?familyid=7e48cd96-4b91-4f7b-b8a0-2b88131ba51d)  
(KB2754670)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Noteper MS12-064**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

<sup>[1]</sup>Per Microsoft Office Word 2007, oltre al pacchetto di aggiornamento per la protezione KB2687315, i clienti devono installare anche l'aggiornamento per la protezione per il pacchetto di compatibilità Microsoft Office (KB2687314) per essere protetti dalle vulnerabilità descritte in questo bollettino.

**Nota** **per** **MS12-066**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Microsoft SharePoint Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
</td>
<td style="border:1px solid black;">
[**MS12-067**](http://go.microsoft.com/fwlink/?linkid=259736)
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2007 Service Pack 2 (coreserver) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a8a818bb-67a3-4558-aac1-aaa33c6f4584)<sup>[1]</sup>
(KB2687405)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2007 Service Pack 3 (coreserver) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a8a818bb-67a3-4558-aac1-aaa33c6f4584)<sup>[1]</sup>
(KB2687405)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2007 Service Pack 2 (coreserver) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=93f4e385-880a-4edc-9cde-24f38a11a41d)<sup>[1]</sup>
(KB2687405)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2007 Service Pack 3 (coreserver) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=93f4e385-880a-4edc-9cde-24f38a11a41d)<sup>[1]</sup>
(KB2687405)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Word Automation Services](http://www.microsoft.com/downloads/details.aspx?familyid=3582ab6c-930b-4660-afcd-e2423ce56d8f)  
(KB2598237)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2010 Service Pack 1 (wosrv)](http://www.microsoft.com/downloads/details.aspx?familyid=af3ade8e-349f-4eec-a5c3-c5a70071582d)  
(KB2687435)  
(Importante)  
[Microsoft SharePoint Server 2010 Service Pack 1 (coreserver)](http://www.microsoft.com/downloads/details.aspx?familyid=5518b70b-cac9-4aff-b049-156d3c08b04b)  
(KB2589280)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Microsoft FAST Search Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
</td>
<td style="border:1px solid black;">
[**MS12-067**](http://go.microsoft.com/fwlink/?linkid=259736)
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft FAST Search Server 2010 per SharePoint
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Advanced Filter Pack](http://www.microsoft.com/downloads/details.aspx?familyid=17909d1f-c679-4a20-b39d-b99f9cc7dbc1)  
(KB2553402)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Groove Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
</td>
<td style="border:1px solid black;">
[**MS12-067**](http://go.microsoft.com/fwlink/?linkid=259736)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Groove Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Groove Server 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=80552d2c-98f2-4c99-bfc6-e091fd1d51c4)  
(KB2687402)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Windows SharePoint Services e Microsoft SharePoint Foundation
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
</td>
<td style="border:1px solid black;">
[**MS12-067**](http://go.microsoft.com/fwlink/?linkid=259736)
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
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=e3a31cd4-bba3-4572-ab24-7b1dd0c4c01c)  
(KB2687356)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=e3a31cd4-bba3-4572-ab24-7b1dd0c4c01c)  
(KB2687356)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versione a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versione a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=77cab67c-be97-4808-9fb4-4defad563851)  
(KB2687356)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=77cab67c-be97-4808-9fb4-4defad563851)  
(KB2687356)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Foundation 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=79724c7c-7cdf-44c9-9e25-577104c5004b)  
(KB2687434)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Office Web Apps
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-064**](http://go.microsoft.com/fwlink/?linkid=260965)
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
</td>
<td style="border:1px solid black;">
[**MS12-067**](http://go.microsoft.com/fwlink/?linkid=259736)
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office Web Apps 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e7a2dd61-36d5-4313-a8dc-15456b275b9c)  
(KB2687401)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Web Apps 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e7a2dd61-36d5-4313-a8dc-15456b275b9c)  
(KB2687401)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS12-064**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Noteper MS12-066**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

<sup>[1]</sup>Per le edizioni supportate di Microsoft SharePoint Server 2007, oltre al pacchetto di aggiornamento per la protezione per Microsoft SharePoint 2007 (KB2687405), i clienti devono installare anche l'aggiornamento per la protezione di Microsoft Windows SharePoint Services 3.0 (KB2687356) per essere protetti dalle vulnerabilità descritte in questo bollettino.

#### Piattaforme e servizi delle comunicazioni Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Communicator
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
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
[Microsoft Communicator 2007 R2](http://www.microsoft.com/downloads/details.aspx?familyid=a228c1dd-9e57-48cb-8db4-896d6c499b46)  
(KB2726391)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Lync
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-066**](http://go.microsoft.com/fwlink/?linkid=260957)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 (32-bit)
</td>
<td style="border:1px solid black;">
[Microsoft Lync 2010 (32-bit)](http://www.microsoft.com/downloads/details.aspx?familyid=6ea3afea-baa2-4b74-9747-8051c544ddf7)  
(KB2726382)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64-bit)
</td>
<td style="border:1px solid black;">
[Microsoft Lync 2010 (64-bit)](http://www.microsoft.com/downloads/details.aspx?familyid=670c20e6-4f26-47b9-b6e0-25f195bf7000)  
(KB2726382)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee
</td>
<td style="border:1px solid black;">
[Microsoft Lync 2010 Attendee](http://www.microsoft.com/downloads/details.aspx?familyid=7f98cb55-027a-40bf-b539-d8fa38ffcc83)  
(installazione a livello amministratore)  
(KB2726388)  
(Importante)  
[Microsoft Lync 2010 Attendee](http://www.microsoft.com/downloads/details.aspx?familyid=32860684-998e-4e55-b719-c44532bc753d)<sup>[1]</sup>
(installazione a livello utente)  
(KB2726384)  
(Importante)
</td>
</tr>
</table>
 
**Noteper MS12-066**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

<sup>[1]</sup>Questo aggiornamento è disponibile soltanto nell'Area download Microsoft.

#### Microsoft SQL Server

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
SQL Server 2000
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-070**](http://go.microsoft.com/fwlink/?linkid=263997)
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
Microsoft SQL Server 2000 Reporting Services Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2000 Reporting Services Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1c70a2cb-e8a9-439f-b34a-7d1641daf325)  
(KB983814)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
SQL Server 2005
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-070**](http://go.microsoft.com/fwlink/?linkid=263997)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=623841cc-06f7-4475-b2c0-531aed9972a3)<sup>[1]</sup>
(GDR)  
(KB2716429)  
(Importante)  
[Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=16cc7b80-ea4c-4b17-9ac2-250b771a569a)<sup>[1]</sup>
(QFE)  
(KB2716427)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi a 32 bit Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi a 32 bit Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=623841cc-06f7-4475-b2c0-531aed9972a3)<sup>[1]</sup>
(GDR)  
(KB2716429)  
(Importante)  
[Microsoft SQL Server 2005 per sistemi a 32 bit Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=16cc7b80-ea4c-4b17-9ac2-250b771a569a)<sup>[1]</sup>
(QFE)  
(KB2716427)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi x64 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi x64 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=623841cc-06f7-4475-b2c0-531aed9972a3)<sup>[1]</sup>
(GDR)  
(KB2716429)  
(Importante)  
[Microsoft SQL Server 2005 per sistemi x64 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=16cc7b80-ea4c-4b17-9ac2-250b771a569a)<sup>[1]</sup>
(QFE)  
(KB2716427)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2005 per sistemi Itanium Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2005 per sistemi Itanium Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=623841cc-06f7-4475-b2c0-531aed9972a3)<sup>[1]</sup>
(GDR)  
(KB2716429)  
(Importante)  
[Microsoft SQL Server 2005 per sistemi Itanium Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=16cc7b80-ea4c-4b17-9ac2-250b771a569a)<sup>[1]</sup>
(QFE)  
(KB2716427)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
SQL Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-070**](http://go.microsoft.com/fwlink/?linkid=263997)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1bf8dc30-2a90-4196-814c-717ccd74ea13)<sup>[1]</sup>
(GDR)  
(KB2716434)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d8b1b25-45ad-4f19-ba50-e77debf2b463)<sup>[1]</sup>
(QFE)  
(KB2716433)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=04621a83-c2e2-4a60-9198-10104372b120)<sup>[1]</sup>
(GDR)  
(KB2716436)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi a 32 bit Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4c4597d2-dea0-49b9-a5a9-a7771a3d64c0)<sup>[1]</sup>
(QFE)  
(KB2716435)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1bf8dc30-2a90-4196-814c-717ccd74ea13)<sup>[1]</sup>
(GDR)  
(KB2716434)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d8b1b25-45ad-4f19-ba50-e77debf2b463)<sup>[1]</sup>
(QFE)  
(KB2716433)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi x64 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=04621a83-c2e2-4a60-9198-10104372b120)<sup>[1]</sup>
(GDR)  
(KB2716436)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi x64 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4c4597d2-dea0-49b9-a5a9-a7771a3d64c0)<sup>[1]</sup>
(QFE)  
(KB2716435)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1bf8dc30-2a90-4196-814c-717ccd74ea13)<sup>[1]</sup>
(GDR)  
(KB2716434)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d8b1b25-45ad-4f19-ba50-e77debf2b463)<sup>[1]</sup>
(QFE)  
(KB2716433)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 per sistemi Itanium Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=04621a83-c2e2-4a60-9198-10104372b120)<sup>[1]</sup>
(GDR)  
(KB2716436)  
(Importante)  
[Microsoft SQL Server 2008 per sistemi Itanium Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4c4597d2-dea0-49b9-a5a9-a7771a3d64c0)<sup>[1]</sup>
(QFE)  
(KB2716435)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
SQL Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-070**](http://go.microsoft.com/fwlink/?linkid=263997)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=215a9184-71c5-41e6-b4d5-03602182a88f)<sup>[1]</sup>
(GDR)  
(KB2716440)  
(Importante)  
[Microsoft SQL Server 2008 R2 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cdc4fc03-dfba-41d4-b651-d7967a067eea)<sup>[1]</sup>
(QFE)  
(KB2716439)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=215a9184-71c5-41e6-b4d5-03602182a88f)<sup>[1]</sup>
(GDR)  
(KB2716440)  
(Importante)  
[Microsoft SQL Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cdc4fc03-dfba-41d4-b651-d7967a067eea)<sup>[1]</sup>
(QFE)  
(KB2716439)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=215a9184-71c5-41e6-b4d5-03602182a88f)<sup>[1]</sup>
(GDR)  
(KB2716440)  
(Importante)  
[Microsoft SQL Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cdc4fc03-dfba-41d4-b651-d7967a067eea)<sup>[1]</sup>
(QFE)  
(KB2716439)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
SQL Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-070**](http://go.microsoft.com/fwlink/?linkid=263997)
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
Microsoft SQL Server 2012 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2012 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=e79b4e5b-1549-4e76-afef-b771b432365b)<sup>[1]</sup>
(GDR)  
(KB2716442)  
(Importante)  
[Microsoft SQL Server 2012 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=ebfcb341-e240-4107-92f1-ab75cc28151a)<sup>[1]</sup>
(QFE)  
(KB2716441)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SQL Server 2012 per sistemi x64
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2012 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e79b4e5b-1549-4e76-afef-b771b432365b)<sup>[1]</sup>
(GDR)  
(KB2716442)  
(Importante)  
[Microsoft SQL Server 2012 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=ebfcb341-e240-4107-92f1-ab75cc28151a)<sup>[1]</sup>
(QFE)  
(KB2716441)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS12-070**

<sup>[1]</sup>Questo aggiornamento è offerto solo ai clienti che eseguono SQL Server Reporting Services (SSRS).

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS12-001"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

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

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

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

-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-064
-   Un ricercatore anonimo, che collabora con il programma [SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html) di Beyond Security per aver segnalato un problema descritto nel bollettino MS12-064
-   Drew Hintz e Andrew Lyons di [Google Security Team](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS12-066
-   Will Dorman di [CERT/CC](http://www.cert.org/) per aver collaborato con noi a 13 problemi descritti nel bollettino MS12-067
-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS12-068

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 ottobre 2012): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (10 ottobre 2012): Per MS12-068 e MS12-069, è stata corretta la valutazione dell'Exploitability per la versione più recente del software nell'**Exploitability Index**, rispettivamente per CVE-2012-2529 e CVE-2012-2551. Per MS12-066, sono stati corretti i numeri di KB per Microsoft Lync 2010 Attendee (installazione a livello amministratore) e Microsoft Lync 2010 Attendee (installazione a livello utente).
-   V1.2 (17 ottobre 2012): Per MS12-066, sono stati corretti i numeri di KB per Microsoft Lync 2010 Attendee (installazione a livello amministratore) e Microsoft Lync 2010 Attendee (installazione a livello utente).
-   V1.3 (23 ottobre 2012): Per MS12-066, sono stati aggiunti Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 32 bit) e Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versione a 64 bit) alla sezione **Software interessato** . La modifica è esclusivamente informativa. Non sono state apportate modifiche alla logica di rilevamento o ai file di aggiornamento della protezione.

*Built at 2014-04-18T01:50:00Z-07:00*
