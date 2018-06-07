---
TOCTitle: 'MS08-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - settembre 2008'
ms:assetid: 'ms08-sep'
ms:contentKeyID: 61240029
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - settembre 2008
===================================================================

Data di pubblicazione: martedì 9 settembre 2008 | Aggiornamento: martedì 9 dicembre 2008

**Versione:** 3.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a settembre 2008.

Con il rilascio dei bollettini di settembre 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 settembre 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 10 settembre 2008 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032374633&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (4)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-054                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità di Windows Media Player può consentire l'esecuzione di codice in modalità remota (954154)**](http://technet.microsoft.com/security/bulletin/ms08-054)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità di Windows Media Player che può consentire l'esecuzione di codice in modalità remota durante la trasmissione di un file audio appositamente predisposto da un server Windows Media. Tale vulnerabilità è stata segnalata a Microsoft privatamente. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-052                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in GDI+ possono consentire l'esecuzione di codice in modalità remota (954593)**](http://technet.microsoft.com/security/bulletin/ms08-052)                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve diverse vulnerabilità di Microsoft Windows GDI+, che sono state segnalate privatamente a Microsoft. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza un file di immagine appositamente predisposto con software interessato o esplora un sito Web che presenta del contenuto appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Software interessato**        | **Microsoft Windows, Internet Explorer, .NET Framework, Office, SQL Server, Visual Studio.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                               |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-053                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità del Codificatore di Windows Media 9 può consentire l'esecuzione di codice in modalità remota (954156)**](http://technet.microsoft.com/security/bulletin/ms08-053)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft relativa al Codificatore di Windows Media 9 Series. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota durante la visualizzazione di una pagina Web appositamente predisposta. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-055                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità di Microsoft Office può consentire l'esecuzione di codice in modalità remota (955047)**](http://technet.microsoft.com/security/bulletin/ms08-055)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente fa clic su un URL di OneNote appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Normalmente per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.

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
Microsoft Windows 2000
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-054**](http://technet.microsoft.com/security/bulletin/ms08-054)
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-053**](http://technet.microsoft.com/security/bulletin/ms08-053)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a860d2d9-653d-4ddb-bbff-323d3ccdb866)  
(KB938464)  
(Critico)  
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c7cbcd19-acc1-4a89-adfa-99b2f431510d)  
(KB947739)  
(Nessuno livello di gravità)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6013f866-3ea1-4672-b1bf-e516204c3a7a)  
(KB947742)  
(Nessuno livello di gravità)  
[Microsoft .NET Framework 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=7f1cd013-2c4b-4582-9114-cb840a96124a)  
(KB947746)  
(Nessuno livello di gravità)  
[Microsoft .NET Framework 2.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=215b73a3-46ab-44a8-a0fb-6d37bd1c39b8)  
(KB947748)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=0cabfbc0-db5d-4a6a-a4cd-e6df89ac2b25)  
(Critico)
</td>
</tr>
<tr>
<th colspan="4">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-054**](http://technet.microsoft.com/security/bulletin/ms08-054)
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-053**](http://technet.microsoft.com/security/bulletin/ms08-053)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=d5891180-5dd1-49ec-bcc6-3030a544202c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e0bd6fbe-f46e-4961-9a79-49ec77d39439)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=57bcb3c2-49d3-4f18-8d03-36abd03d7403)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=caf8a45e-a9f8-4e91-98fd-87eddbeae64c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c5d26771-1f49-4bbf-902c-bf92e527cadb)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=18efea9e-b103-46de-90d9-5e295854cec3)  
(Critico)  
[Codificatore di Windows Media 9 Series x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=ebc1737c-6e78-4244-a1b2-a56d031f16e9)  
(Critico)
</td>
</tr>
<tr>
<th colspan="4">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-054**](http://technet.microsoft.com/security/bulletin/ms08-054)
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-053**](http://technet.microsoft.com/security/bulletin/ms08-053)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ac03f138-eca4-46e1-9782-e811820e547f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=54ce1080-94cf-4e4f-8e09-a7dbab2757c5)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=93f1451b-5b62-47e5-8f0c-b720b957999a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=c83011cd-90b8-494c-9cad-fa055e101992)  
(Moderato)  
[Codificatore di Windows Media 9 Series x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=d8f1b782-136b-443f-b5f2-63aa4d1fd94a)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=14e99f8a-cdd4-40d7-8cfc-73ae6bd6dfad)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-054**](http://technet.microsoft.com/security/bulletin/ms08-054)
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-053**](http://technet.microsoft.com/security/bulletin/ms08-053)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
<tr>
<td style="border:1px solid black;">
Windows Vista e Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=2f4118fd-1ffb-46da-b922-cd4ca4f9d84e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=16f3ad21-ed77-4c32-93df-3b650b2b32a5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=99beebc4-553a-46f8-8245-e3d932306c93)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=334352e7-d41f-494f-866d-f1f1745ffd17)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=aa47d016-f5c9-4586-8876-f1f4f255f54d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=99beebc4-553a-46f8-8245-e3d932306c93)  
(Critico)  
[Codificatore di Windows Media 9 Series x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=54d1279a-7f26-4727-a39d-5505bcd4fc53)  
(Critico)
</td>
</tr>
<tr>
<th colspan="4">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-054**](http://technet.microsoft.com/security/bulletin/ms08-054)
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-053**](http://technet.microsoft.com/security/bulletin/ms08-053)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=72fc6028-6af4-44ec-8d2a-28c53807d6bc)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=23bd3be5-cc66-46f8-9420-49d65d8afe1d)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=5434ca66-5a6b-4517-92fb-72dea0a172ec)\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=3906512b-26db-473e-b522-3883ff34a21c)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7f1e0f05-6c9d-4ad1-9b19-50ee4fa7bd7e)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Codificatore di Windows Media 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=5434ca66-5a6b-4517-92fb-72dea0a172ec)\*  
(Moderato)  
[Codificatore di Windows Media 9 Series x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=e30f9427-26d0-4e86-b9b8-bc637c3b5734)\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=5159bdba-3825-4816-a2be-ab035332b9e2)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questi aggiornamenti non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core, anche se i file interessati da queste vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx).

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
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-055**](http://technet.microsoft.com/security/bulletin/ms08-055)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ef3de64c-fc17-4500-9da4-a3bba97fda6d)  
(KB953405)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ef3de64c-fc17-4500-9da4-a3bba97fda6d)  
(KB953405)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 2 e Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e9f8e309-d721-4bab-b485-5eede8d49eb8)  
(KB954478)  
(Importante)  
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e9f8e309-d721-4bab-b485-5eede8d49eb8)  
(KB954478)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e670ad22-d3c1-41f7-ba30-6a67139feaa3)  
(KB953404)  
(Importante)  
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e670ad22-d3c1-41f7-ba30-6a67139feaa3)  
(KB953404)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007 e Microsoft Office System 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office System 2007](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)  
(Importante)  
[Microsoft Office System 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office System 2007](http://www.microsoft.com/downloads/details.aspx?familyid=fb457536-26c5-428b-97e4-1fc13718266e)  
(KB951944)  
(Importante)  
[Microsoft Office System 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fb457536-26c5-428b-97e4-1fc13718266e)  
(KB951944)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
<td style="border:1px solid black;">
[**MS08-055**](http://technet.microsoft.com/security/bulletin/ms08-055)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
Microsoft Office Project 2002 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office Project 2002 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=ef3de64c-fc17-4500-9da4-a3bba97fda6d)  
(KB953405)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio 2002 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2002 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a6d9d3ef-f087-4f61-9ec1-522b7d4b9c48)  
(KB954479)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Word Viewer, Microsoft Word Viewer 2003, Microsoft Word Viewer 2003 Service Pack 3, Microsoft Office Excel Viewer 2003, Microsoft Office Excel Viewer 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Word Viewer, Microsoft Word Viewer 2003, Microsoft Word Viewer 2003 Service Pack 3, Microsoft Office Excel Viewer 2003, Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e9f8e309-d721-4bab-b485-5eede8d49eb8)  
(KB954478)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Visualizzatore di Microsoft Office PowerPoint 2003
</td>
<td style="border:1px solid black;">
[Visualizzatore di Microsoft Office PowerPoint 2003](http://www.microsoft.com/downloads/details.aspx?familyid=cd503f08-1831-45ff-bdf4-dd918ca40505)  
(KB956500)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Excel Viewer, Visualizzatore di Microsoft Office PowerPoint 2007, Visualizzatore di Microsoft Office PowerPoint 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer, Visualizzatore di Microsoft Office PowerPoint 2007, Visualizzatore di Microsoft Office PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Expression Web e Microsoft Expression Web 2
</td>
<td style="border:1px solid black;">
[Microsoft Expression Web e Microsoft Expression Web 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Groove 2007 e Microsoft Office Groove 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Office Groove 2007 e Microsoft Office Groove 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4b656fe8-6253-490c-a81a-e4e8f0bb58d2)  
(KB954326)\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Works
</td>
<td style="border:1px solid black;">
[Microsoft Works 8](http://www.microsoft.com/downloads/details.aspx?familyid=eb0d224e-a517-40d9-9fc6-2345fa12a841)  
(KB956483)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Digital Image 2006 Suite Edition
</td>
<td style="border:1px solid black;">
[Microsoft Digital Image 2006 Suite Edition](http://www.microsoft.com/downloads/details.aspx?familyid=04afd760-8173-4069-9e82-d3bf053d9eae)  
(KB955992)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office OneNote 2007
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office OneNote 2007](http://www.microsoft.com/downloads/details.aspx?familyid=8ac3576c-7873-4ac6-8bbc-033f6a7bb395)  
(KB950130)  
(Critico)  
[Microsoft Office OneNote 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8ac3576c-7873-4ac6-8bbc-033f6a7bb395)  
(KB950130)  
(Critico)
</td>
</tr>
</table>
 
\*L'aggiornamento per questo software interessato è identico a quello per Microsoft Office XP Service Pack 3.

\*\*L'aggiornamento per questo software interessato è identico a quello per Microsoft Office 2003 Service Pack 2 e Microsoft Office 2003 Service Pack 3.

\*\*\*L'aggiornamento per questo software interessato è identico a quello per Microsoft Office System 2007 e Microsoft Office System 2007 Service Pack 1.

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
Microsoft SQL Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2000 Reporting Services Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
Non applicabile  
Aggiornamento QFE:  
[SQL Server 2000 Reporting Services Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5f9e7f78-7439-414b-a9dc-a779b89427db)  
(KB954609)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4603c722-2468-4adb-b945-2ed0458b8f47)  
(KB954606)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5148b887-f323-4adb-9721-61e1c0cfd213)  
(KB954607)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SQL Server 2005 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4603c722-2468-4adb-b945-2ed0458b8f47)  
(KB954606)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5148b887-f323-4adb-9721-61e1c0cfd213)  
(KB954607)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
SQL Server 2005 per sistemi basati su Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Aggiornamento GDR:  
[SQL Server 2005 per sistemi basati su Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4603c722-2468-4adb-b945-2ed0458b8f47)  
(KB954606)  
(Critico)  
Aggiornamento QFE:  
[SQL Server 2005 per sistemi basati su Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5148b887-f323-4adb-9721-61e1c0cfd213)  
(KB954607)  
(Critico)
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
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2002 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2002 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7848a652-4025-44bb-9c98-37a078b56d01)  
(KB947736)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9bc1e8f8-6c30-4aa0-90f5-fbb0ad5fd90e)  
(KB947737)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio 2005 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2005 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7bf790b-3249-4ee8-9440-fa911ebbc08a)  
(KB947738)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio 2008
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio 2008](http://www.microsoft.com/downloads/details.aspx?familyid=a8c80b29-6d00-4949-a005-5d706122919a)  
(KB952241)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Report Viewer 2005 Service Pack 1 Redistributable Package
</td>
<td style="border:1px solid black;">
[Microsoft Report Viewer 2005 Service Pack 1 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=82833f27-081d-4b72-83ef-2836360a904d)  
(KB954765)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Report Viewer 2008 Redistributable Package
</td>
<td style="border:1px solid black;">
[Microsoft Report Viewer 2008 Redistributable Package](http://www.microsoft.com/downloads/details.aspx?familyid=6ae0aa19-3e6c-474c-9d57-05b2347456b1)  
(KB954766)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual FoxPro 8.0 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 8.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1f4371b9-b8be-4455-94d2-2304ee340543) installato in Microsoft Windows 2000 Service Pack 4  
(KB955368)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual FoxPro 9.0 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 9.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=49b21e30-722d-446e-9020-aceb3870db69) installato in Microsoft Windows 2000 Service Pack 4  
(KB955369)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual FoxPro 9.0 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 9.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=36957f47-9d8b-477d-bd60-5959e5a2eafa) installato in Microsoft Windows 2000 Service Pack 4  
(KB955370)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Platform SDK Redistributable: GDI+
</td>
<td style="border:1px solid black;">
[Microsoft Platform SDK Redistributable: GDI+](http://www.microsoft.com/downloads/details.aspx?familyid=6a63ab9c-df12-4d41-933c-be590feaa05a)  
(Nessuno livello di gravità)
</td>
</tr>
</table>
 

#### Software di protezione Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Forefront Security
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-052**](http://technet.microsoft.com/security/bulletin/ms08-052)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Forefront Client Security 1.0
</td>
<td style="border:1px solid black;">
[Microsoft Forefront Client Security 1.0](http://www.microsoft.com/downloads/details.aspx?familyid=1eb1a79f-44ca-499e-90bb-ac51894e9d1e) installato in Microsoft Windows 2000 Service Pack 4  
(KB957177)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://technet.microsoft.com/it-it/sms/bb676802.aspx) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043.aspx), incluso nell'[Application Compatibility Toolkit 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche relative a Software Update Services e Windows Server Update Services nei contenuti del 2008. Include tutti i contenuti Windows.
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/it-it/wsus/bb466214.aspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/it-it/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Greg MacManus di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-052.
-   Bing Liu del [FortiGuard Global Security Research Team](http://www.fortiguardcenter.com/) di Fortinet per aver segnalato un problema descritto nel bollettino MS08-052.
-   Peter Winter-Smith di [NGSSoftware](http://www.ngssoftware.com/) e Ivan Fratric, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-052.
-   Il [Vulnerability Research Team di Assurent Secure Technologies](http://www.assurent.com/) per aver segnalato un problema descritto nel bollettino MS08-052.
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS08-052.
-   Nguyen Minh Duc e Le Manh Tung, assieme al [Bach Khoa Internetwork Security Center (BKIS) della University of Technology di Hanoi (Vietnam)](http://security.bkis.vn/), per avere segnalato un problema descritto nel bollettino MS08-053.
-   Brett Moore di [Insomnia Security](http://www.insomniasec.com/) per avere segnalato un problema descritto nel bollettino MS08-055.

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 settembre 2008): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (9 settembre 2008): Il riepilogo dei bollettini è stato aggiornato per aggiungere Microsoft Office Project 2002 Service Pack 2, tutto il software del Visualizzatore di Office per Microsoft Office 2003 e tutto il software del Visualizzatore di Office per Microsoft Office System 2007 alla tabella del Software interessato per MS08-052.
-   V2.1 (17 settembre 2008): Il riepilogo dei bollettini è stato aggiornato per sostituire Microsoft Office Project 2002 Service Pack 2 con Microsoft Office Project 2002 Service Pack 1 nella tabella Software interessato. Questa modifica riguarda solamente il nome del prodotto. Non sono previste modifiche ai file binari o al rilevamento.
-   V2.2 (29 ottobre 2008): Il riepilogo dei bollettini è stato aggiornato per rimuovere il Visualizzatore di Microsoft Visio 2003, il Visualizzatore di Microsoft Visio 2007 e il Visualizzatore di Microsoft Visio 2007 Service Pack 1 dall'elenco del Software interessato per MS08-052.
-   V3.0 (9 dicembre 2008): Il riepilogo dei bollettini è stato aggiornato per aggiungere il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 e il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1, Microsoft Expression Web e Microsoft Expression Web 2, Microsoft Office Groove 2007 e Microsoft Office Groove 2007 Service Pack 1 all'elenco del software interessato per MS08-052.

*Built at 2014-04-18T01:50:00Z-07:00*
