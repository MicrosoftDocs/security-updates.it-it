---
TOCTitle: 'MS07-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2007'
ms:assetid: 'ms07-nov'
ms:contentKeyID: 61240015
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms07-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2007
==================================================================

Data di pubblicazione: martedì 13 novembre 2007

**Versione:** 1.0

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a novembre 2007.

Con il rilascio dei bollettini del mese di novembre 2007, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente l'8 novembre 2007. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 14 novembre 2007 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di novembre](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032344694&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (1)
-----------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-061                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità legata alla gestione degli URI Windows può consentire l'esecuzione di codice in modalità remota (943460)**](http://technet.microsoft.com/security/bulletin/ms07-061)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | L'aggiornamento risolve una vulnerabilità segnalata pubblicamente. Nella shell Windows esiste una vulnerabilità legata all'esecuzione di codice in modalità remota nel modo in cui Windows gestisce URI inviati e appositamente predisposti. Se la shell di Windows non esegue una convalida appropriata degli URI, un utente malintenzionato potrebbe sfruttare la vulnerabilità eseguendo codice non autorizzato. Microsoft ha individuato i possibili modi di sfruttare questa vulnerabilità, che riguarda solo i sistemi con Internet Explorer 7. Tuttavia, la vulnerabilità è presente in un file di Windows, Shell32.dll, incluso in tutte le edizioni supportate di Windows XP e Windows Server 2003. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

Importante (1)
--------------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-062                                                                                                                                                                                                                                                                                                                                                               |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in DNS può consentire attacchi di spoofing (941672)**](http://technet.microsoft.com/security/bulletin/ms07-062)                                                                                                                                                                                                                                                                        |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello importante risolve una vulnerabilità segnalata privatamente a Microsoft. Questa vulnerabilità di spoofing esiste nei server DNS di Windows e può consentire a un utente malintenzionato di inviare risposte appositamente predisposte alle richieste DNS, eseguendo lo spoofing o il reindirizzamento del traffico di Internet dalle posizioni legittime. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                         |
| **Effetti della vulnerabilità** | Spoofing                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema, tranne nel caso di situazioni particolari.                                                                                                                                                                                    |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                |

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
[**MS07-061**](http://technet.microsoft.com/security/bulletin/ms07-061)
</td>
<td style="border:1px solid black;">
[**MS07-062**](http://technet.microsoft.com/security/bulletin/ms07-062)
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
Microsoft Windows 2000 Server Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=c80fcd9b-d0f8-44db-96fc-bf2ead054ff4)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=8ba1c2f9-1bde-4e97-b327-21259c5e5104)
</td>
<td style="border:1px solid black;">
** **
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=4ef7fdd7-8887-4c64-a70c-c6ae734d7c5f)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=4ef7fdd7-8887-4c64-a70c-c6ae734d7c5f)
</td>
<td style="border:1px solid black;">
** **
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=e5d8a866-2c1f-4035-8325-c1be61a75c3b)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=ed8e2cb4-bcd9-40fc-9ad6-46b364d0656d)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=e5d8a866-2c1f-4035-8325-c1be61a75c3b)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?displaylang=it&familyid=ed8e2cb4-bcd9-40fc-9ad6-46b364d0656d)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=bf26da08-15b8-4d65-ba12-4cc74c7a1326)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d1323e14-ffa7-4d03-a2a7-9240c192a75e)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=bf26da08-15b8-4d65-ba12-4cc74c7a1326)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d1323e14-ffa7-4d03-a2a7-9240c192a75e)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=1c055f11-3273-4a4c-a33f-bf61ac9ec4c5)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=f3ad67de-85ad-452d-a1e0-0af3faf969d6)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=1c055f11-3273-4a4c-a33f-bf61ac9ec4c5)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=f3ad67de-85ad-452d-a1e0-0af3faf969d6)
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

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Nota** Dopo il 9 ottobre 2007, il file MSSecure.XML utilizzato da MBSA 1.2.1 non verrà più aggiornato. Dopo questa data, non verranno aggiunti nuovi aggiornamenti per la protezione al file MSSecure.XML utilizzato da MBSA 1.2.1 e non verranno rilasciate nuove versioni di Enterprise Scan Tool. Non sono interessati gli strumenti Security Update Inventory Tool (SUIT) o Extended Security Update Inventory Tool (ESUIT) per SMS 2.0 e SMS 2003. Per ulteriori informazioni, visitare [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=50120).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per la distribuzione degli aggiornamenti per la protezione, visitare il sito [Gestione delle patch per la protezione con SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://go.microsoft.com/fwlink/?linkid=33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://go.microsoft.com/fwlink/?linkid=33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=33387) e in [SMS 2.0 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=21161).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per questo mese:

-   Microsoft ha rilasciato tre aggiornamenti **non correlati alla protezione** e ad alta priorità su Microsoft Update (MU) e Windows Server Update Services (WSUS).
-   Microsoft non ha rilasciato aggiornamenti **non correlati alla protezione** e ad alta priorità per Windows su Windows Update (WU).

Tenere presente che queste informazioni riguardano **soltanto** gli aggiornamenti **non correlati alla protezione** e ad alta-priorità su Microsoft Update, Windows Update e Windows Server Update Services rilasciati lo stesso giorno del riepilogo dei bollettini sulla sicurezza. **Non** vengono fornite informazioni sugli aggiornamenti **non correlati alla protezione** rilasciati in altri giorni.

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione delle patch](http://go.microsoft.com/fwlink/?linkid=21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086/it).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://www.microsoft.com/italy/technet/community/default.mspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Jesper Johansson per aver collaborato con noi su un problema descritto nel bollettino MS07-061
-   Carsten H. Eiram di [Secunia](http://corporate.secunia.com/) per aver collaborato con noi su un problema descritto nel bollettino MS07-061
-   Aviv Raff di [Finjan](http://www.finjan.com/) per aver collaborato con noi su un problema descritto nel bollettino MS07-061
-   Petko Petkov di [GNUCITIZEN](http://www.gnucitizen.org/) per aver collaborato con noi su un problema descritto nel bollettino MS07-061
-   Alla Berzroutchko di [Scanit](http://www.scanit.be/) per aver segnalato un problema descritto nel bollettino MS07-062
-   Amit Klein di [Trusteer](http://www.trusteer.com/) per aver segnalato un problema descritto nel bollettino MS07-062

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (13 novembre 2007): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
