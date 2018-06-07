---
TOCTitle: 'MS08-JAN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - gennaio 2008'
ms:assetid: 'ms08-jan'
ms:contentKeyID: 61240022
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-jan(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - gennaio 2008
=================================================================

Data di pubblicazione: martedì 8 gennaio 2008 | Aggiornamento: venerdì 25 gennaio 2008

**Versione:** 1.2

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a gennaio 2008.

Con il rilascio dei bollettini del mese di gennaio 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 3 gennaio 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21163).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 9 gennaio 2008 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di gennaio](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032357213&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (1)
-----------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-001                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Vulnerabilità in Windows TCP/IP possono consentire l'esecuzione di codice in modalità remota (941644)**](http://technet.microsoft.com/security/bulletin/ms08-001)                                                                                                                                                                                                                                                                                                                |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve due vulnerabilità segnalate privatamente relative all'elaborazione del protocollo TCP/IP (Transmission Control Protocol/Internet Protocol). Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato, riuscendo quindi a installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                       |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                        |

Importante (1)
--------------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-002                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in LSASS può consentire l'acquisizione di privilegi più elevati (943485)**](http://technet.microsoft.com/security/bulletin/ms08-002)                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Riepilogo**                   | Questo aggiornamento di livello importante risolve una vulnerabilità segnalata privatamente in Microsoft Windows Local Security Authority Subsystem Service (LSASS). Questa vulnerabilità potrebbe consentire a un utente malintenzionato di eseguire codice arbitrario con privilegi elevati. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato, riuscendo quindi a installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati nel sistema locale                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                        |
| **Software interessato**        | **Windows. **Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma o componente elencato sono riportati l'effetto della vulnerabilità e un collegamento al relativo aggiornamento.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

**Software interessato e posizioni per il download**

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-001**](http://technet.microsoft.com/security/bulletin/ms08-001)
</td>
<td style="border:1px solid black;">
[**MS08-002**](http://technet.microsoft.com/security/bulletin/ms08-002)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<th colspan="3">
Sistemi operativi Windows
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=980f5457-c7b5-421c-8643-0e57429ec156)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7956632e-17d9-4876-8340-84fe3e43e5cc)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=0a766242-2342-4fa0-9b66-8953c54a2211)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=6a4cf182-8e36-490e-aefe-edb7b3a0df9c)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=2e8bc7d5-fe81-4ed5-9efa-360738d160ee)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=51fc657b-2b4a-4725-a744-d279e027c4a5)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=fda060a5-9a1e-4036-9899-13eb61fdd8be)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=12397b47-b18f-4d4d-b8d7-adec8ff310d5)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=19d993f9-06dd-4dc4-b0cc-c59e822eb8fa)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=f19fd790-a4e6-4a8a-8077-d1bbfe37ecca)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=2c2264f7-ebbb-40ab-9dbf-9b4e313665a7)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=0382a195-aa3d-409b-8a79-9fe61588d8a9)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Small Business Server 2003 Service Pack 1, Windows Small Business Server 2003 R2, Windows Small Business Server 2003 R2 Service Pack 2 e Windows Home Server
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=fda060a5-9a1e-4036-9899-13eb61fdd8be)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=23c0e03a-db66-4618-bce0-af55e5c1b067)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=5f6a37b1-c604-47c9-932f-485db2eda133)
</td>
<td style="border:1px solid black;">
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://msdn2.microsoft.com/it-it/embedded/aa731232.aspx3). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723/it).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://www.microsoft.com/italy/technet/security/bulletin/ms07-50120).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/en-us/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33387) e in [SMS 2.0 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21161).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per questo mese:

-   Microsoft ha rilasciato cinque aggiornamenti **non correlati alla protezione** e ad alta priorità su Microsoft Update (MU) e Windows Server Update Services (WSUS).
-   Microsoft ha rilasciato due aggiornamenti **non correlati alla protezione** e ad alta priorità per Windows su Windows Update (WU) e WSUS.

Tenere presente che queste informazioni riguardano **soltanto** gli aggiornamenti **non correlati alla protezione** e ad alta-priorità su Microsoft Update, Windows Update e Windows Server Update Services rilasciati lo stesso giorno del riepilogo dei bollettini sulla sicurezza. **Non** vengono fornite informazioni sugli aggiornamenti **non correlati alla protezione** rilasciati in altri giorni.

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione delle patch](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086/it).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://www.microsoft.com/italy/technet/community/default.mspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   [IBM Internet Security Systems X-Force](http://www.iss.net/) di Alex Wheeler e Ryan Smith per aver segnalato un problema descritto nel bollettino [MS08-001](http://technet.microsoft.com/security/bulletin/ms08-001)
-   [IBM Internet Security Systems X-Force](http://www.iss.net/) di Alex Wheeler e Ryan Smith per aver segnalato un problema descritto nel bollettino [MS08-001](http://technet.microsoft.com/security/bulletin/ms08-001)
-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino [MS08-002](http://technet.microsoft.com/security/bulletin/ms08-002)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 gennaio 2008): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (23 gennaio 2008): riepilogo dei bollettini aggiornato per inserire Windows Small Business Server 2003 Service Pack 2 nei software interessati del bollettino MS08-001.
-   V1.2 (25 gennaio 2008): riepilogo dei bollettini aggiornato per inserire Windows Small Business Server 2003 Service Pack 1, Windows Small Business Server 2003 R2, Windows Small Business Server 2003 R2 Service Pack 2 e Windows Home Server nei software interessati del bollettino MS08-001.

*Built at 2014-04-18T01:50:00Z-07:00*
