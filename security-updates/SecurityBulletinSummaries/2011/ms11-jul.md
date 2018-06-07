---
TOCTitle: 'MS11-JUL'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2011'
ms:assetid: 'ms11-jul'
ms:contentKeyID: 61240059
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-jul(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2011
================================================================

Data di pubblicazione: martedì 12 luglio 2011

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a luglio 2011.

Con il rilascio dei bollettini sulla sicurezza di luglio 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 7 luglio 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 13 luglio 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di luglio](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032487855&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217102">MS11-053</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nello stack Bluetooth può consentire l'esecuzione di codice in modalità remota (2566220)</strong> <br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nello stack di Bluetooth di Windows. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente malintenzionato invia una serie di pacchetti Bluetooth appositamente predisposti a un sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Questa vulnerabilità interessa solo i sistemi dotati di funzionalità Bluetooth.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=220172">MS11-054</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2555917)</strong> <br />
<br />
Questo aggiornamento per la protezione risolve 15 vulnerabilità segnalate privatamente in Microsoft Windows. La più grave delle vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso localmente ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217465">MS11-056</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel sottosistema runtime client/server di Windows possono consentire l'acquisizione di privilegi più elevati (2507938) </strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità del sottosistema runtime client/server di Microsoft Windows (CSRSS) segnalate privatamente. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede a un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di sfruttare tali vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=220276">MS11-055</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Visio può consentire l'esecuzione di codice in modalità remota (2560847) </strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Visio. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file di Visio legittimo situato nella stessa directory di rete di un file della libreria appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
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
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                              | ID CVE                                                                           | Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software               | Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software              | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali                                                                                                                  |  
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|  
| [MS11-053](http://go.microsoft.com/fwlink/?linkid=217102) | Vulnerabilità nello stack Bluetooth                                                                     | [CVE-2011-1265](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1265) | Non interessato                                                                                                          | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | Questa vulnerabilità interessa solo i sistemi client (versioni supportate di Windows Vista e Windows 7) con funzionalità Bluetooth |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1874](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1874) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1875](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1875) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1876](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1876) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1877](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1877) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1878](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1878) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1879](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1879) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                      | [CVE-2011-1880](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1880) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                      | [CVE-2011-1881](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1881) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1882](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1882) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1883](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1883) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                       | [CVE-2011-1884](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1884) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                      | [CVE-2011-1885](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1885) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Il parametro errato Win32k causa una vulnerabilità legata all'intercettazione di informazioni personali | [CVE-2011-1886](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1886) | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | Permanente                                                                       | Questa vulnerabilità riguarda l'intercettazione di informazioni personali                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                      | [CVE-2011-1887](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1887) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-054](http://go.microsoft.com/fwlink/?linkid=220172) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                      | [CVE-2011-1888](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1888) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-055](http://go.microsoft.com/fwlink/?linkid=220276) | Vulnerabilità legata al caricamento di librerie non sicure in Microsoft Visio                           | [CVE-2010-3148](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3148) | Non interessato                                                                                                          | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Non applicabile                                                                  | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente                                                             |  
| [MS11-056](http://go.microsoft.com/fwlink/?linkid=217465) | Vulnerabilità AllocConsole locale di tipo EOP in CSRSS                                                  | [CVE-2011-1281](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1281) | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                                                                          |  
| [MS11-056](http://go.microsoft.com/fwlink/?linkid=217465) | Vulnerabilità SrvSetConsoleLocalEUDC locale di tipo EOP in CSRSS                                        | [CVE-2011-1282](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1282) | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-056](http://go.microsoft.com/fwlink/?linkid=217465) | Vulnerabilità SrvSetConsoleNumberOfCommand locale di tipo EOP in CSRSS                                  | [CVE-2011-1283](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1283) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-056](http://go.microsoft.com/fwlink/?linkid=217465) | Vulnerabilità SrvWriteConsoleOutput locale di tipo EOP in CSRSS                                         | [CVE-2011-1284](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1284) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |  
| [MS11-056](http://go.microsoft.com/fwlink/?linkid=217465) | Vulnerabilità SrvWriteConsoleOutputString locale di tipo EOP in CSRSS                                   | [CVE-2011-1870](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1870) | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                                                                          |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle?**
  
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
</tr>
<tr>
<th colspan="4">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d7a47370-f415-46ea-9a82-a943f743c8b6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=425c705e-94f2-4fa6-9df2-dc71897215fa)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=db89d88f-d0d4-4ed6-8589-bf27557c0304)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c389fa20-677e-49b6-af44-781e5522d08b)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7a26a437-a705-4d48-8389-50f159a39891)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dff4c67a-8c8b-4d7d-84c7-57429becf0ff)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=95393f89-0b05-4243-95ed-17bcdad24bfb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1615a995-9a04-440a-ae52-5917738f0ecb)  
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
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3b094bdb-4150-44f2-a638-afd5f41b00a3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=a81c011d-eeea-4383-9efb-df70515ab357)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6bff74ac-45f3-4585-92da-316921b458fa)<sup>[1]</sup>
(KB2561109)  
(Critico)  
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a1e5aa7d-5f38-4ce2-9575-4b4cb7520160)  
(KB2532531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c1fe1e53-34d5-497e-8ba2-50caa8dc1158)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a5e192af-dae5-47ef-a9d0-f761a8caa974)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=849d2694-c8b3-4670-8203-912661bccabf)<sup>[1]</sup>
(KB2561109)  
(Critico)  
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4287eeb4-ab29-4727-83f2-260d838b44d4)  
(KB2532531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7bc0a285-cc32-4c6b-abee-d92130d459b7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1007f5d3-9be1-4f03-a3f0-12ddb555653c)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b88d0471-4427-4835-9446-db71116481f0)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=36e3dbaf-36f5-4c74-8f11-ecbef46f58e1)\*  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d3df6184-3e3c-4949-a1ee-293ec68f8149)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b43d2ab5-e281-4c6b-bb37-1f1b5d86ac82)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9e021d69-7f0c-457f-af86-07e760d8f421)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b70209f2-1c51-45af-b3c4-3473aebcdb35)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7f811b75-c3ff-411a-aaa9-126dce34cc01)  
(KB2532531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=41db1b2f-f862-43bb-89bc-4b97737e5cb9)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ac3b435c-8caf-40cc-8f13-b52261b3b9e6)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=90b2da71-18f9-46ee-9e3d-b08620ca06aa)  
(KB2532531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=211abdc6-40c7-4bfc-8c2d-be72981f311e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=64e5f889-fa46-4884-9b22-3ba4e2fba1b9)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-053**](http://go.microsoft.com/fwlink/?linkid=217102)
</td>
<td style="border:1px solid black;">
[**MS11-054**](http://go.microsoft.com/fwlink/?linkid=220172)
</td>
<td style="border:1px solid black;">
[**MS11-056**](http://go.microsoft.com/fwlink/?linkid=217465)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4f54e498-3825-407d-a036-1900a65d34f1)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b99a40cf-8a31-43d9-bd0b-a458a533068b)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e7ae39e8-1154-4a13-8598-29d4a6358762)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=784efc20-3a41-42ab-b48d-51fd59d71523)  
(Importante)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS11-053**

<sup>[1]</sup>Windows Vista Service Pack 1 risulta interessato solo quando è installato Windows Vista Feature Pack per wireless facoltativo.

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-055**](http://go.microsoft.com/fwlink/?linkid=220276)
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
Microsoft Visio 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=1c7b2a5b-4aa6-4006-90bf-89f8b2b7becd)  
(KB2493523)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

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

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche la sezione precedente, **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/it-it/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

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

-   Tarjei Mandt di [Norman](http://www.norman.com) per aver segnalato 14 problemi descritti nel bollettino MS11-054
-   Liang Yin (professore), Sihan Qing, Weiping Wen e Husheng Zhou, [Dipartimento di protezione delle informazioni dell'università di Pechino](http://www.ss.pku.edu.cn/en/), per aver segnalato un problema descritto nel bollettino MS11-054
-   Matthew 'j00 ru' Jurczyk di [Hispasec](http://www.hispasec.com/) [Virustotal](http://www.virustotal.com/) per aver segnalato cinque problemi descritti nel bollettino MS11-056

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 luglio 2011): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
