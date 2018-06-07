---
TOCTitle: 'MS08-AUG'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2008'
ms:assetid: 'ms08-aug'
ms:contentKeyID: 61240019
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-aug(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2008
================================================================

Data di pubblicazione: martedì 12 agosto 2008 | Aggiornamento: mercoledì 15 ottobre 2008

**Versione:** 3.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati nel mese di agosto 2008.

Con il rilascio dei bollettini di agosto 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio dei bollettini, pubblicata originariamente il 7 agosto 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il giorno 13 agosto 2008 alle ore 11:00 (ora del Pacifico: USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di agosto](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032374631&culture=en-us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (6)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-046                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Vulnerabilità nel sistema di Gestione colori immagine di Microsoft Windows può consentire l'esecuzione di codice in modalità remota (952954)**](http://technet.microsoft.com/security/bulletin/ms08-046)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Riepilogo**                   | L'aggiornamento risolve una vulnerabilità segnalata privatamente nel sistema di Gestione colori immagine di Microsoft (ICM) che può consentire l'esecuzione di codice in modalità remota nell'ambito dell'utente corrente. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-045                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (953838)**](http://technet.microsoft.com/security/bulletin/ms08-045)                                                                                                                                                                                                                                                                                                                                                                   |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente e una divulgata pubblicamente. Tutte queste vulnerabilità potrebbero consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Windows, Internet Explorer.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                 |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-041                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nel controllo ActiveX per Snapshot Viewer di Microsoft Access può consentire l'esecuzione di codice in modalità remota (955617)**](http://technet.microsoft.com/security/bulletin/ms08-041)                                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft e riscontrata nel controllo ActiveX per Snapshot Viewer di Microsoft Access. Un utente malintenzionato potrebbe sfruttare la vulnerabilità creando una pagina Web dannosa. Se un utente visualizza la pagina Web, la vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                             |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                         |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-043                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (954066)**](http://technet.microsoft.com/security/bulletin/ms08-043)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve quattro vulnerabilità riscontrate in Microsoft Office Excel che possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Excel appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-051                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Microsoft PowerPoint possono consentire l'esecuzione di codice in modalità remota (949785)**](http://technet.microsoft.com/security/bulletin/ms08-051)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve tre vulnerabilità di Microsoft Office Powerpoint e del Visualizzatore di Microsoft Office PowerPoint, che possono consentire l'esecuzione di codice in modalità remota nel caso in cui un utente apra un file di Powerpoint appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando una di queste vulnerabilità, un utente malintenzionato potrebbe assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-044                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità nei filtri di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (924090)**](http://technet.microsoft.com/security/bulletin/ms08-044)                                                                                                                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente a Microsoft. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante la visualizzazione con Microsoft Office di un file di immagine appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                      |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                  |

Importante (5)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-047                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità legata all'elaborazione dei criteri IPsec può consentire l'intercettazione di informazioni personali (953733)**](http://technet.microsoft.com/security/bulletin/ms08-047)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento risolve una vulnerabilità segnalata privatamente a Microsoft e legata al modo in cui vengono applicate in Windows alcune regole di Internet Protocol Security (IPsec). Questa vulnerabilità può indurre i sistemi a ignorare i criteri IPsec e a trasmettere il traffico di rete sotto forma di testo non crittografato. Ciò può portare alla divulgazione in rete di informazioni che dovrebbero essere crittografate e può consentire a un utente malintenzionato, che intercetti il traffico di rete, di visualizzare e modificare il contenuto di tale traffico. Si noti che questa vulnerabilità non consente di eseguire codice direttamente o di acquisire diritti utente più elevati, ma potrebbe essere utilizzata per raccogliere informazioni utili al fine di compromettere ulteriormente il sistema o la rete interessati. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Intercettazione di informazioni personali                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-049                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Vulnerabilità nel Sistema di eventi possono consentire l'esecuzione di codice in modalità remota (950974)**](http://technet.microsoft.com/security/bulletin/ms08-049)                                                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento risolve due vulnerabilità segnalate privatamente nel Sistema di eventi di Microsoft Windows che può consentire l'esecuzione di codice in modalità remota. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti amministrativi completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                       |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                    |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-048                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento per la protezione di Outlook Express e Windows Mail (951066)**](http://technet.microsoft.com/security/bulletin/ms08-048)                                                                                                                                                                                                                                                                                                                                                                                           |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft e riscontrata in Outlook Express e Windows Mail. Tale vulnerabilità può consentire l'intercettazione di informazioni personali nel momento in cui un utente visiti una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Intercettazione di informazioni personali                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                         |
| **Software interessato**        | **Microsoft Windows, Outlook Express, Windows Mail.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                               |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-050                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Windows Messenger può consentire l'intercettazione di informazioni personali (955702)**](http://technet.microsoft.com/security/bulletin/ms08-050)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Riepilogo**                   | Quest'aggiornamento per la protezione risolve una vulnerabilità segnalata pubblicamente nelle versioni supportate di Windows Messenger. Conseguentemente a questa vulnerabilità, lo scripting di un controllo ActiveX potrebbe consentire l'intercettazione di informazioni personali nel contesto dell'utente collegato. Un utente malintenzionato potrebbe modificare lo stato, ottenere informazioni relative ai contatti e avviare sessioni di chat audio e video all'insaputa dell'utente collegato. Un utente malintenzionato potrebbe inoltre acquisire l'ID di accesso di un altro utente e collegarsi in modalità remota al client di Messenger di quell'utente, assumendone l'identità. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Intercettazione di informazioni personali                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer è possibile verificare se è necessario installare soltanto questo aggiornamento per Windows Messenger 4.7 nelle edizioni supportate di Windows XP. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **Microsoft Windows, Windows Messenger.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-042                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Microsoft Word può consentire l'esecuzione di codice in modalità remota (955048)**](http://technet.microsoft.com/security/bulletin/ms08-042)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento della protezione risolve una vulnerabilità segnalata pubblicamente a Microsoft e riscontrata in Microsoft Word. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file di Word appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

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
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="7">
Microsoft Windows 2000
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-046**](http://technet.microsoft.com/security/bulletin/ms08-046)
</td>
<td style="border:1px solid black;">
[**MS08-045**](http://technet.microsoft.com/security/bulletin/ms08-045)
</td>
<td style="border:1px solid black;">
[**MS08-047**](http://technet.microsoft.com/security/bulletin/ms08-047)
</td>
<td style="border:1px solid black;">
[**MS08-049**](http://technet.microsoft.com/security/bulletin/ms08-049)
</td>
<td style="border:1px solid black;">
[**MS08-048**](http://technet.microsoft.com/security/bulletin/ms08-048)
</td>
<td style="border:1px solid black;">
[**MS08-050**](http://technet.microsoft.com/security/bulletin/ms08-050)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=db455d17-435f-46d7-b2dd-5babb5a1eeb3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=1557b93b-ecba-4f42-b89d-db0ee067d65b)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=aa780735-5928-4c46-89a4-63a814954796)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=1b2ad648-7dc9-407a-99f6-f39922746027)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 5.5 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6257bfae-35f0-4c0e-b960-bca7aa6f86f7)  
(Importante)  
[Microsoft Outlook Express 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=dab178f7-c282-41f4-acb1-a86e6aa4c91b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-046**](http://technet.microsoft.com/security/bulletin/ms08-046)
</td>
<td style="border:1px solid black;">
[**MS08-045**](http://technet.microsoft.com/security/bulletin/ms08-045)
</td>
<td style="border:1px solid black;">
[**MS08-047**](http://technet.microsoft.com/security/bulletin/ms08-047)
</td>
<td style="border:1px solid black;">
[**MS08-049**](http://technet.microsoft.com/security/bulletin/ms08-049)
</td>
<td style="border:1px solid black;">
[**MS08-048**](http://technet.microsoft.com/security/bulletin/ms08-048)
</td>
<td style="border:1px solid black;">
[**MS08-050**](http://technet.microsoft.com/security/bulletin/ms08-050)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d313f42c-f43f-48ea-82ef-3bc33077c7fa)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=69af2f30-138e-4b15-ab8d-4fce44cc0bc2)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=8e2125c7-52cb-4052-82a3-2d3c6a953752)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=01a34aa4-a456-4efc-a93a-c3c682b0181c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=91469f2f-461c-4a67-8738-d42520427f6b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Messenger 4.7](http://www.microsoft.com/downloads/details.aspx?familyid=8f588f7e-c4ed-42a0-b157-54b1eda60474)  
(KB946648)  
(Importante)  
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=3150c6b8-f50b-4b84-a7ce-c8daf77c080c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=4780b89e-9735-4d3f-8def-34e7337ff604)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=39b41e4b-3237-409d-a818-ab0517c5e7cf)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=246b2686-e330-47a2-b4d4-68f218ad4021)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=2220aece-79d2-426f-90ec-24a17470567a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Messenger 4.7](http://www.microsoft.com/downloads/details.aspx?familyid=a5fc5457-832f-4ee8-be60-4cc8518d1c10)  
(KB946648)  
(Importante)  
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-046**](http://technet.microsoft.com/security/bulletin/ms08-046)
</td>
<td style="border:1px solid black;">
[**MS08-045**](http://technet.microsoft.com/security/bulletin/ms08-045)
</td>
<td style="border:1px solid black;">
[**MS08-047**](http://technet.microsoft.com/security/bulletin/ms08-047)
</td>
<td style="border:1px solid black;">
[**MS08-049**](http://technet.microsoft.com/security/bulletin/ms08-049)
</td>
<td style="border:1px solid black;">
[**MS08-048**](http://technet.microsoft.com/security/bulletin/ms08-048)
</td>
<td style="border:1px solid black;">
[**MS08-050**](http://technet.microsoft.com/security/bulletin/ms08-050)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=828d8fdc-8534-4621-85a5-08aec255496f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=0617a5dd-dce9-4de0-b0a0-ce38efe13524)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b3c2e2fd-1cb9-491b-937c-053dd59a65bf)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=92a3d08f-c117-4b24-bc78-2b913d270df6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=30f2244a-f6fd-4fc1-a871-abf6958cb660)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Messenger 4.7](http://www.microsoft.com/downloads/details.aspx?familyid=302315a8-ccb2-47c2-9104-b8e1d1f49aa0)  
(KB954723)  
(Moderato)  
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=0a13776f-d543-41df-b904-d51e368c81cc)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=32a63f52-9fe6-48e3-bb4e-7d4dda5e0a90)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=88a26b76-f7df-45c9-8ed0-7d3cd71c1987)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6bfbb6d8-5106-4adf-83cb-35ffc6e8eaf8)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=3287f006-cbb2-4c6d-820c-32833e08035a)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Messenger 4.7](http://www.microsoft.com/downloads/details.aspx?familyid=be94d138-7d7b-489e-baa6-e214950be6b9)  
(KB954723)  
(Moderato)  
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=9566493f-4260-4072-947a-527887d2cd63)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=1855997e-a3be-46b1-a0bc-bb55eb0045fe)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=97d0d37d-5d76-4bc3-8cbd-1e3976c82acf)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=45356565-697f-41b3-9879-3edd11dbcb7e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=c8570e40-355b-4a9b-933d-53ae021cbda5)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Messenger 4.7](http://www.microsoft.com/downloads/details.aspx?familyid=e4b72618-536b-4a21-bd91-d91be9ca24e5)  
(KB954723)  
(Moderato)  
[Windows Messenger 5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774)  
(KB899283)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="7">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-046**](http://technet.microsoft.com/security/bulletin/ms08-046)
</td>
<td style="border:1px solid black;">
[**MS08-045**](http://technet.microsoft.com/security/bulletin/ms08-045)
</td>
<td style="border:1px solid black;">
[**MS08-047**](http://technet.microsoft.com/security/bulletin/ms08-047)
</td>
<td style="border:1px solid black;">
[**MS08-049**](http://technet.microsoft.com/security/bulletin/ms08-049)
</td>
<td style="border:1px solid black;">
[**MS08-048**](http://technet.microsoft.com/security/bulletin/ms08-048)
</td>
<td style="border:1px solid black;">
[**MS08-050**](http://technet.microsoft.com/security/bulletin/ms08-050)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista e Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=13cba012-dd20-48f9-8e44-e4cb104c4cad)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3f21a8a2-9861-4fef-9d1e-caf5f7822c1a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=6418c78f-f008-4028-beb1-5a5ea8e797a1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=3851bcf8-f971-4d38-b27f-97396854aac0)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ead919c2-d548-47b7-9cd6-80f991266428)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=aa04a754-fbfb-42a7-89d2-14373e3f4742)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e03ccfb0-3ea3-4c59-adcf-9882d7086013)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=3bf7eb8a-b347-4661-be2d-682adc713769)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-046**](http://technet.microsoft.com/security/bulletin/ms08-046)
</td>
<td style="border:1px solid black;">
[**MS08-045**](http://technet.microsoft.com/security/bulletin/ms08-045)
</td>
<td style="border:1px solid black;">
[**MS08-047**](http://technet.microsoft.com/security/bulletin/ms08-047)
</td>
<td style="border:1px solid black;">
[**MS08-049**](http://technet.microsoft.com/security/bulletin/ms08-049)
</td>
<td style="border:1px solid black;">
[**MS08-048**](http://technet.microsoft.com/security/bulletin/ms08-048)
</td>
<td style="border:1px solid black;">
[**MS08-050**](http://technet.microsoft.com/security/bulletin/ms08-050)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4b52ff2f-d2f5-4c20-b6cf-86d86c56b0f8)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=c3363df6-39dc-4910-9ce5-66553155378e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=0640f95e-1eee-4dd1-b4dd-2b82b7e984b9)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=dc3c4b63-acd3-4469-8d47-e0562d99ee65)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=df9814a6-5be0-4ac1-a767-a0eae8d5ee5d)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=39dd1722-412b-469d-a475-b6513764838c)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=51a93538-5e94-4f81-a6e0-d497a7b4899d)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=5f973f54-2322-4b41-8c1a-3e712c0da8ae)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ffc3cfcb-73fe-4a6d-9595-e9d7a5b3d3f7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=e9c6cd46-30ad-46ee-9c8b-d0b446e660c4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=390da130-749d-4890-aad7-be91e15b32bb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=9226cd85-1445-4976-a126-757c5d142ffd)  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** La vulnerabilità affrontata da questo aggiornamento non interessa le edizioni supportate di Windows Server 2008 se Windows Server 2008 è stato installato utilizzando l'opzione di installazione di Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

#### Suite e software Microsoft Office

 
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
</tr>
<tr>
<th colspan="6">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-041**](http://technet.microsoft.com/security/bulletin/ms08-041)
</td>
<td style="border:1px solid black;">
[**MS08-043**](http://technet.microsoft.com/security/bulletin/ms08-043)
</td>
<td style="border:1px solid black;">
[**MS08-051**](http://technet.microsoft.com/security/bulletin/ms08-051)
</td>
<td style="border:1px solid black;">
[**MS08-044**](http://technet.microsoft.com/security/bulletin/ms08-044)
</td>
<td style="border:1px solid black;">
[**MS08-042**](http://technet.microsoft.com/security/bulletin/ms08-042)
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
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works 8
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
[Microsoft Works 8](http://www.microsoft.com/downloads/details.aspx?familyid=458985c3-9c6f-4049-81cd-0d0389c81f11)  
(KB955428)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Access 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=54e4031d-298f-480c-88d5-0ad3b2b62ba9)  
(KB955441)  
(Critico)
</td>
<td style="border:1px solid black;">
[Excel 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4bf8688e-e5b9-4e53-a1a1-8cf1acfdb80b)  
(KB951582)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e7c044d8-778a-4985-b25b-4f7f6e4abadd)  
(KB949007)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3ab323ec-9f92-453c-b7c7-9a95a9efcaea)  
(KB921595)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Access 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=34b655f8-1922-4246-94ca-ed381c3e3b13)  
(KB955440)  
(Critico)
</td>
<td style="border:1px solid black;">
[Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9bbf7550-f5c4-4b9b-bd86-1e7be6c42eb5)  
(KB951551)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f8921074-7985-4d42-ac2b-d2f3b1d466ba)  
(KB948995)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=bf566ce6-23da-45e5-9c2b-c47331d30e79)  
(KB921596)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c7146dfc-e1be-4d13-877b-1d9bcacc4a64)  
(KB954463)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 2 e Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office Access 2003 Service Pack 2 e Microsoft Office Access 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fd698517-a504-427d-9e5f-fde8f102142c)  
(KB955439)  
(Critico)
</td>
<td style="border:1px solid black;">
[Excel 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fc612e9a-bdf3-4952-8ada-0de5a50973f0)  
(KB951548)  
(Importante)  
[Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fc612e9a-bdf3-4952-8ada-0de5a50973f0)  
(KB951548)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7a7c21f0-5e0e-4dee-9710-1ce3d565913f)\*\*  
(KB948988)  
(Importante)  
[Microsoft Office PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7a7c21f0-5e0e-4dee-9710-1ce3d565913f)\*\*  
(KB948988)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e0df2f6e-1102-461d-829f-5f3e2d7eb4b3)  
(KB921598)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=13a37b76-9fec-426f-8176-3c95f934efe0)  
(KB954464)  
(Importante)  
[Microsoft Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=13a37b76-9fec-426f-8176-3c95f934efe0)  
(KB954464)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007 e Microsoft Office System 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Excel 2007](http://www.microsoft.com/downloads/details.aspx?familyid=2753e8d6-e156-49ef-af2d-4c521c808ffd)  
(KB951546)  
(Importante)  
[Excel 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2753e8d6-e156-49ef-af2d-4c521c808ffd)  
(KB951546)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=55fd618a-e9c5-4f1e-b9a5-b2e47ec98ef1)  
(KB951338)  
(Importante)  
[Microsoft Office PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55fd618a-e9c5-4f1e-b9a5-b2e47ec98ef1)  
(KB951338)  
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
<th colspan="6">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-041**](http://technet.microsoft.com/security/bulletin/ms08-041)
</td>
<td style="border:1px solid black;">
[**MS08-043**](http://technet.microsoft.com/security/bulletin/ms08-043)
</td>
<td style="border:1px solid black;">
[**MS08-051**](http://technet.microsoft.com/security/bulletin/ms08-051)
</td>
<td style="border:1px solid black;">
[**MS08-044**](http://technet.microsoft.com/security/bulletin/ms08-044)
</td>
<td style="border:1px solid black;">
[**MS08-042**](http://technet.microsoft.com/security/bulletin/ms08-042)
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
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Project 2002 Service Pack 1
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
[Microsoft Office Project 2002 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=bf566ce6-23da-45e5-9c2b-c47331d30e79)  
(KB921596)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
SnapShot Viewer per Microsoft Access
</td>
<td style="border:1px solid black;">
[SnapShot Viewer per Microsoft Access](http://www.microsoft.com/downloads/details.aspx?familyid=7c22bb32-7ce3-4ff2-8366-ba2eb5135833)  
(KB957198)  
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
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visualizzatore di Microsoft Office PowerPoint 2003
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Visualizzatore di Microsoft Office PowerPoint 2003](http://www.microsoft.com/downloads/details.aspx?familyid=911c8872-dec8-4b8e-9708-93dcabd3e036)  
(KB949041)  
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
Microsoft Office Excel Viewer 2003 e Microsoft Office Excel Viewer 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer 2003](http://www.microsoft.com/downloads/details.aspx?familyid=d7ed9e75-15f2-4950-98b3-93023ba0f4c1)  
(KB951589)  
(Importante)  
[Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d7ed9e75-15f2-4950-98b3-93023ba0f4c1)  
(KB951589)  
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=b574d906-7f09-49b0-80bf-e84dee8c4583)  
(KB955472)  
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
Microsoft Office Converter Pack
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
[Microsoft Office Converter Pack](http://www.microsoft.com/downloads/details.aspx?familyid=199b08c7-6d79-4930-8f0c-31034629c485)  
(KB925256)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=7afdae9b-9c74-4af7-9844-0e54221ea3b9)  
(KB951596)  
(Importante)  
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7afdae9b-9c74-4af7-9844-0e54221ea3b9)  
(KB951596)  
(Importante)
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=84ce5d58-0010-4945-bce9-67a41f898f2f) (KB954038)  
(Importante)  
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=84ce5d58-0010-4945-bce9-67a41f898f2f) (KB954038)  
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
Microsoft Office SharePoint Server 2007 e Microsoft Office SharePoint Server 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007](http://www.microsoft.com/downloads/details.aspx?familyid=a7731749-b026-4765-808a-e151b990f0e1)\*  
(KB953397)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a7731749-b026-4765-808a-e151b990f0e1)\*  
(KB953397)  
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 x64 Edition e Microsoft Office SharePoint Server 2007 x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=fc95ab88-2d31-44e1-a702-7cb10e83695b)\*  
(KB953397)  
(Importante)  
[Microsoft Office SharePoint Server 2007 x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fc95ab88-2d31-44e1-a702-7cb10e83695b)\*  
(KB953397)  
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
<th colspan="6">
Microsoft Office per Mac
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-041**](http://technet.microsoft.com/security/bulletin/ms08-041)
</td>
<td style="border:1px solid black;">
[**MS08-043**](http://technet.microsoft.com/security/bulletin/ms08-043)
</td>
<td style="border:1px solid black;">
[**MS08-051**](http://technet.microsoft.com/security/bulletin/ms08-051)
</td>
<td style="border:1px solid black;">
[**MS08-044**](http://technet.microsoft.com/security/bulletin/ms08-044)
</td>
<td style="border:1px solid black;">
[**MS08-042**](http://technet.microsoft.com/security/bulletin/ms08-042)
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
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=ebd3af0c-3f62-4d18-bf45-881655683bd5)  
(KB956343)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=ebd3af0c-3f62-4d18-bf45-881655683bd5)  
(KB956343)  
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
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=9515c70d-be80-4ade-856a-ea542f7d84e1)  
(KB956344)  
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
 
**\*Nota per Microsoft Office SharePoint Server 2007, Microsoft Office SharePoint Server 2007 Service Pack 1, Microsoft Office SharePoint Server 2007 x64 Edition e Microsoft Office SharePoint Server 2007 x64 Edition Service Pack 1 (MS08-043):** L'aggiornamento contenuto nel bollettino sulla sicurezza MS08-043 si applica ai server in cui è instalato Excel Services, quali la configurazione predefinita di Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services.

**\*\*Nota per Microsoft Office Powerpoint 2003 Service Pack 2 e Microsoft Office Powerpoint 2003 Service Pack 3 (MS08-051):** Microsoft ha pubblicato i nuovi pacchetti di aggiornamento, denominati Versione 2, nell'Area download Microsoft. I clienti che hanno installato manualmente la Versione 1 di questo aggiornamento dall'Area download di Microsoft devono reinstallare la Versione 2 di questo aggiornamento. I clienti che hanno installato questo aggiornamento utilizzando Microsoft Update o Office Update non devono reinstallarlo. Per ulteriori informazioni, incluse altre opzioni di installazione o soluzioni alternative, vedere il bollettino [MS08-051](http://technet.microsoft.com/security/bulletin/ms08-051).

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

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33387) e in [SMS 2.0 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21161).

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

-   [ISC/SANS](http://isc.sans.org/) per aver segnalato un problema descritto nel bollettino MS08-042
-   [VeriSign iDefense VCP](http://www.idefense.com/vcp) per aver segnalato un problema descritto nel bollettino MS08-043
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS08-043
-   Jeremy Funk per aver segnalato un problema descritto nel bollettino MS08-043
-   Shaun Colley di [NGS Software](http://www.nextgenss.com/) per aver segnalato un problema descritto nel bollettino MS08-044
-   Damian Put di [Zero Day Initiative (ZDI)](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS08-044
-   Un ricercatore anonimo che collabora con [iDefense VCP](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-044
-   Damian Put che collabora con [iDefense VCP](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-044
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS08-045.
-   Tavis Ormandy del [Google Security Team](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS08-045.
-   Sam Thomas, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-045.
-   [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS08-045
-   Jun Mao di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-046
-   Jorge Luis Alvarez Medina di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS08-048.
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS08-049
-   Haifei Li del [Fortinet Security Research Team](http://www.fortiguardcenter.com) per aver segnalato un problema descritto nel bollettino MS08-050
-   Vadim Pogulievsky di [Malicious Code Research Center](http://www.finjan.com/securitylab.aspx?id=547) di Finjan per aver segnalato un problema descritto nel bollettino MS08-050
-   Ruben Santamarta di [Reversemode.com](http://reversemode.com/), che collabora con [iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettinon MS08-051.
-   ADLab di [Venustech](http://www.venustech.com.cn/) per aver segnalato un problema descritto nel bollettino MS08-051

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 agosto 2008): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (20 agosto 2008): è stata aggiunta una nota al bollettino MS08-043 nella sezione "Software interessato e posizioni per il download" per chiarire che questo aggiornamento si applica ai server in cui è installato Excel Services, quali la configurazione predefinita di Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services. È stata inoltre aggiunta una nota al bollettino MS08-051 nella sezione "Software interessato e posizioni per il download", riguardo la pubblicazione di nuovi pacchetti di aggiornamento da parte di Microsoft, denominati Versione 2, per Microsoft Office Powerpoint 2003 Service Pack 2 e Microsoft Office Powerpoint 2003 Service Pack 3 nell'Area download Microsoft. I clienti che hanno installato manualmente la Versione 1 di questo aggiornamento dall'Area download di Microsoft devono reinstallare la Versione 2 di questo aggiornamento. I clienti che hanno installato questo aggiornamento utilizzando Microsoft Update o Office Update non devono reinstallarlo.
-   V3.0 (15 ottobre 2008): incluso l'aggiornamento per Snapshot Viewer per Microsoft Access (MS08-041). Gli utenti che hanno installato l'aggiornamento per Microsoft Office 2000 Service Pack 3, Office XP Service Pack 2, Office 2003 Service Pack 2 o Office 2003 Service Pack 3 non devono eseguire una nuova installazione dell'aggiornamento per Snapshot Viewer autonomo per Microsoft Access.

*Built at 2014-04-18T01:50:00Z-07:00*
