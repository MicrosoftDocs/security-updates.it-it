---
TOCTitle: 'MS09-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2009'
ms:assetid: 'ms09-nov'
ms:contentKeyID: 61240039
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2009
==================================================================

Data di pubblicazione: martedì 10 novembre 2009 | Aggiornamento: mercoledì 25 novembre 2009

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a novembre 2009.

Con il rilascio dei bollettini del mese di novembre 2009, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 5 novembre 2009. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 11 novembre 2009 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i webcast dei bollettini sulla sicurezza di novembre](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032407490&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-063">MS09-063</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità dei servizi Web sulle periferiche API può consentire l'esecuzione di codice in modalità remota (973565)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente dei servizi Web sulle periferiche API (WSDAPI) sul sistema operativo Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un sistema Windows interessato riceve un pacchetto appositamente predisposto. Soltanto gli utenti malintenzionati sulla subnet locale possono sfruttare questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-064">MS09-064</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel Server di registrazione licenze può consentire l'esecuzione di codice in modalità remota (974783)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows 2000 che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente malintenzionato invia un messaggio di rete appositamente predisposto a un computer che esegue il Server di registrazione licenze. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le reti dagli attacchi sferrati dall'esterno del perimetro aziendale.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-065">MS09- 065</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (969947)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità del kernel di Windows, che sono state segnalate privatamente a Microsoft. La più grave delle vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un contenuto reso con carattere EOT (Embedded OpenType) appositamente predisposto. In uno scenario di attacco dal Web, un utente malintenzionato dovrebbe pubblicare un sito Web che comprende caratteri appositamente predisposti per tentare di sfruttare questa vulnerabilità. Inoltre, i siti Web manomessi e quelli che accettano o ospitano contenuti forniti dagli utenti potrebbero presentare contenuti appositamente predisposti per sfruttare questa vulnerabilità. Poiché non è in alcun modo possibile obbligare gli utenti a visitare un sito Web appositamente predisposto, un utente malintenzionato dovrebbe indurre le vittime a visitare il sito Web, in genere inducendole a fare clic in un messaggio di posta elettronica o Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-066">MS09- 066</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Active Directory può consentire un attacco di tipo Denial of Service (973309)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel servizio Active Directory, in Active Directory Application Mode (ADAM) e in Active Directory Lightweight Directory Service (AD LDS). La vulnerabilità può consentire un attacco del tipo Denial of Service se lo spazio dello stack si esaurisce durante l'esecuzione di determinati tipi di richieste LDAP o LDAPS. Questa vulnerabilità interessa soltanto i controller di dominio e i sistemi configurati per l'esecuzione di LDAP o LDAPS.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-067">MS09- 067</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (972652)</strong><br />
<br />
Questo aggiornamento per la protezione risolve numerose vulnerabilità di Microsoft Windows segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-068">MS09- 068</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office Word può consentire l'esecuzione di codice in modalità remota (976307)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità che può consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Word appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                                        | Titolo della vulnerabilità                                                                                | ID CVE                                                                            | Valutazione dell'Exploitability Index                                                                                 | Note fondamentali                                                                                                                                        |  
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS09-063](http://technet.microsoft.com/security/bulletin/ms09-063)  | Vulnerabilità legata al danneggiamento della memoria dei servizi Web sulle periferiche API                | [CVE-2009-2512](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2512)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Lo scenario consente un attacco possibile e limitato di tipo Denial of Service.                                                                          |  
| [MS09-064](http://technet.microsoft.com/security/bulletin/ms09-064)  | Vulnerabilità legata all'overflow degli heap nel Server di registrazione licenze                          | [CVE-2009-2523](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2523)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | L'attacco si basa su una race condition che è difficile sfruttare. Si prevede che qualsiasi attacco diverso da un Denial of Service non sarà affidabile. |  
| [MS09- 065](http://technet.microsoft.com/security/bulletin/ms09-065) | Vulnerabilità legata alla risoluzione del riferimento del puntatore NULL in Win32k                        | [CVE-2009-1127](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1127)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 065](http://technet.microsoft.com/security/bulletin/ms09-065) | Vulnerabilità legata alla convalida insufficiente di dati in Win32k                                       | [CVE-2009-2513](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2513)  | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |  
| [MS09- 065](http://technet.microsoft.com/security/bulletin/ms09-065) | Vulnerabilità legata all'analisi del formato EOT in Win32k                                                | [CVE-2009-2514](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-2514)  | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |  
| [MS09- 066](http://technet.microsoft.com/security/bulletin/ms09-066) | Vulnerabilità legata all'overflow dello stack di ricorsione LSASS                                         | [CVE-2009-1928](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1928)  | [**3**](http://technet.microsoft.com/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Esiste la condizione per un attacco di tipo Denial of Service.                                                                                           |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata al danneggiamento della memoria cache in Excel                                       | [CVE-2009-3127](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3127)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata al danneggiamento della memoria SxView in Excel                                      | [CVE-2009-3128](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3128)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata al danneggiamento della memoria con record Featheader in Excel                       | [CVE-2009-3129](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3129)  | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata all'overflow degli heap di analisi dei documenti Excel                               | [CVE-2009-3130](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3130)  | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata al danneggiamento della memoria di analisi delle formule in Excel                    | [CVE-2009-3131](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3131)  | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata all'analisi degli indici in Excel                                                    | [CVE-2009-3132](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3132)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata al danneggiamento della memoria di analisi di documenti Excel                        | [CVE-2009-3133](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3133)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 067](http://technet.microsoft.com/security/bulletin/ms09-067) | Vulnerabilità legata alla sterilizzazione dei campi in Excel                                              | [CVE-2009-3134](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3134)  | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                |  
| [MS09- 068](http://technet.microsoft.com/security/bulletin/ms09-068) | Vulnerabilità legata al danneggiamento della memoria delle informazioni sui file in Microsoft Office Word | [CVE-2009- 3135](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-3135) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                |
  
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
[**MS09-063**](http://technet.microsoft.com/security/bulletin/ms09-063)
</td>
<td style="border:1px solid black;">
[**MS09-064**](http://technet.microsoft.com/security/bulletin/ms09-064)
</td>
<td style="border:1px solid black;">
[**MS09-065**](http://technet.microsoft.com/security/bulletin/ms09-065)
</td>
<td style="border:1px solid black;">
[**MS09-066**](http://technet.microsoft.com/security/bulletin/ms09-066)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=365a8dff-2383-42f6-b567-e545461fd135)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=45db8bb1-c81b-4d3f-a658-74f5fa445f81)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory in Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=297158cf-374c-45d9-b213-978e1f54d244)  
(KB973037)  
(Importante)
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
[**MS09-063**](http://technet.microsoft.com/security/bulletin/ms09-063)
</td>
<td style="border:1px solid black;">
[**MS09-064**](http://technet.microsoft.com/security/bulletin/ms09-064)
</td>
<td style="border:1px solid black;">
[**MS09-065**](http://technet.microsoft.com/security/bulletin/ms09-065)
</td>
<td style="border:1px solid black;">
[**MS09-066**](http://technet.microsoft.com/security/bulletin/ms09-066)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=916abdad-44b7-4f9d-986a-0c3558fb8e06)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=cbe09780-f288-457a-b254-58c9c8744055)  
(KB973039)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1d0464c6-5ed8-4064-887e-618a2db09236)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=b65ddf36-a02d-4aa2-9b4f-7416dbf59e2a)  
(KB973039)  
(Importante)
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
[**MS09-063**](http://technet.microsoft.com/security/bulletin/ms09-063)
</td>
<td style="border:1px solid black;">
[**MS09-064**](http://technet.microsoft.com/security/bulletin/ms09-064)
</td>
<td style="border:1px solid black;">
[**MS09-065**](http://technet.microsoft.com/security/bulletin/ms09-065)
</td>
<td style="border:1px solid black;">
[**MS09-066**](http://technet.microsoft.com/security/bulletin/ms09-066)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5cd62750-e269-44ae-8c7c-c335e8545b9a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=28f1c494-4e16-43b6-93d2-49e15f142ac9)  
(KB973037)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=44cb9029-4b19-4bad-8fc9-3efe285adb0e)  
(KB973039)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=04a7f817-f330-4003-8b25-d3e744905b12)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=509aeec0-112b-44ab-8686-43f381b61940)  
(KB973037)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=87f2109e-5129-467c-930f-70af31ebf5de)  
(KB973039)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b95daac0-4c99-47a4-b0ca-9429997ea3d9)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=040e691b-1ef0-4b73-bef7-a1d77b84b0ca)  
(KB973037)  
(Importante)
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
[**MS09-063**](http://technet.microsoft.com/security/bulletin/ms09-063)
</td>
<td style="border:1px solid black;">
[**MS09-064**](http://technet.microsoft.com/security/bulletin/ms09-064)
</td>
<td style="border:1px solid black;">
[**MS09-065**](http://technet.microsoft.com/security/bulletin/ms09-065)
</td>
<td style="border:1px solid black;">
[**MS09-066**](http://technet.microsoft.com/security/bulletin/ms09-066)
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
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ebf0c294-cd99-445a-a741-78253e47189f)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=54562103-1d99-42d7-8f7f-c0cbcdce90db)  
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
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d9645fc9-f524-43f1-8b8c-94b3b4312158)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fcb87cc8-6fd7-4f16-93d6-552999462fb1)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[**MS09-063**](http://technet.microsoft.com/security/bulletin/ms09-063)
</td>
<td style="border:1px solid black;">
[**MS09-064**](http://technet.microsoft.com/security/bulletin/ms09-064)
</td>
<td style="border:1px solid black;">
[**MS09-065**](http://technet.microsoft.com/security/bulletin/ms09-065)
</td>
<td style="border:1px solid black;">
[**MS09-066**](http://technet.microsoft.com/security/bulletin/ms09-066)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d6a60883-b103-459a-a91b-cd6ed946cefe)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b97d48de-0f6d-4bca-b990-acf543fdb8b7)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=701abf15-7f93-41de-8d09-13404fd79a7e)\*  
(KB973037)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3dde1587-42d3-438f-8344-696a5657b9b1)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0e2b8607-10fa-406a-96a5-18290f479c48)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=17f5f9e0-5869-41da-9b3b-6e67540af1f0)\*  
(KB973037)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=841a027f-22fa-42de-93b3-57a3fe92a1d3)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=28eba3f3-99a5-424c-bc8d-a718c716699e)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

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
[**MS09-067**](http://technet.microsoft.com/security/bulletin/ms09-067)
</td>
<td style="border:1px solid black;">
[**MS09-068**](http://technet.microsoft.com/security/bulletin/ms09-068)
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
[Microsoft Office Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=5672c8fc-8509-4962-ad86-ebc0f2575043)  
(KB973471)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0369fae5-958b-4eba-83a4-9c07e701c273)  
(KB973444)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6a6a0f5d-17dc-4a34-b9a0-0774aa287ba5)  
(KB973475)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6b77bc62-bcbb-4b9a-97d1-a49ca0582e54)  
(KB973443)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=322b24ca-aff6-4ca0-acf1-440cae0f9693)<sup>[1]</sup>
(KB973593)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-067**](http://technet.microsoft.com/security/bulletin/ms09-067)
</td>
<td style="border:1px solid black;">
[**MS09-068**](http://technet.microsoft.com/security/bulletin/ms09-068)
</td>
</tr>
<tr>
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=8f115b1c-1e28-4ecf-937c-99c4b60c7c8e)  
(KB976830)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=8f115b1c-1e28-4ecf-937c-99c4b60c7c8e)  
(KB976830)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=b84fe57d-ddda-451e-9ead-69e10aee7928)  
(KB976828)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=b84fe57d-ddda-451e-9ead-69e10aee7928)  
(KB976828)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=4dd4bc05-1217-497e-8f65-4347f2544ed6)  
(KB976831)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=4dd4bc05-1217-497e-8f65-4347f2544ed6)  
(KB976831)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Altro software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-067**](http://technet.microsoft.com/security/bulletin/ms09-067)
</td>
<td style="border:1px solid black;">
[**MS09-068**](http://technet.microsoft.com/security/bulletin/ms09-068)
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
Microsoft Office Excel Viewer 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=19151e22-5642-456c-bd39-298574369cdb)  
(KB973484)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer Service Pack 1 e Microsoft Office Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fb36df5e-ebef-46bf-9edd-67f2c76dbdb3)  
(KB973707)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Word Viewer 2003
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4cc5e6c5-7efb-4180-9a9b-0788115c91e1)  
(KB973866)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Word Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=4cc5e6c5-7efb-4180-9a9b-0788115c91e1)  
(KB973866)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c4c92d2e-e87d-446f-8d3e-8f4be10c70aa)  
(KB973704)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS09-067**

<sup>[1]</sup>\*Per Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB973593, gli utenti devono installare anche l'aggiornamento per la protezione per il [pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c4c92d2e-e87d-446f-8d3e-8f4be10c70aa) (KB973704) per essere protetti dalle vulnerabilità descritte nel bollettino.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Note** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx010402221040.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/default.aspx?ln=it): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
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

-   Neel Mehta di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS09-063
-   Cody Pierce di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS09-064
-   Agin Sun per aver segnalato un problema descritto nel bollettino MS09-065
-   Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS09-065
-   Bing Liu di [FortiGuard Labs di Fortinet](http://www.fortiguard.com/) per aver segnalato tre problemi descritti nel bollettino MS09-067
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-067
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-067
-   Un ricercatore anonimo che collabora con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS09-067
-   Nicolas Joly di [VUPEN Security](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS09-067
-   Jun Mao di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-068

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/default.aspx?ln=it).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (10 novembre 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (25 novembre 2009): È stata aggiunta una nota fondamentale relativa all'Exploitability Index per CVE-2009-2523.

*Built at 2014-04-18T01:50:00Z-07:00*
