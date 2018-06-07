---
TOCTitle: 'MS09-JUL'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2009'
ms:assetid: 'ms09-jul'
ms:contentKeyID: 61240035
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-jul(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2009
================================================================

Data di pubblicazione: martedì 14 luglio 2009 | Aggiornamento: martedì 9 marzo 2010

**Versione:** 8.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a luglio 2009.

Con la pubblicazione dei bollettini per luglio 2009, questo riepilogo bollettini sostituisce le notifiche anticipate inizialmente emesse il 9 luglio 2009 e il 24 luglio 2009 (bollettino straordinario). Per ulteriori informazioni sul servizio di notifica anticipata dei bollettini, vedere [Notifica del rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft ha messo a disposizione un webcast per rispondere alle domande dei clienti sui bollettini programmati il 15 luglio 2009 alle 11:00 ora del Pacifico (USA e Canada). Questo webcast è ora disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Per i bollettini straordinari sulla sicurezza aggiunti alla versione 2.0 di questo riepilogo, MS09-034 e MS09-035, Microsoft ospita due webcast per rispondere alle domande degli utenti il 28 luglio 2009 alle 13:00, ora del Pacifico (Stati Uniti & Canada) e alle 16:00, ora del Pacifico (Stati Uniti & Canada). Iscriversi ora al [webcast di giorno 28 luglio alle 13:00](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032422339&culture=en-us) e [al webcast dello stesso giorno alle 16:00](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032422341&culture=en-us). Successivamente, questi webcast saranno disponibili su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-029">MS09-029</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel motore per caratteri Embedded OpenType possono consentire l'esecuzione di codice in modalità remota (961371)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità nel motore per caratteri Embedded OpenType (EOT), componente di Microsoft Windows. Tali vulnerabilità sono state segnalate privatamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota. Sfruttando una di queste vulnerabilità, un utente malintenzionato può assumere il controllo completo del sistema interessato in maniera remota. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-028">MS09-028</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft DirectShow possono consentire l'esecuzione di codice in modalità remota (971633)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e due vulnerabilità segnalate privatamente di Microsoft DirectShow. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file multimediale QuickTime appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-032">MS09-032</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit di ActiveX (973346)</strong><br />
<br />
Questo aggiornamento per la protezione affronta una vulnerabilità che è stata segnalata privatamente. La vulnerabilità presente nel controllo ActiveX Microsoft Video può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer, creando il controllo ActiveX. Non è mai stata prevista la creazione di istanze del controllo ActiveX in Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-034">MS09-034</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (972260)</strong><br />
<br />
Questo aggiornamento per la protezione straordinario è rilasciato in concomitanza con il Bollettino Microsoft sulla sicurezza MS09-035, il quale descrive i rischi legati all'utilizzo di componenti e controlli sviluppati con versioni di Microsoft Active Template Library (ATL) esposte a vulnerabilità. Questo aggiornamento per la protezione di Internet Explorer aiuta a limitare, in maniera preventiva, gli attacchi noti all'interno di Internet Explorer per i componenti e controlli sviluppati con versioni di ATL esposte a vulnerabilità, come descritto nell'Advisory Microsoft sulla sicurezza (973882) e nel Bollettino Microsoft sulla sicurezza MS09-035.<br />
<br />
Questo aggiornamento per la protezione risolve inoltre tre vulnerabilità di Internet Explorer segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-033">MS09-033</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Virtual PC e Virtual Server può consentire l'acquisizione di privilegi più elevati (969856)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Virtual PC e Microsoft Virtual Server che è stata segnalata privatamente. Un utente malintenzionato che sfrutti questa vulnerabilità potrebbe eseguire codice non autorizzato e acquisire il controllo completo del sistema operativo guest interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Virtual PC, Virtual Server</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-031">MS09-031</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft ISA Server 2006 può consentire l'acquisizione di privilegi più elevati (970953)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Internet Security and Acceleration (ISA) Server 2006. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato riesce ad agire per conto di un account utente amministrativo per un server ISA configurato per l'autenticazione Radius One Time Password (OTP) e per la delega dell'autenticazione con la delega vincolata Kerberos.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft ISA Server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-030">MS09-030</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Office Publisher può consentire l'esecuzione di codice in modalità remota (969516)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Office Publisher che può consentire l'esecuzione di codice in modalità remota se un utente apre un file Publisher appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-035">MS09-035</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Active Template Library di Visual Studio potrebbero consentire l'esecuzione di codice in modalità remota (969706)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità segnalate privatamente nelle versioni pubbliche di Microsoft Active Template Library (ATL) contenute in Visual Studio. Questo aggiornamento per la protezione è esplicitamente rivolto agli sviluppatori di componenti e controlli. Gli sviluppatori che creano e ridistribuiscono componenti e controlli utilizzando ATL dovrebbero installare l'aggiornamento fornito in questo bollettino e attenersi alla procedura descritta per creare, nonché distribuire ai propri clienti, i componenti e controlli che non sono esposti alle vulnerabilità descritte in questo bollettino sulla sicurezza.<br />
<br />
Questo bollettino sulla sicurezza descrive le vulnerabilità che potrebbero consentire l'esecuzione di codice in modalità remota se un utente effettuasse un caricamento di un componente o controllo creato con le versioni di ATL vulnerabili.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Moderato</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Visual Studio</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                                       | Titolo del bollettino                                                                                                                     | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                 | Note fondamentali                                                                                                   |  
|---------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|  
| [MS09-028](http://technet.microsoft.com/security/bulletin/ms09-028) | Alcune vulnerabilità in Microsoft DirectShow possono consentire l'esecuzione di codice in modalità remota (971633)                        | [CVE-2009-1537](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1537) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet.**                                       |  
| [MS09-028](http://technet.microsoft.com/security/bulletin/ms09-028) | Alcune vulnerabilità in Microsoft DirectShow possono consentire l'esecuzione di codice in modalità remota (971633)                        | [CVE-2009-1538](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1538) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-028](http://technet.microsoft.com/security/bulletin/ms09-028) | Alcune vulnerabilità in Microsoft DirectShow possono consentire l'esecuzione di codice in modalità remota (971633)                        | [CVE-2009-1539](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1539) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-029](http://technet.microsoft.com/security/bulletin/ms09-029) | Alcune vulnerabilità nel motore per caratteri Embedded OpenType possono consentire l'esecuzione di codice in modalità remota (961371):    | [CVE-2009-0231](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0231) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-029](http://technet.microsoft.com/security/bulletin/ms09-029) | Alcune vulnerabilità nel motore per caratteri Embedded OpenType possono consentire l'esecuzione di codice in modalità remota (961371):    | [CVE-2009-0232](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0232) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-030](http://technet.microsoft.com/security/bulletin/ms09-030) | Una vulnerabilità in Microsoft Office Publisher può consentire l'esecuzione di codice in modalità remota (969516)                         | [CVE-2009-0566](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0566) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-031](http://technet.microsoft.com/security/bulletin/ms09-031) | Una vulnerabilità di Microsoft ISA Server 2006 può consentire l'acquisizione di privilegi più elevati (970953)                            | [CVE-2009-1135](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1135) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                           |  
| [MS09-032](http://technet.microsoft.com/security/bulletin/ms09-032) | Aggiornamento cumulativo per la protezione dei kill bit di ActiveX (973346)                                                               | [CVE-2008-0015](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-0015) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet.**                                       |  
| [MS09-033](http://technet.microsoft.com/security/bulletin/ms09-033) | Una vulnerabilità in Virtual PC e Virtual Server può consentire l'acquisizione di privilegi più elevati (969856)                          | [CVE-2009-1542](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1542) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | È possibile l'esecuzione di codice funzionale con media probabilità di risultati di sfruttamento.                   |  
| [MS09-034](http://technet.microsoft.com/security/bulletin/ms09-034) | Aggiornamento cumulativo per la protezione di Internet Explorer (972260)                                                                  | [CVE-2009-1917](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1917) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'esecuzione di codice funzionale è semplice e affidabile.                                                          |  
| [MS09-034](http://technet.microsoft.com/security/bulletin/ms09-034) | Aggiornamento cumulativo per la protezione di Internet Explorer (972260)                                                                  | [CVE-2009-1918](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1918) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | È possibile l'esecuzione di codice funzionale con media probabilità di risultati di sfruttamento.                   |  
| [MS09-034](http://technet.microsoft.com/security/bulletin/ms09-034) | Aggiornamento cumulativo per la protezione di Internet Explorer (972260)                                                                  | [CVE-2009-1919](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1919) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | È possibile l'esecuzione di codice funzionale con media probabilità di risultati di sfruttamento.                   |  
| [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035) | Alcune vulnerabilità in Active Template Library di Visual Studio potrebbero consentire l'esecuzione di codice in modalità remota (969706) | [CVE-2009-0901](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0901) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'esecuzione di codice funzionale è semplice e affidabile.                                                          |  
| [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035) | Alcune vulnerabilità in Active Template Library di Visual Studio potrebbero consentire l'esecuzione di codice in modalità remota (969706) | [CVE-2009-2493](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2493) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'esecuzione di codice funzionale è semplice e affidabile.                                                          |  
| [MS09-035](http://technet.microsoft.com/security/bulletin/ms09-035) | Alcune vulnerabilità in Active Template Library di Visual Studio potrebbero consentire l'esecuzione di codice in modalità remota (969706) | [CVE-2009-2495](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2495) | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Solamente bug per l'intercettazione di informazioni personali senza alcun pericolo legato all'esecuzione di codice. |
  
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
</tr>
<tr>
<th colspan="5">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-029**](http://technet.microsoft.com/security/bulletin/ms09-029)
</td>
<td style="border:1px solid black;">
[**MS09-028**](http://technet.microsoft.com/security/bulletin/ms09-028)
</td>
<td style="border:1px solid black;">
[**MS09-032**](http://technet.microsoft.com/security/bulletin/ms09-032)
</td>
<td style="border:1px solid black;">
[**MS09-034**](http://technet.microsoft.com/security/bulletin/ms09-034)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=1efbbd95-cd72-43df-b1ce-7e2b0c0cb9e2)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=e3e54348-6548-4162-b4c0-9910ec6e18b3)  
(Critico)  
[DirectX 8.1](http://www.microsoft.com/downloads/details.aspx?familyid=ce297c3e-8122-4276-a9c2-d1a404f8028d)\*\*\*  
(Critico)  
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=862db2ad-3c1f-4a26-af70-d8c4f5a69dda)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=89d941f0-3f71-46e3-8096-716561396b72)  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=50ffc8f4-7ab7-4e64-9965-5767db5f53cd)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=93bd1baa-e2fb-4e8c-9dd7-738efef32282)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-029**](http://technet.microsoft.com/security/bulletin/ms09-029)
</td>
<td style="border:1px solid black;">
[**MS09-028**](http://technet.microsoft.com/security/bulletin/ms09-028)
</td>
<td style="border:1px solid black;">
[**MS09-032**](http://technet.microsoft.com/security/bulletin/ms09-032)
</td>
<td style="border:1px solid black;">
[**MS09-034**](http://technet.microsoft.com/security/bulletin/ms09-034)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6914167b-6961-480c-a4d4-808cd58a035b)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=09d585cb-481d-4767-875e-9c6ebe456b80)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=24701af8-b87e-4e85-9463-f50755a1b6ad)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=22bed634-5227-4a22-8df5-801f3e2e232a)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c874c8f8-0449-42b1-8d8b-901040069568)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=0acc8aaa-0ae1-412a-9f2b-dc7c707cae00)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3b8b019e-e6d8-4ce2-8f1f-3a6399b252d1)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=f8cd4803-82da-467c-8cb1-520f5a6021d4)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2cbf3699-7f79-4006-99e9-0a4c0d394c48)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=35ab0c5e-df3d-4873-8139-d1d98b3ac350)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=113cc76a-c434-42ff-b594-4834989ad5ba)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=29c8d9e6-2cb8-42b6-b0a6-2510fdb49eab)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-029**](http://technet.microsoft.com/security/bulletin/ms09-029)
</td>
<td style="border:1px solid black;">
[**MS09-028**](http://technet.microsoft.com/security/bulletin/ms09-028)
</td>
<td style="border:1px solid black;">
[**MS09-032**](http://technet.microsoft.com/security/bulletin/ms09-032)
</td>
<td style="border:1px solid black;">
[**MS09-034**](http://technet.microsoft.com/security/bulletin/ms09-034)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=018ef53d-f78e-4084-940d-7c86bf59d83c)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=571d57c5-1ef8-4dc4-a1e5-2211a805f0cc)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b0a458d6-c34c-41c7-964a-c130cfcb0d01)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=44852619-58ad-48f2-bc55-e8e1c72b1ba9)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f4112c25-9e6f-473a-bdbc-3df6dd66e6af)  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=f4ae65a7-142f-4953-a542-315dac2ac606)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7f5fc902-f5d8-4a87-a73f-68632f9a0935)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=1779cbc0-0c29-4fac-a3a6-8b335ffcb98e)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b7a7bb0-80ef-4f25-bc70-3d0ac06007c5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=bd7f36c6-c5c5-4f19-ab59-39f1aaba7fe2)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a594ee0d-ec8f-47df-9125-89d0bbf2115d)  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3bc0e17b-898b-4f29-aa29-607527e1c1cd)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=7df0fce2-543c-4e82-85e6-012bfc8bf130)  
(Critico)
</td>
<td style="border:1px solid black;">
[DirectX 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=48282a89-f849-405a-a31e-2676f45b5042)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=7be36edf-02af-402f-983a-f9ca8128b6b5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=cdb70acf-77c3-40a4-b6a3-0fbc0fc0d7fc)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=adb6bad2-9931-4ede-856e-bb43bb0f6071)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="5">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-029**](http://technet.microsoft.com/security/bulletin/ms09-029)
</td>
<td style="border:1px solid black;">
[**MS09-028**](http://technet.microsoft.com/security/bulletin/ms09-028)
</td>
<td style="border:1px solid black;">
[**MS09-032**](http://technet.microsoft.com/security/bulletin/ms09-032)
</td>
<td style="border:1px solid black;">
[**MS09-034**](http://technet.microsoft.com/security/bulletin/ms09-034)
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
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c67d85c4-25c5-4821-8db9-91764888f893)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6c90240e-c201-4dad-9835-ea71e3527b45)  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=d3be9a13-1a5b-4b74-9649-449df923f573)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b05a19f7-7412-4c2b-ad11-34396e54ca43)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3f8ae651-59f7-48e1-9e8c-8e07c6806964)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d2084e8d-212b-4c39-9163-a71ec6d1b1c7)  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=2b23cd74-6cf1-413b-82a7-b602347e3ce6)  
(Critico)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=900e9a05-2f71-42de-b603-47e4ac061bcb)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-029**](http://technet.microsoft.com/security/bulletin/ms09-029)
</td>
<td style="border:1px solid black;">
[**MS09-028**](http://technet.microsoft.com/security/bulletin/ms09-028)
</td>
<td style="border:1px solid black;">
[**MS09-032**](http://technet.microsoft.com/security/bulletin/ms09-032)
</td>
<td style="border:1px solid black;">
[**MS09-034**](http://technet.microsoft.com/security/bulletin/ms09-034)
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
<td style="border:1px solid black;">
Nessuno
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
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=91f6ee68-0e39-4ec3-b4cd-45f05404e2fb)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0194f994-5821-4fb9-b9e1-ed6af248c995)\*  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=92e3af41-71b0-4a28-afc7-123733180ead)\*  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=30f99bda-9107-4969-90af-2a30e12acdae)\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5cdc3014-97b3-47b5-a6b7-cd0e12ec60e4)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4127b125-fdaa-489a-a80c-14b5647ac7e0)\*  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=1958ec40-3b7b-43a9-9fdc-742735dcf516)\*  
(Moderato)  
[Windows Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=acd3667b-6676-4010-b23b-e8372dd55f93)\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=03330a14-9cfa-4146-a3d3-4b7a76975d2d)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4082c776-318c-4e0c-83fc-2f3f472c039a)  
(Nessun livello di gravità\*\*)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=470387ac-6d75-4b7e-8ca5-376b67a8bd4d)  
(Moderato)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008**

**\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS09-032**

**\*\***Livelli di gravità non sono applicabili a quest'aggiornamento perché la vulnerabilità trattata in questo bollettino non interessa questo software. Tuttavia, agli utenti di questo software Microsoft viene consigliato di applicare l'aggiornamento per la protezione come misura preventiva per difendersi da eventuali nuovi vettori identificabili in futuro.

**Note per MS09-028**

**\*\*\***L'aggiornamento per DirectX 8.1 interessa anche DirectX 8.1b.

**\*\*\*\***L'aggiornamento per DirectX 9.0 interessa anche DirectX 9.0a, DirectX 9.0b e DirectX 9.0c.

#### Suite e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-030**](http://technet.microsoft.com/security/bulletin/ms09-030)
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
Microsoft Office System 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office Publisher 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d4b0665d-5744-49c7-a3c0-f231fd08d3b8)  
(KB969693)  
(Importante)
</td>
</tr>
</table>
 

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Visual Studio
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-035**](http://go.microsoft.com/fwlink/?linkid=158131)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2003
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=63ce454e-f69c-44e3-89fb-eb23c2e2154e)  
(KB971089)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2005
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7c8729dc-06a2-4538-a90d-ff9464dc0197)  
(KB971090)  
(Moderato)  
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9d7ee45b-9892-41b5-ac08-5fde9cde1b42)\*  
(KB973673)  
(Moderato)  
[Microsoft Visual Studio 2005 Service Pack 1 64-bit Hosted Visual C++ Tools](http://www.microsoft.com/downloads/details.aspx?familyid=43f96f2a-69c6-4c5e-b72c-0edfa35f4fc2)  
(KB973830)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Embedded CE 6.0
</td>
<td style="border:1px solid black;">
[Windows Embedded CE 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=99d114f8-4d95-4075-a0f1-45f498f0ade8)\*\*  
(KB974616)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2008
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2008](http://www.microsoft.com/downloads/details.aspx?familyid=8f9da646-94dd-469d-baea-a4306270462c)  
(KB971091)  
(Moderato)  
[Microsoft Visual Studio 2008](http://www.microsoft.com/downloads/details.aspx?familyid=e3bb6602-b7f4-4614-9999-77f5c6f66ccd)\*  
(KB973674)  
(Moderato)  
[Microsoft Visual Studio 2008 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=294de390-3c94-49fb-a014-9a38580e64cb)  
(KB971092)  
(Moderato)  
[Microsoft Visual Studio 2008 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=75fbf397-5140-4961-92a9-78a88ba7228f)\*  
(KB973675)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual C++ 2005
</td>
<td style="border:1px solid black;">
[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=766a6af7-ec73-40ff-b072-9112bab119c2)  
(KB973544)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual C++ 2008
</td>
<td style="border:1px solid black;">
[Microsoft Visual C++ 2008 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=8b29655e-9da4-4b6b-9ac5-687ca0770f93)  
(KB973551)  
(Moderato)  
[Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=2051a0c1-c9b5-4b0a-a8f5-770a549fd78c)  
(KB973552)  
(Moderato)
</td>
</tr>
</table>
 
**Note per MS09-035**

\*Per applicazioni mobili che utilizzano ATL per dispositivi Smart Device

\*\*Installa l'aggiornamento mensile Windows Embedded CE 6.0 (dicembre 2009). Questo pacchetto di aggiornamento è disponibile soltanto nell'Area download Microsoft.

#### Software per la protezione e prodotti server Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Internet Security and Acceleration Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-031**](http://technet.microsoft.com/security/bulletin/ms09-031)
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
Microsoft Internet Security and Acceleration Server 2006
</td>
<td style="border:1px solid black;">
[Microsoft Internet Security and Acceleration Server 2006](http://www.microsoft.com/downloads/details.aspx?familyid=c4e9b1dd-526d-407b-bc23-ebc2738b1b19)  
(KB970811)  
(Importante)  
[Microsoft Internet Security and Acceleration Server 2006 Supportability Update](http://www.microsoft.com/downloads/details.aspx?familyid=e8ccd770-a925-411c-b994-78e4cf5c3476)  
(KB970811)  
(Importante)  
[Microsoft Internet Security and Acceleration Server 2006 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e536cfed-c1af-4868-b2ac-79178d6355a5)  
(KB971143)  
(Importante)
</td>
</tr>
</table>
 

#### Software di virtualizzazione Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Virtual PC
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-033**](http://technet.microsoft.com/security/bulletin/ms09-033)
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
Microsoft Virtual PC 2004
</td>
<td style="border:1px solid black;">
[Microsoft Virtual PC 2004 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=56a160e1-59b5-45bc-aecf-dfe614a7efad)  
(KB969856)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual PC 2007
</td>
<td style="border:1px solid black;">
[Microsoft Virtual PC 2007](http://www.microsoft.com/downloads/details.aspx?familyid=5318c1fa-daf1-4028-832b-eaec9906a46a)  
(KB969856)  
(Importante)  
[Microsoft Virtual PC 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=88de1513-8d35-410f-8896-fe668f885ca0)  
(KB969856)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual PC 2007 x64 Edition
</td>
<td style="border:1px solid black;">
[Microsoft Virtual PC 2007 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=5318c1fa-daf1-4028-832b-eaec9906a46a)  
(KB969856)  
(Importante)  
[Microsoft Virtual PC 2007 x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=88de1513-8d35-410f-8896-fe668f885ca0)  
(KB969856)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Virtual Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-033**](http://technet.microsoft.com/security/bulletin/ms09-033)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual Server 2005
</td>
<td style="border:1px solid black;">
[Microsoft Virtual Server 2005](http://www.microsoft.com/downloads/details.aspx?familyid=85d4f910-4c13-4229-aba7-b9d6181d78c8)  
(KB969856)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 R2
</td>
<td style="border:1px solid black;">
[Microsoft Virtual Server 2005 R2 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1481024d-b430-4d0e-be16-2f141c6a7e57)  
(KB969856)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 R2 x64 Edition
</td>
<td style="border:1px solid black;">
[Microsoft Virtual Server 2005 R2 x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1481024d-b430-4d0e-be16-2f141c6a7e57)  
(KB969856)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Note** A partire dal 1 agosto, 2009, Microsoft non offrirà più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx010402221040.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723/it).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://technet.microsoft.com/it-it/sms/bb676802.aspx) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/en-us/wsus/dd573344.aspx).

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

-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) e Zheng Wenbin, Liu Qi, e Song Shenlei di [Qihoo 360 Security Center](http://www.360.cn/) per aver segnalato un problema descritto nel bollettino MS09-028
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-028
-   Aaron Portnoy di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com/) e un ricercatore anonimo di [Zero Day Initiative](http://www.zerodayinitiative.com/) di Tipping Point, Thomas Garnier di [SkyRecon](http://www.skyrecon.com/), e Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS09-028.
-   [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-029
-   Thomas Waldegger per aver segnalato un problema descritto nel bollettino MS09-029
-   Lionel d'Hauenens di [Labo Skopia](http://www.laboskopia.com/), che collabora con [VeriSign iDefense Labs](http://www.idefense.com/), per aver segnalato un problema descritto nel bollettino MS09-030.
-   Ryan Smith e Alex Wheeler di [IBM ISS X-Force](http://www.iss.net/) per avere inizialmente segnalato un problema descritto nel bollettino MS09-032
-   Julien Tinnes e Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS09-033.
-   Peter Vreugdenhil di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-034
-   Wushi e Ling di [team509](http://www.team509.com/), che collaborano con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-034
-   Peter Vreugdenhil, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-034
-   David Dewey di [IBM ISS X-Force](http://www.iss.net/), per aver segnalato un problema descritto nel bollettino MS09-035
-   Ryan Smith di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato due problemi descritti nel bollettino MS09-035

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 luglio 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (15 luglio 2009): È stato aggiornato il Riepilogo per il bollettino MS09-032; sono stati corretti i requisiti di riavvio per MS09-029; e apportate delle modifiche di diverso tipo.
-   V2.0 (28 luglio 2009): Aggiunti bollettini Microsoft sulla sicurezza MS09-034, Aggiornamento cumulativo per la protezione di Internet Explorer (972260) e MS09-035, Alcune vulnerabilità in Active Template Library di Visual Studio potrebbero consentire l'esecuzione di codice in modalità remota (969706). Sono stati inoltre aggiunti i collegamenti ai webcast dei bollettini relativi ai presenti bollettini straordinari sulla sicurezza.
-   V3.0 (4 agosto 2009): Il bollettino è stato rivisto per comunicare la nuova pubblicazione dell'aggiornamento per Microsoft Internet Explorer 6 Service Pack 1 in Microsoft Windows 2000 Service Pack 4. Tutti i clienti che hanno già installato l'aggiornamento originale per Internet Explorer 6 Service Pack 1 in Microsoft Windows 2000 Service Pack 4 sono già protetti. Tuttavia, i clienti che dispongono della versione in lingua coreana di Internet Explorer 6 Service Pack 1 possono reinstallare l'aggiornamento per Internet Explorer 6 Service Pack 1 sui propri sistemi Windows 2000 per godere della stessa protezione e risolvere allo stesso tempo un problema di stampa. Vedere il bollettino Microsoft sulla sicurezza MS09-034.
-   V4.0 (11 agosto 2009): Il bollettino è stato rivisto per comunicare il nuovo rilascio di MS09-035 al fine di fornire nuovi aggiornamenti per Microsoft Visual Studio 2005 Service Pack 1 (KB973673), Microsoft Visual Studio 2008 (KB973674) e Microsoft Visual Studio 2008 Service Pack 1 (KB973675), per gli sviluppatori che utilizzano Visual Studio per creare componenti e controlli per applicazioni mobili utilizzando ATL per dispositivi Smart Device.
-   V4.1 (13 agosto 2009): È stato corretto il requisito di riavvio per MS09-035.
-   V5.0 (19 agosto 2009): È stata aggiunta una nota a piè di pagina per il bollettino MS09-028 per chiarire il software interessato per DirectX 8.1.
-   V6.0 (25 agosto 2009): È stato rivisto per comunicare il nuovo rilascio dell'aggiornamento in lingua giapponese per Windows XP Service Pack 2, Windows XP Service Pack 3 e Windows XP Professional x64 Edition Service Pack 2. Tutti i clienti che hanno già installato l'aggiornamento originale sono già protetti. Tuttavia, i clienti che dispongono della versione in lingua giapponese di Windows XP Service Pack 2, Windows XP Service Pack 3 o Windows XP Professional x64 Edition Service Pack 2 devono reinstallare l'aggiornamento per godere della stessa protezione e per risolvere allo stesso tempo un problema di stampa. Vedere il Bollettino Microsoft sulla sicurezza MS09-029.
-   V7.0 (12 gennaio 2010): Revisione per l'aggiunta di Windows Embedded CE 6.0 al software interessato per MS09-035. L'aggiornamento per Windows Embedded CE 6.0 (KB974616) è un aggiornamento cumulativo disponibile soltanto nell'Area download Microsoft. Si consiglia ai clienti che utilizzando la piattaforma Windows Embedded CE 6.0 di applicare l'aggiornamento cumulativo.
-   V8.0 (09 marzo 2010): bollettino rivisto per aggiungere Microsoft Virtual Server 2005 al software interessato per MS09-033.

*Built at 2014-04-18T01:50:00Z-07:00*
