---
TOCTitle: 'MS11-MAY'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2011'
ms:assetid: 'ms11-may'
ms:contentKeyID: 61240062
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-may(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2011
================================================================

Data di pubblicazione: martedì 10 maggio 2011 | Aggiornamento: martedì 14 giugno 2011

**Versione:** 1.2

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a maggio 2011.

Con il rilascio dei bollettini sulla sicurezza di maggio 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 05 maggio 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 11 maggio 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di maggio](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032455071&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=214807">MS11-035</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Internet Name Service (WINS) può consentire l'esecuzione di codice in modalità remota (2524426)</strong> <br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità di Windows Internet Name Service (WINS), che sono state segnalate a Microsoft privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente riceve un pacchetto di replica WINS appositamente predisposto in un sistema interessato che esegua il servizio WINS. Per impostazione predefinita, WINS non è installato in nessun sistema operativo interessato. Solo i clienti che hanno installato il componente manualmente sono interessati dal problema.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=217670">MS11-036</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft PowerPoint possono consentire l'esecuzione di codice in modalità remota (2545814)</strong> <br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft PowerPoint. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di PowerPoint appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. L'installazione e la configurazione della Convalida file di Office per evitare l'apertura di file sospetti blocca i vettori di attacco per sfruttare le vulnerabilità descritte in CVE-2011-1269 e CVE-2011-1270.</td>
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
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
| ID bollettino                                             | Titolo della vulnerabilità                                                             | ID CVE                                                                           | Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software             | Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software              | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali |  
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------------|  
| [MS11-036](http://go.microsoft.com/fwlink/?linkid=217670) | Vulnerabilità ad attacchi di tipo RCE di danneggiamento della memoria di presentazione | [CVE-2011-1269](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1269) | Non interessato                                                                                                        | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | Non applicabile                                                                  | (Nessuna)         |  
| [MS11-035](http://go.microsoft.com/fwlink/?linkid=214807) | Vulnerabilità legata alla mancata risposta del servizio WINS                           | [CVE-2011-1248](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1248) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Media probabilità di sfruttamento della vulnerabilità   | Temporaneo                                                                       | (Nessuna)         |  
| [MS11-036](http://go.microsoft.com/fwlink/?linkid=217670) | Vulnerabilità ad attacchi di tipo RCE nel sovraccarico del buffer di presentazione     | [CVE-2011-1270](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1270) | Non interessato                                                                                                        | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) – Scarsa probabilità di sfruttamento della vulnerabilità  | Non applicabile                                                                  | (Nessuna)         |
  
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
</tr>
<tr>
<th colspan="2">
Windows Server 2003  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-035**](http://go.microsoft.com/fwlink/?linkid=214807)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0d289146-8470-45dd-a886-d1b35a2c6d4b)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0d3e85a9-42ff-447b-ab8c-095a1c0b224c)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=4c388fe8-883a-4118-a7ff-50f1e9d0a071)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-035**](http://go.microsoft.com/fwlink/?linkid=214807)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9019a3ff-d953-4b0b-8c7a-05aa9cf65c92)\*  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=841130fa-4522-4079-b7eb-f8466ac3ef12)\*  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-035**](http://go.microsoft.com/fwlink/?linkid=214807)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8732b41e-2f25-4ee1-a8b7-a8b8b9e22d08)\*  
(Critico)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

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
[**MS11-036**](http://go.microsoft.com/fwlink/?linkid=217670)
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
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2e8a30ac-bcfe-4535-8ceb-723c25b43d5f)  
(KB2535802)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fc1cfcac-64cc-484a-97f2-3dcfe84cfdcd)  
(KB2535812)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9a181739-709a-4c0d-a97f-f9891c45c04c)  
(KB2535818)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-036**](http://go.microsoft.com/fwlink/?linkid=217670)
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-036**](http://go.microsoft.com/fwlink/?linkid=217670)
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
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5be09069-1cac-4b1e-ac94-4fb7024fb4ac)  
(KB2540162)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS11-036**

<sup>[1]</sup>Gli aggiornamenti per la protezione per Microsoft Office 2004 per Mac (KB2555786), per Microsoft Office 2008 per Mac (KB2555785) e per il convertitore file in formato XML aperto per Mac (KB2555787) sono disponibili a partire dal 14 giugno, 2011. Consultare il bollettino per maggiori informazioni.

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

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

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

-   Luigi Auriemma, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS11-035
-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver collaborato con noi a due problemi descritti nel bollettino MS11-036

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (10 maggio 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (17 maggio 2011): per MS11-036, è stata rimossa una nota a piè di pagina non corretta dalla tabella Software interessato che riguarda gli aggiornamenti per la protezione KB2535818 e KB2540162 per Microsoft PowerPoint 2007 Service Pack 2.
-   V1.2 (14 giugno 2011): Per MS11-036, è stato rivisto questo riepilogo dei bollettini per comunicare che gli aggiornamenti per la protezione per Microsoft Office 2004 per Mac (KB2555786), Microsoft Office 2008 per Mac (KB2555785) e per il convertitore file in formato XML aperto per Mac (KB2555787) sono disponibili. Consultare MS11-036 per maggiori informazioni.

*Built at 2014-04-18T01:50:00Z-07:00*
