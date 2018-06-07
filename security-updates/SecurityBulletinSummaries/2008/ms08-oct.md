---
TOCTitle: 'MS08-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - ottobre 2008'
ms:assetid: 'ms08-oct'
ms:contentKeyID: 61240028
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - ottobre 2008
=================================================================

Data di pubblicazione: martedì 14 ottobre 2008 | Aggiornamento: giovedì 23 ottobre 2008

**Versione:** 3.0

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a ottobre 2008.

Con il rilascio dei bollettini del mese di ottobre 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 9 ottobre 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini l'15 ottobre 2008 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032374639). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (5)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-067                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nel servizio Server può consentire l'esecuzione di codice in modalità remota (958644)**](http://technet.microsoft.com/security/bulletin/ms08-067)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel servizio Server. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un sistema interessato riceve una richiesta RPC appositamente predisposta. Sui sistemi Windows Server 2003, Microsoft Windows 2000 e Windows XP un utente malintenzionato può sfruttare questa vulnerabilità senza autenticazione per eseguire codice arbitrario. È possibile che questa vulnerabilità sia utilizzata per creare uno scenario suscettibile ad attacco da worm. Le configurazioni predefinite standard dei firewall e le procedure consigliate per la configurazione dei firewall consentono di proteggere le risorse di rete dagli attacchi sferrati dall'esterno del perimetro aziendale. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-060                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Active Directory può consentire l'esecuzione di codice in modalità remota (957280)**](http://technet.microsoft.com/security/bulletin/ms08-060)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente relativa alle implementazioni di Active Directory su Microsoft Windows 2000 Server. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato accede alla rete interessata. Questa vulnerabilità interessa soltanto i server di Microsoft Windows 2000 configurati come controller di dominio. Se un server Microsoft Windows 2000 non è stato configurato come controller di dominio, non rileva le query LDAP (Lightweight Directory Access Protocol) o LDAP su SSL (LDAPS) e non è esposto a tale vulnerabilità. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-058                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (956390)**](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente e una divulgata pubblicamente. Tali vulnerabilità possono consentire l'intercettazione di informazioni personali o l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                     |
| **Software interessato**        | **Microsoft Windows, Internet Explorer.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                    |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-059                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità del servizio RPC di Host Integration Server può consentire l'esecuzione di codice in modalità remota (956695)**](http://technet.microsoft.com/security/bulletin/ms08-059)                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Host Integration Server che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente malintenzionato invia una richiesta RPC (Remote Procedure Call) appositamente predisposta a un sistema interessato. I clienti che seguono le procedure consigliate e configurano l'account di servizio SNA RPC in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che configurano l'account di servizio SNA RPC in modo da godere di privilegi amministrativi. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **Microsoft Host Integration Server.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-057                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (956416)**](http://technet.microsoft.com/security/bulletin/ms08-057)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve tre vulnerabilità riscontrate in Microsoft Office Excel che possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Excel appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

Importante (6)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-066                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nel driver di funzioni ausiliario di Microsoft può consentire l'acquisizione di privilegi più elevati (956803)**](http://technet.microsoft.com/security/bulletin/ms08-066)                                                                                                                                                                                                                   |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel driver di funzioni ausiliario di Microsoft. Sfruttando questa vulnerabilità, un utente malintenzionato locale potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                          |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                            |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-061                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (954211)**](http://technet.microsoft.com/security/bulletin/ms08-061)                                                                                                                                                                                             |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e due vulnerabilità segnalate privatamente del kernel di Windows. Sfruttando queste vulnerabilità, un utente malintenzionato locale potrebbe assumere il pieno controllo del sistema interessato. Tali vulnerabilità non possono essere sfruttate in remoto o da utenti anonimi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                       |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                     |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                    |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-062                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità del servizio di stampa Internet di Windows può consentire l'esecuzione di codice in modalità remota (953155)**](http://technet.microsoft.com/security/bulletin/ms08-062)                                                                                                                                                                                                                    |
| **Riepilogo**                   | L'aggiornamento risolve una vulnerabilità segnalata privatamente del servizio di stampa Internet di Windows che può consentire l'esecuzione di codice in modalità remota. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                          |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                         |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                           |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-063                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in SMB (Server Message Block) può consentire l'esecuzione di codice in modalità remota (957095)**](http://technet.microsoft.com/security/bulletin/ms08-063)                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel protocollo SMB (Server Message Block) di Microsoft. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota su un server che condivide file o cartelle. Un utente malintenzionato in grado di sfruttare queste vulnerabilità può installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                      |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                        |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-064                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Vulnerabilità nella manipolazione dei descrittori di indirizzi virtuali può consentire l'acquisizione di privilegi più elevati (956841)**](http://technet.microsoft.com/security/bulletin/ms08-064)                                                                                                                                                                                                                                                                                                                                            |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel descrittore di indirizzi virtuali. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente esegue un'applicazione appositamente predisposta. Sfruttando questa vulnerabilità, un utente malintenzionato può acquisire privilegi più elevati in un sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti amministrativi completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                          |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                            |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-065                                                                                                                                                                                                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Accodamento messaggi può consentire l'esecuzione di codice in modalità remota (951071)**](http://technet.microsoft.com/security/bulletin/ms08-065)                                                                                                                                     |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel servizio di Accodamento messaggi (MSMQ) nei sistemi Microsoft Windows 2000. La vulnerabilità può consentire l'esecuzione di codice in modalità remota nei sistemi Microsoft Windows con il servizio MSMQ attivato. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                            |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                        |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                       |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                         |

Moderato (1)
------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-056                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità di Microsoft Office può consentire l'intercettazione di informazioni personali (957699)**](http://technet.microsoft.com/security/bulletin/ms08-056)                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. Tale vulnerabilità può consentire l'intercettazione di informazioni personali nel momento in cui un utente seleziona un URL CDO appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può introdurre uno script del lato client nel browser dell'utente. Tale script può consentire l'accesso ai contenuti, la divulgazione di informazioni personali e l'esecuzione di tutte le operazioni consentite all'utente del sito Web interessato. |
| **Livello di gravità massimo**  | [Moderato](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Intercettazione di informazioni personali                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

Exploitability Index
--------------------

<span></span>
**Come utilizzare questa tabella**

Utilizzare questa tabella per conoscere la probabilità del rilascio di codice dannoso relativo a ciascuno degli aggiornamenti per la protezione che potrebbe essere necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/en-us/security/cc998259.aspx).

| ID bollettino                                                       | Titolo del bollettino                                                                                                                                                                                  | ID CVE        | Valutazione dell'Exploitability Index                                                                                   | Note fondamentali                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [MS08-056](http://technet.microsoft.com/security/bulletin/ms08-056) | [Una vulnerabilità di Microsoft Office può consentire l'intercettazione di informazioni personali (957699)](http://technet.microsoft.com/security/bulletin/ms08-056)                                   | CVE-2008-4020 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  | È possibile che venga creato del codice dannoso. Il livello di gravità rimane tuttavia basso, poiché la vulnerabilità consente lo spoofing tramite una finestra di dialogo solo in determinati scenari previsti dalle applicazioni Web. Tale vulnerabilità potrebbe dunque riscuotere poca attenzione da parte di utenti malintenzionati.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [MS08-057](http://technet.microsoft.com/security/bulletin/ms08-057) | [Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (956416)](http://technet.microsoft.com/security/bulletin/ms08-057)                               | CVE-2008-4019 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-057](http://technet.microsoft.com/security/bulletin/ms08-057) | [Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (956416)](http://technet.microsoft.com/security/bulletin/ms08-057)                               | CVE-2008-3471 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-057](http://technet.microsoft.com/security/bulletin/ms08-057) | [Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (956416)](http://technet.microsoft.com/security/bulletin/ms08-057)                               | CVE-2008-3477 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-2947 | (pubblico al momento del rilascio del bollettino)                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-3472 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-3473 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-3475 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-3474 | [3 - Scarsa probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx) |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-058](http://technet.microsoft.com/security/bulletin/ms08-058) | [Aggiornamento cumulativo per la protezione di Internet Explorer (956390)](http://technet.microsoft.com/security/bulletin/ms08-058)                                                                    | CVE-2008-3476 | [3 - Scarsa probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx) |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-059](http://technet.microsoft.com/security/bulletin/ms08-059) | [Una vulnerabilità del servizio RPC di Host Integration Server può consentire l'esecuzione di codice in modalità remota (956695)](http://technet.microsoft.com/security/bulletin/ms08-059)             | CVE-2008-3466 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   | Anche se Host Integration Server viene installato di solito solo da alcuni tipi di clienti aziendali, è probabile che venga creato del codice dannoso per questo programma.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| [MS08-060](http://technet.microsoft.com/security/bulletin/ms08-060) | [Una vulnerabilità in Active Directory può consentire l'esecuzione di codice in modalità remota (957280)](http://technet.microsoft.com/security/bulletin/ms08-060)                                     | CVE-2008-4023 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  | È probabile che venga sfruttata tale vulnerabilità per provocare una condizione di Denial of Service. È improbabile tuttavia che venga creato un codice dannoso per eseguire codice in modalità remota, poiché non è possibile controllare la scrittura di indirizzi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| [MS08-061](http://technet.microsoft.com/security/bulletin/ms08-061) | [Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (954211)](http://technet.microsoft.com/security/bulletin/ms08-061)                              | CVE-2008-2250 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-061](http://technet.microsoft.com/security/bulletin/ms08-061) | [Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (954211)](http://technet.microsoft.com/security/bulletin/ms08-061)                              | CVE-2008-2252 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   | È molto probabile che venga creato del codice dannoso per sistemi con più processori.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| [MS08-061](http://technet.microsoft.com/security/bulletin/ms08-061) | [Alcune vulnerabilità del kernel di Windows possono consentire l'acquisizione di privilegi più elevati (954211)](http://technet.microsoft.com/security/bulletin/ms08-061)                              | CVE-2008-2251 | [3 - Scarsa probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx) | È possibile che venga sfruttata tale vulnerabilità, anche se la creazione di un codice dannoso valido e funzionante è piuttosto complessa.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| [MS08-062](http://technet.microsoft.com/security/bulletin/ms08-062) | [Una vulnerabilità del servizio di stampa Internet di Windows può consentire l'esecuzione di codice in modalità remota (953155)](http://technet.microsoft.com/security/bulletin/ms08-062)              | CVE-2008-1446 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   | In alcuni attacchi limitati e mirati è stato rinvenuto del codice dannoso. Se da un lato il servizio IPP (Internet Printing Protocol) è attivato per impostazione predefinita, dall'altro l'accesso a questo servizio tramite IIS richiede l'autenticazione per impostazione predefinita su tutte le piattaforme.                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| [MS08-063](http://technet.microsoft.com/security/bulletin/ms08-063) | [Una vulnerabilità in SMB (Server Message Block) può consentire l'esecuzione di codice in modalità remota (957095)](http://technet.microsoft.com/security/bulletin/ms08-063)                           | CVE-2008-4038 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-064](http://technet.microsoft.com/security/bulletin/ms08-064) | [Una vulnerabilità nella manipolazione dei descrittori di indirizzi virtuali può consentire l'acquisizione di privilegi più elevati (956841)](http://technet.microsoft.com/security/bulletin/ms08-064) | CVE-2008-4036 | [2 - Media probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-065](http://technet.microsoft.com/security/bulletin/ms08-065) | [Una vulnerabilità in Accodamento messaggi può consentire l'esecuzione di codice in modalità remota (951071)](http://technet.microsoft.com/security/bulletin/ms08-065)                                 | CVE-2008-3479 | [3 - Scarsa probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx) | Se da un lato è possibile l'intercettazione di informazioni personali, dall'altro non è sempre possibile accedere al contenuto utile di una memoria. Se è possibile causare un problema di danneggiamento della memoria, è difficile tuttavia eseguire codice in modalità remota.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| [MS08-066](http://technet.microsoft.com/security/bulletin/ms08-066) | [Una vulnerabilità nel driver di funzioni ausiliario di Microsoft può consentire l'acquisizione di privilegi più elevati (956803)](http://technet.microsoft.com/security/bulletin/ms08-066)            | CVE-2008-3464 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [MS08-067](http://technet.microsoft.com/security/bulletin/ms08-067) | [Una vulnerabilità nel servizio Server può consentire l'esecuzione di codice in modalità remota (958644)](http://technet.microsoft.com/security/bulletin/ms08-067)                                     | CVE-2008-4250 | [1 - Alta probabilità di sfruttamento della vulnerabilità](http://technet.microsoft.com/en-us/security/cc998259.aspx)   | In alcuni attacchi limitati e mirati è stato rinvenuto del codice dannoso che interessa Windows XP e Windows Server 2003. Mentre questo servizio è abilitato per impostazione predefinita su tutte le piattaforme interessate, lo sfruttamento della vulnerabilità è più probabile su Microsoft Windows 2000, Windows XP e Windows Server 2003. Le installazioni di default di Windows Vista e Windows Server 2008 richiedono l'autenticazione per le misure di protezione introdotte come parte di UAC, che rafforzano i livelli di integrità. Questo tipo di protezione è attiva anche se il prompt UAC è disabilitato. Anche dopo l'esecuzione dell'autenticazione lo sfruttamento della vulnerabilità è più difficile grazie ai miglioramenti di ASLR e Protezione esecuzione programmi. |

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
Microsoft Windows 2000
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-067**](http://technet.microsoft.com/security/bulletin/ms08-067)
</td>
<td style="border:1px solid black;">
[**MS08-060**](http://technet.microsoft.com/security/bulletin/ms08-060)
</td>
<td style="border:1px solid black;">
[**MS08-058**](http://technet.microsoft.com/security/bulletin/ms08-058)
</td>
<td style="border:1px solid black;">
[**MS08-066**](http://technet.microsoft.com/security/bulletin/ms08-066)
</td>
<td style="border:1px solid black;">
[**MS08-061**](http://technet.microsoft.com/security/bulletin/ms08-061)
</td>
<td style="border:1px solid black;">
[**MS08-062**](http://technet.microsoft.com/security/bulletin/ms08-062)
</td>
<td style="border:1px solid black;">
[**MS08-063**](http://technet.microsoft.com/security/bulletin/ms08-063)
</td>
<td style="border:1px solid black;">
[**MS08-064**](http://technet.microsoft.com/security/bulletin/ms08-064)
</td>
<td style="border:1px solid black;">
[**MS08- 065**](http://technet.microsoft.com/security/bulletin/ms08-065)
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
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=e22eb3ae-1295-4fe2-9775-6f43c5c2aed3)  
(Critico)
</td>
<td style="border:1px solid black;">
[Active Directory in Microsoft Windows 2000 Server Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=8ed7bb9a-4b26-49d7-8c14-60226d2bc20d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=257c0478-56dd-42eb-a90e-607d01613db7)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=02390258-08e9-4b75-960d-be081b749558)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=3a6165a6-d7e7-4526-9291-290caf0639b4)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=8163d1f6-feb5-4f39-8134-3ed42326b822)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=9ed29c3a-0682-4586-bbc2-a73deaa18e4c)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=899e2728-2433-4ccb-a195-05b5d65e5469)  
(Importante)
</td>
</tr>
<tr>
<th colspan="10">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-067**](http://technet.microsoft.com/security/bulletin/ms08-067)
</td>
<td style="border:1px solid black;">
[**MS08-060**](http://technet.microsoft.com/security/bulletin/ms08-060)
</td>
<td style="border:1px solid black;">
[**MS08-058**](http://technet.microsoft.com/security/bulletin/ms08-058)
</td>
<td style="border:1px solid black;">
[**MS08-066**](http://technet.microsoft.com/security/bulletin/ms08-066)
</td>
<td style="border:1px solid black;">
[**MS08-061**](http://technet.microsoft.com/security/bulletin/ms08-061)
</td>
<td style="border:1px solid black;">
[**MS08-062**](http://technet.microsoft.com/security/bulletin/ms08-062)
</td>
<td style="border:1px solid black;">
[**MS08-063**](http://technet.microsoft.com/security/bulletin/ms08-063)
</td>
<td style="border:1px solid black;">
[**MS08-064**](http://technet.microsoft.com/security/bulletin/ms08-064)
</td>
<td style="border:1px solid black;">
[**MS08- 065**](http://technet.microsoft.com/security/bulletin/ms08-065)
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
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0d5f9b6e-9265-44b9-a376-2067b73d6a03)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=a7f0f47b-b1ee-4516-9fbf-bf8e579963d0)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4e73de2b-05e6-4901-9bac-46d8f469e635)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b16d9dac-c430-4dd8-a1e5-9a614801f1d9)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7718bf14-c26c-43f3-be67-4c79ab5b2607)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e7ef571f-c9e8-4e14-95a3-3eeaec55b784)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2f7e5981-6eef-4f08-86c0-c6a7607ea5d0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=25997b73-a640-49c1-b19e-768a18bbe22c)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4c16a372-7bf8-4571-b982-dac6b2992b25)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=234c05fb-988b-4e02-aab6-bb23e447df3d)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ccf7a3e3-ec30-4b95-9a86-00032301513c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5b607efc-c6fb-4079-8478-e4f3262386d3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b06d3a02-b6e4-4d40-913a-3759a31f20f3)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3ae4b913-bff0-4974-b198-828ca10d2a87)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4e1675eb-6b06-48e9-9765-23a2c7737bdc)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=50fae854-0bde-46f8-9444-b9e0d9bfecad)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-067**](http://technet.microsoft.com/security/bulletin/ms08-067)
</td>
<td style="border:1px solid black;">
[**MS08-060**](http://technet.microsoft.com/security/bulletin/ms08-060)
</td>
<td style="border:1px solid black;">
[**MS08-058**](http://technet.microsoft.com/security/bulletin/ms08-058)
</td>
<td style="border:1px solid black;">
[**MS08-066**](http://technet.microsoft.com/security/bulletin/ms08-066)
</td>
<td style="border:1px solid black;">
[**MS08-061**](http://technet.microsoft.com/security/bulletin/ms08-061)
</td>
<td style="border:1px solid black;">
[**MS08-062**](http://technet.microsoft.com/security/bulletin/ms08-062)
</td>
<td style="border:1px solid black;">
[**MS08-063**](http://technet.microsoft.com/security/bulletin/ms08-063)
</td>
<td style="border:1px solid black;">
[**MS08-064**](http://technet.microsoft.com/security/bulletin/ms08-064)
</td>
<td style="border:1px solid black;">
[**MS08- 065**](http://technet.microsoft.com/security/bulletin/ms08-065)
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
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f26d395d-2459-4e40-8c92-3de1c52c390d)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=ae8d22d5-20aa-471d-a423-f54c9d75febe)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=feaf2adf-7892-4dbf-a147-db4d5dbe52f3)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ee88ff2d-1b12-4f4c-a081-9f27a6fba074)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6e696762-d652-4a8f-ab8f-622f9746c320)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=437a9b68-6a0c-48c8-9348-0d6fda48aa21)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dbbebb3f-f1c7-402c-bd16-6f88da0d042c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e8ef3d5f-dd8e-4945-92cd-9d3e30b16667)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c04d2afb-f9d0-4e42-9e1f-4b944a2de400)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=07fc88c4-2571-4a4d-b573-ae576798ab4c)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=319dba34-07ca-47f9-a1e9-20df2df7966b)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ab4d94d3-458c-4946-ab7f-03a279629d25)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=57ca28ea-e5e1-4191-a3d6-84aa90a3d668)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d3df6508-a568-449d-ac97-fbf3f97b98ef)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=989ac6f1-515c-467d-a200-2aabe66d9319)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c2e754f9-086a-494c-bc19-5feed7df8b65)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=ab590756-f11f-43c9-9dcc-a85a43077acf)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=b68937af-f04a-4d1e-9d7f-ec92af5194de)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=47381d91-4a14-4a09-96b3-3345155df52d)  
(Basso)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=63234f85-6e5d-4ef6-b7cf-d1d2c78a5517)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1e6c3f81-85bb-48e6-a5af-635a7e540c93)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=748f54f1-40b9-407c-9819-909061b53743)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=91589cfb-15ba-4dd2-9e3b-107899fbcba6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=5a3832ec-3f8f-42c1-a603-b1330d527547)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="10">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-067**](http://technet.microsoft.com/security/bulletin/ms08-067)
</td>
<td style="border:1px solid black;">
[**MS08-060**](http://technet.microsoft.com/security/bulletin/ms08-060)
</td>
<td style="border:1px solid black;">
[**MS08-058**](http://technet.microsoft.com/security/bulletin/ms08-058)
</td>
<td style="border:1px solid black;">
[**MS08-066**](http://technet.microsoft.com/security/bulletin/ms08-066)
</td>
<td style="border:1px solid black;">
[**MS08-061**](http://technet.microsoft.com/security/bulletin/ms08-061)
</td>
<td style="border:1px solid black;">
[**MS08-062**](http://technet.microsoft.com/security/bulletin/ms08-062)
</td>
<td style="border:1px solid black;">
[**MS08-063**](http://technet.microsoft.com/security/bulletin/ms08-063)
</td>
<td style="border:1px solid black;">
[**MS08-064**](http://technet.microsoft.com/security/bulletin/ms08-064)
</td>
<td style="border:1px solid black;">
[**MS08- 065**](http://technet.microsoft.com/security/bulletin/ms08-065)
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
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=18fdff67-c723-42bd-ac5c-cac7d8713b21)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4756e04b-6e1c-4d78-a3c0-17f6b4b97975)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3483b400-cedc-441f-ba8e-594e3df89190)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9b5995df-a3b8-4e81-b118-9bb057e19884)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=72dd6015-25d1-45f4-a769-88ac43074b44)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b4212db5-093e-497d-b999-2e3780f9f7c2)  
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
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a976999d-264f-4e6a-9bd6-3ad9d214a4bd)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=bd19c72b-4f83-47ab-93be-d2c286e732c4)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=905ab030-14a5-4a3d-aa11-e8f957f6a1ea)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4a0fcf4b-eb8e-456a-b934-400ae18248ee)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f793af16-5464-4db1-a42b-1c5f17c538ed)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c20808cb-c30a-4b53-91e5-810eb6b4b2e3)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="10">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-067**](http://technet.microsoft.com/security/bulletin/ms08-067)
</td>
<td style="border:1px solid black;">
[**MS08-060**](http://technet.microsoft.com/security/bulletin/ms08-060)
</td>
<td style="border:1px solid black;">
[**MS08-058**](http://technet.microsoft.com/security/bulletin/ms08-058)
</td>
<td style="border:1px solid black;">
[**MS08-066**](http://technet.microsoft.com/security/bulletin/ms08-066)
</td>
<td style="border:1px solid black;">
[**MS08-061**](http://technet.microsoft.com/security/bulletin/ms08-061)
</td>
<td style="border:1px solid black;">
[**MS08-062**](http://technet.microsoft.com/security/bulletin/ms08-062)
</td>
<td style="border:1px solid black;">
[**MS08-063**](http://technet.microsoft.com/security/bulletin/ms08-063)
</td>
<td style="border:1px solid black;">
[**MS08-064**](http://technet.microsoft.com/security/bulletin/ms08-064)
</td>
<td style="border:1px solid black;">
[**MS08- 065**](http://technet.microsoft.com/security/bulletin/ms08-065)
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
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=25c17b07-1efe-43d7-9b01-3dfdf1ce0bd7)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ec73f416-2204-42d6-8932-c96578ac819f)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=8b97114a-71aa-47a2-b9e7-f4e158c18c80)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=3d6290d8-1745-4bc0-9ca9-eeb1ad0be4a5)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=cf6744e6-b54c-40f6-a78d-7ba9453133c0)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=ec9eeb82-0497-4c55-94bb-9a47cb3521b4)\*  
(Importante)
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
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=7b12018e-0cc1-4136-a68c-be4e1633c8df)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=baacd1c2-9764-4fea-bd4d-c49791974fef)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=6e641db2-90c8-458f-9795-3e46b70a5203)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=a33c833c-d5c5-4e37-8f89-7b9079f92e59)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=223236e8-7b19-4b47-8a90-bfc35eb9318a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=0bc178b8-f8ae-4f41-8f88-fb6a75be1bca)\*  
(Importante)
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
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=2bcf89ef-6446-406c-9c53-222e0f0baf7a)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=250a45dd-7eae-4440-bd10-02a703940976)  
(Basso)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b6546e1c-bf7b-4354-8574-6c16fa707de0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=31783e88-76e2-4bc6-b4ae-308443c6d223)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=077b697c-04a0-45bd-b08c-331d5c30cb47)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=0af72663-4945-4916-8c55-090ba4d82793)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questi aggiornamenti non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(en-us,vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

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
[**MS08-057**](http://technet.microsoft.com/security/bulletin/ms08-057)
</td>
<td style="border:1px solid black;">
[**MS08-056**](http://technet.microsoft.com/security/bulletin/ms08-056)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
[Excel 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=1b2740e0-ecdd-48ca-84e0-eb187c31eb16)  
(KB955461)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=27cedef1-c47c-472c-a343-cd9b4ebc2bba)  
(KB955464)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1aee2d5-bfa0-40e3-91b6-98bf65524e8c)  
(KB956464)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 2 e Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Excel 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4df27e8a-d803-483b-a700-0177d71bf368)  
(KB955466)  
(Importante)  
[Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4df27e8a-d803-483b-a700-0177d71bf368)  
(KB955466)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office System 2007 e Microsoft Office System 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
[Excel 2007](http://www.microsoft.com/downloads/details.aspx?familyid=2765bbc0-ea2e-4b6e-822c-222ee8e5021f)  
(KB955470)  
(Importante)  
[Excel 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2765bbc0-ea2e-4b6e-822c-222ee8e5021f)  
(KB955470)  
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
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-057**](http://technet.microsoft.com/security/bulletin/ms08-057)
</td>
<td style="border:1px solid black;">
[**MS08-056**](http://technet.microsoft.com/security/bulletin/ms08-056)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=ba4fa21a-7e01-4ef8-9b9f-9d51d00ef094)  
(KB958312)  
(Importante)
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
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=e70c5ae0-2858-46de-81f8-dcd1786656b7)  
(KB958267)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per MAC
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=2a8d9a3b-b8a4-43b6-82a6-a2e7d16ae11d)  
(KB958304)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[**MS08-057**](http://technet.microsoft.com/security/bulletin/ms08-057)
</td>
<td style="border:1px solid black;">
[**MS08-056**](http://technet.microsoft.com/security/bulletin/ms08-056)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer 2003](http://www.microsoft.com/downloads/details.aspx?familyid=9769ce08-5207-4c63-b7b9-536266ad6b2b)  
(KB955468)  
(Importante)  
[Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=9769ce08-5207-4c63-b7b9-536266ad6b2b)  
(KB955468)  
(Importante)  
[Microsoft Office Excel Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=83c88444-75b8-44d1-b280-3671394ade45)  
(KB955935)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=9a7be004-5903-4101-90c5-c0d5f8722af9)  
(KB955936)  
(Importante)  
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=9a7be004-5903-4101-90c5-c0d5f8722af9)  
(KB955936)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007](http://www.microsoft.com/downloads/details.aspx?familyid=5c29e646-504c-4455-9d35-9a1bed6d7535)\*  
(KB955937)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5c29e646-504c-4455-9d35-9a1bed6d7535)\*  
(KB955937)  
(Importante)  
[Microsoft Office SharePoint Server 2007 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=3c21c405-2c9e-45d0-be4d-8ccd093af31f)\*  
(KB955937)  
(Importante)  
[Microsoft Office SharePoint Server 2007 x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3c21c405-2c9e-45d0-be4d-8ccd093af31f)\*  
(KB955937)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
\*Questo aggiornamento si applica ai server che hanno installato Excel Services, come Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet, nella loro configurazione predefinita. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services.

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
Microsoft Host Integration Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-059**](http://technet.microsoft.com/security/bulletin/ms08-059)
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
Microsoft Host Integration Server 2000
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2000 Service Pack 2 (server)](http://www.microsoft.com/downloads/details.aspx?familyid=11cca58b-59a4-4e93-9eb1-19b07c290a10)  
(Critico)  
[Microsoft Host Integration Server 2000 (client amministrativo)](http://www.microsoft.com/downloads/details.aspx?familyid=41b49291-1231-4e23-aef7-818207453d56)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Host Integration Server 2004
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2004 (server)](http://www.microsoft.com/downloads/details.aspx?familyid=9ca255ed-9334-4848-af94-49ef3078cdc0)  
(Critico)  
[Microsoft Host Integration Server 2004 Service Pack 1 (server)](http://www.microsoft.com/downloads/details.aspx?familyid=eca756a1-ca56-4481-b23c-53c159a4e08c)  
(Critico)  
[Microsoft Host Integration Server 2004 (client)](http://www.microsoft.com/downloads/details.aspx?familyid=92cb54e7-f4ff-40a4-99cb-6257c4d8d4cd)  
(Critico)  
[Microsoft Host Integration Server 2004 Service Pack 1 (client)](http://www.microsoft.com/downloads/details.aspx?familyid=d776515c-09aa-4a04-876d-606bfc26a006)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Host Integration Server 2006
</td>
<td style="border:1px solid black;">
[Microsoft Host Integration Server 2006 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=1ae79da3-ec17-4d4b-8011-d777a237ac93)  
(Critico)  
[Microsoft Host Integration Server 2006 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=05da4540-4976-458a-a612-7385d78695a2)  
(Critico)
</td>
</tr>
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

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer e Microsoft Office Detection Tool per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33387) e in [SMS 2.0 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21161).

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

-   [NetAgent Co. Ltd.](http://www.netagent.co.jp/) per aver segnalato un problema descritto nel bollettino MS08-056
-   Joshua J. Drake di [iDefense](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-057.
-   Wushi, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-057.
-   Lionel d'Hauenens di [Labo Skopia](http://www.laboskopia.com/), che collabora con [iDefense VCP](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS08-057.
-   David Bloom per aver segnalato un problema descritto nel bollettino MS08-058.
-   Gregory Rubin per aver segnalato un problema descritto nel bollettino MS08-058.
-   [Ivan Fratric](http://ifsec.blogspot.com/), collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-058.
-   Thierry Zoller di [n.runs](http://www.nruns.com/) per aver segnalato un problema descritto nel bollettino MS08-058.
-   Lee Dagon di [Composica](http://www.composica.com/) per aver segnalato un problema descritto nel bollettino MS08-058.
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [iDefense VCP](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS08-059.
-   Paul Miseiko di [nCircle](http://www.ncircle.com/) per aver segnalato un problema descritto nel bollettino MS08-060.
-   Paul Caton di [iShadow](http://www.ishadow.com/) per aver segnalato un problema descritto nel bollettino MS08-061.
-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino MS08-061.
-   [CERT/CC](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS08-062
-   Morin di Joshua di [Codenomicon](http://www.codenomicon.com/) per aver segnalato un problema descritto nel bollettino MS08-063.
-   Cody Pierce e Aaron Portnoy di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com) per aver segnalato un problema descritto nel bollettino MS08-065
-   Fabien Le Mentec di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino MS08-066.
-   Alex Ionescu (<http://www.alex-ionescu.com/>) per aver segnalato un problema descritto nel bollettino MS08-064.

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 ottobre 2008): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (15 ottobre 2008): rimosso il livello di gravità per Windows Server 2008 per i sistemi basati su Itanium (MS08-062).
-   V2.1 (16 ottobre 2008): È stato aggiornato il Riepilogo per bollettino Microsoft sulla sicurezza MS08-062.
-   V3.0 (23 ottobre 2008): è stato aggiunto il bollettino Microsoft sulla sicurezza MS08-067, la vulnerabilità nel servizio Server può consentire l'esecuzione di codice in modalità remota (958644). E' stato anche aggiunto il link al Webcast dedicato al bollettino straordinario.

*Built at 2014-04-18T01:50:00Z-07:00*
