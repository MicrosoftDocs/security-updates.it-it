---
TOCTitle: 'MS08-JUL'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2008'
ms:assetid: 'ms08-jul'
ms:contentKeyID: 61240023
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-jul(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2008
================================================================

Data di pubblicazione: martedì 8 luglio 2008 | Aggiornamento: mercoledì 11 febbraio 2009

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a luglio 2008.

Con il rilascio dei bollettini di luglio 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini, pubblicata originariamente il 3 luglio 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il giorno 9 luglio 2008 alle ore 11:00 (ora del Pacifico: USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di luglio](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032374629&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Importante (4)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-040                                                                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Microsoft SQL Server possono consentire l'acquisizione di privilegi più elevati (941203)**](http://technet.microsoft.com/security/bulletin/ms08-040)                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente a Microsoft. La più pericolosa di tali vulnerabilità può consentire a un utente malintenzionato di eseguire del codice e di assumere il controllo completo di un sistema interessato. L'utente malintenzionato autenticato potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti amministrativi completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                              |
| **Software interessato**        | **Microsoft Windows, Microsoft SQL Server.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-038                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Esplora risorse può consentire l'esecuzione di codice in modalità remota (950582)**](http://technet.microsoft.com/security/bulletin/ms08-038)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata pubblicamente in Esplora risorse che può consentire l'esecuzione di codice in modalità remota al momento dell'apertura e del salvataggio di un file di ricerca salvato appositamente predisposto. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-037                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità presenti in DNS possono consentire attacchi di spoofing (953230)**](http://go.microsoft.com/fwlink/?linkid=119620)                                                                                                                                                                                                                                                                                         |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve due vulnerabilità di Windows Domain Name System (DNS), segnalate privatamente a Microsoft, che potrebbero consentire attacchi di spoofing. Tali vulnerabilità sono presenti sia nel client che nel server DNS e potrebbero consentire a un utente malintenzionato remoto di reindirizzare il traffico di rete tra sistemi in Internet a sistemi scelti dall'utente malintenzionato. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                |
| **Effetti della vulnerabilità** | Spoofing                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                           |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-039                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità presenti in Outlook Web Access per Exchange Server possono consentire l'acquisizione di privilegi più elevati (953747)**](http://go.microsoft.com/fwlink/?linkid=120820)                                                                                                                                                                                                                                                 |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente a Microsoft e relative a Outlook Web Access (OWA) per Microsoft Exchange Server. Sfruttando tali vulnerabilità, un utente malintenzionato può accedere ai dati di una singola sessione di un client OWA, acquisendo privilegi più elevati. L'utente malintenzionato può quindi eseguire qualunque operazione durante la sessione OWA del client singolo. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                      |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                           |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

#### Sistemi operativi Windows

 
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
[**MS08-040**](http://technet.microsoft.com/security/bulletin/ms08-040)
</td>
<td style="border:1px solid black;">
[**MS08-038**](http://technet.microsoft.com/security/bulletin/ms08-038)
</td>
<td style="border:1px solid black;">
[**MS08-037**](http://go.microsoft.com/fwlink/?linkid=119620)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Aggiornamento del client DNS:  
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=269c219c-9d6b-4b12-b621-c70cd07cdd22)  
(Importante)  
Aggiornamento del server DNS:  
[Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=332aa92f-a1ad-42a0-87d0-485d2d41335b)  
(Importante)
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
[**MS08-040**](http://technet.microsoft.com/security/bulletin/ms08-040)
</td>
<td style="border:1px solid black;">
[**MS08-038**](http://technet.microsoft.com/security/bulletin/ms08-038)
</td>
<td style="border:1px solid black;">
[**MS08-037**](http://go.microsoft.com/fwlink/?linkid=119620)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità massimo**
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
Aggiornamento del client DNS:  
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ed989a33-7a9e-4423-93a8-b38907467cdf)  
(Importante)  
Nessuno aggiornamento del server DNS applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Aggiornamento del client DNS:  
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a2b016fa-b108-4e8e-b41b-4ca89002907b)  
(Importante)  
Nessuno aggiornamento del server DNS applicabile
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
[**MS08-040**](http://technet.microsoft.com/security/bulletin/ms08-040)
</td>
<td style="border:1px solid black;">
[**MS08-038**](http://technet.microsoft.com/security/bulletin/ms08-038)
</td>
<td style="border:1px solid black;">
[**MS08-037**](http://go.microsoft.com/fwlink/?linkid=119620)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2000 Desktop Engine (WMSDE)](http://www.microsoft.com/downloads/details.aspx?familyid=1c0ae18b-1f17-44b3-a337-b36e7de437a7)  
(KB948110)  
(Importante)  
[Database interno di Windows (WYukon) Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48f6aaa5-49fc-4a16-bc34-8514e214b8cf)  
(KB948109)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Aggiornamento del client DNS:  
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4ef5033c-9843-4e0b-bfad-fcaf05d7dab9)  
(Importante)  
Aggiornamento del server DNS:  
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d1fcb794-e6a5-4c28-b3b3-9cd88f468a42)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft SQL Server 2000 Desktop Engine (WMSDE)](http://www.microsoft.com/downloads/details.aspx?familyid=1c0ae18b-1f17-44b3-a337-b36e7de437a7)  
(KB948110)  
(Importante)  
[Database interno di Windows (WYukon) x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48f6aaa5-49fc-4a16-bc34-8514e214b8cf)  
(KB948109)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Aggiornamento del client DNS:  
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=66624a1f-38bf-4af7-936d-3131474ffe1f)  
(Importante)  
Aggiornamento del server DNS:  
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=040a1ba8-21b0-439e-bf21-1acd1c43b162)  
(Importante)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Aggiornamento del client DNS:  
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=facc80da-61d6-49c5-872d-a1980b66ae3e)  
(Importante)  
Aggiornamento del server DNS:  
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c63e3ee6-6055-4313-b0f1-fec7408886bb)  
(Importante)
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
[**MS08-040**](http://technet.microsoft.com/security/bulletin/ms08-040)
</td>
<td style="border:1px solid black;">
[**MS08-038**](http://technet.microsoft.com/security/bulletin/ms08-038)
</td>
<td style="border:1px solid black;">
[**MS08-037**](http://go.microsoft.com/fwlink/?linkid=119620)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista e Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=06739ca6-7368-4acb-bb67-7e8146071a29)  
(Importante)
</td>
<td style="border:1px solid black;">
Nessuno aggiornamento del client DNS applicabile  
Nessuno aggiornamento del server DNS applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=74ea0893-7c2f-4fad-ad27-588ad953b046)  
(Importante)
</td>
<td style="border:1px solid black;">
Nessuno aggiornamento del client DNS applicabile  
Nessuno aggiornamento del server DNS applicabile
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
[**MS08-040**](http://technet.microsoft.com/security/bulletin/ms08-040)
</td>
<td style="border:1px solid black;">
[**MS08-038**](http://technet.microsoft.com/security/bulletin/ms08-038)
</td>
<td style="border:1px solid black;">
[**MS08-037**](http://go.microsoft.com/fwlink/?linkid=119620)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo del bollettino**
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Database interno di Windows (WYukon) Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48f6aaa5-49fc-4a16-bc34-8514e214b8cf)\*  
(KB948109)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=189a4170-b495-4904-9cbd-209e7494d303)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Nessuno aggiornamento del client DNS applicabile  
Aggiornamento del server DNS:  
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=1fcea8f4-b233-42e1-b913-c4fcae276c7b)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi basati su x64
</td>
<td style="border:1px solid black;">
[Database interno di Windows (WYukon) x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=48f6aaa5-49fc-4a16-bc34-8514e214b8cf)\*  
(KB948109)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=85d8701d-f8c7-4079-8a21-a3a9d5ba71ce)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Nessuno aggiornamento del client DNS applicabile  
Aggiornamento del server DNS:  
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=afac5bbc-71fa-457b-8b0a-f5902d37bfd0)\*  
(Importante)
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
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b30ee4f0-850f-4ff3-86a4-663603a0a802)  
(Importante)
</td>
<td style="border:1px solid black;">
Nessuno aggiornamento del client DNS applicabile  
Nessuno aggiornamento del server DNS applicabile
</td>
</tr>
</table>
 
**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<caption>Microsoft SQL Server</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-040"><strong>MS08-040</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Server 7.0 Service Pack 4</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=c95b2cb3-51a4-44e4-b9f4-9416e9ce16a0">SQL Server 7.0 Service Pack 4</a><br />
(KB948113)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=c95b2cb3-51a4-44e4-b9f4-9416e9ce16a0">SQL Server 7.0 Service Pack 4</a><br />
(KB948113)<br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SQL Server 2000 Service Pack 4</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4fd1f86a-94a2-43d8-9b0a-774c81426d9e">SQL Server 2000 Service Pack 4</a><br />
(KB948110)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=8316bc5e-8c2d-4710-8acc-b815ccc81cd4">SQL Server 2000 Service Pack 4</a><br />
(KB948111)<br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Server 2000 Itanium-based Edition Service Pack 4</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4fd1f86a-94a2-43d8-9b0a-774c81426d9e">SQL Server 2000 Itanium-based Edition Service Pack 4</a><br />
(KB948110)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=8316bc5e-8c2d-4710-8acc-b815ccc81cd4">SQL Server 2000 Itanium-based Edition Service Pack 4</a><br />
(KB948111)<br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SQL Server 2005 Service Pack 2</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c9851cc-2c4c-4190-872c-84993a7623b7">SQL Server 2005 Service Pack 2</a><br />
(KB948109)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a60bb7e7-ef4e-4cbd-b63a-0ad7bd1402b3">SQL Server 2005 Service Pack 2</a><br />
(KB948108)<br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Server 2005 x64 Edition Service Pack 2</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c9851cc-2c4c-4190-872c-84993a7623b7">SQL Server 2005 x64 Edition Service Pack 2</a><br />
(KB948109)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a60bb7e7-ef4e-4cbd-b63a-0ad7bd1402b3">SQL Server 2005 x64 Edition Service Pack 2</a><br />
(KB948108)<br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SQL Server 2005 con SP2 per sistemi basati su Itanium</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c9851cc-2c4c-4190-872c-84993a7623b7">SQL Server 2005 con SP2 per sistemi basati su Itanium</a><br />
(KB948109)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a60bb7e7-ef4e-4cbd-b63a-0ad7bd1402b3">SQL Server 2005 con SP2 per sistemi basati su Itanium</a><br />
(KB948108)<br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Data Engine (MSDE) 1.0 Service Pack 4</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=c95b2cb3-51a4-44e4-b9f4-9416e9ce16a0">Microsoft Data Engine (MSDE) 1.0 Service Pack 4</a><br />
(KB948113)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=c95b2cb3-51a4-44e4-b9f4-9416e9ce16a0">Microsoft Data Engine (MSDE) 1.0 Service Pack 4</a><br />
(KB948113)<br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) Service Pack 4</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4fd1f86a-94a2-43d8-9b0a-774c81426d9e">Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) Service Pack 4</a><br />
(KB948110)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=8316bc5e-8c2d-4710-8acc-b815ccc81cd4">Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) Service Pack 4</a><br />
(KB948111)<br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft SQL Server 2005 Express Edition Service Pack 2</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c9851cc-2c4c-4190-872c-84993a7623b7">Microsoft SQL Server 2005 Express Edition Service Pack 2</a><br />
(KB948109)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a60bb7e7-ef4e-4cbd-b63a-0ad7bd1402b3">Microsoft SQL Server 2005 Express Edition Service Pack 2</a><br />
(KB948108)<br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 2</td>
<td style="border:1px solid black;">Aggiornamento GDR:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c9851cc-2c4c-4190-872c-84993a7623b7">Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 2</a><br />
(KB948109)<br />
(Importante)<br />
<br />
Aggiornamento QFE:<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a60bb7e7-ef4e-4cbd-b63a-0ad7bd1402b3">Microsoft SQL Server 2005 Express Edition with Advanced Services Service Pack 2</a><br />
(KB948108)<br />
(Importante)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Microsoft Exchange Server</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=120820"><strong>MS08-039</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Exchange Server 2003 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=e099c1d1-5af6-4d6c-b735-9599412b3131">Microsoft Exchange Server 2003 Service Pack 2</a><br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Exchange Server 2007</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=086a2a13-a1de-4b1d-bd12-b148bfd2dafa">Microsoft Exchange Server 2007</a><br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Exchange Server 2007 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=63e7f26c-92a8-4264-882d-f96b348c96ab">Microsoft Exchange Server 2007 Service Pack 1</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

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

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/it-it/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676800.aspx).

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

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/it-it/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/it-it/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Dan Kaminsky di [IOActive](http://www.ioactive.com/) per aver segnalato un problema descritto nel bollettino MS08-037.
-   Michael Jordan di [Context Information Security](http://www.contextis.co.uk/) per aver segnalato due problemi descritti nel bollettino MS08-039.
-   Un utente anonimo per aver segnalato un problema descritto nel bollettino MS08-040.
-   Un utente anonimo per aver segnalato un problema descritto nel bollettino MS08-040.
-   Brett Moore di [Insomnia Security](http://www.insomniasec.com/), che collabora con [iDefense VCP](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS08-040.
-   Un utente anonimo per aver segnalato un problema descritto nel bollettino MS08-040.

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/?ln=it&x=15&y=11). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 luglio 2008): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (11 febbraio 2009): È stato rimosso il riferimento non corretto a Microsoft SQL Server 2000 Desktop Engine (WMSDE) in Microsoft Windows 2000 Service Pack 4 dalla tabella Software interessato e posizioni per il download del bollettino MS08-040, relativa al sistema operativo Windows.

*Built at 2014-04-18T01:50:00Z-07:00*
