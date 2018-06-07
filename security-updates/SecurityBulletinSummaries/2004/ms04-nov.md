---
TOCTitle: 'MS04-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2004'
ms:assetid: 'ms04-nov'
ms:contentKeyID: 61239981
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms04-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2004
==================================================================

Data di pubblicazione: martedì 9 novembre 2004

**Versione:** 1.0

**Data di pubblicazione:** 9 novembre 2004
**Numero di versione:** 1.0

Una versione per gli utenti finali di questo documento è disponibile presso il seguente [sito Web](http://www.microsoft.com/italy/security/default.mspx).

**Protezione dei PC:** per informazioni su come assicurare la protezione dei PC, visitare gli indirizzi seguenti:

-   Informazioni per gli utenti finali: visitare il sito Web [Proteggi il tuo PC](http://www.microsoft.com/italy/athome/security/default.mspx).
-   Informazioni per i professionisti IT: visitare il sito Web [Security Guidance Center](http://www.microsoft.com/italy/security/guidance/default.mspx).

**Strategie per la gestione degli aggiornamenti:** per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare il sito Web [Patch Management, Security Updates, and Downloads](http://go.microsoft.com/fwlink/?linkid=21168).

**IT Pro Security Zone Community:** visitando il [sito Web IT Pro Security Zone](http://go.microsoft.com/fwlink/?linkid=21164) è possibile ottenere informazioni su come migliorare la protezione e ottimizzare l'infrastruttura IT utilizzata, nonché discutere con altri professionisti IT le varie problematiche relative alla sicurezza.

**Servizio di notifica sulla sicurezza Microsoft:** per ricevere automaticamente una notifica per posta elettronica ogni volta che viene pubblicato un bollettino Microsoft sulla sicurezza, è possibile sottoscrivere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

#### Riepilogo

Questo bollettino include gli aggiornamenti per alcune vulnerabilità scoperte di recente, elencate di seguito in ordine di gravità.

Importante (1)
--------------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS04-039                                                                     |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | Una vulnerabilità in ISA Server 2000 e Proxy Server 2.0 può consentire lo spoofing di contenuti Internet (888258) |
| **Riepilogo**                   | La vulnerabilità può consentire all'autore di un attacco lo spoofing di contenuti Internet attendibili.           |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                               |
| **Effetti della vulnerabilità** | Spoofing                                                                                                          |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".    |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma o componente elencato sono riportati l'effetto della vulnerabilità e un collegamento al relativo aggiornamento.

**Software interessato e posizioni per il download**

|                                                                                                                                                   | Dettagli                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Identificatore del bollettino**                                                                                                                 | **MS04-039**                                                                                                |
| **Livello di gravità massimo**                                                                                                                    | [**Importante**](http://technet.microsoft.com/security/bulletin/rating)                                     |
| **Software interessato:**                                                                                                                         |                                                                                                             |
| Microsoft Internet Security and Acceleration Server 2000 Service Pack 1 e Microsoft Internet Security and Acceleration Server 2000 Service Pack 2 | [Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7a4c318f-5ac9-4cf2-8792-a4a62076ebe7) |
| Microsoft Small Business Server 2000 (che include Microsoft Internet Security and Acceleration Server 2000)                                       | [Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7a4c318f-5ac9-4cf2-8792-a4a62076ebe7) |
| Microsoft Small Business Server 2003 Premium Edition (che include Microsoft Internet Security and Acceleration Server 2000)                       | [Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7a4c318f-5ac9-4cf2-8792-a4a62076ebe7) |
| Microsoft Proxy Server 2.0 Service Pack 1                                                                                                         | [Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7a4c318f-5ac9-4cf2-8792-a4a62076ebe7) |

Deployment
----------

<span></span>
**Systems Management Server:**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire il deployment controllato di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per il deployment degli aggiornamenti per la protezione, visitare il [sito Web SMS 2003 Security Patch Management](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Service Feature Pack](http://go.microsoft.com/fwlink/?linkid=33340) per semplificare il deployment degli aggiornamenti per la protezione. Per ulteriori informazioni su SMS, visitare il [sito Web SMS](http://go.microsoft.com/fwlink/?linkid=21158).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e il deployment degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, visitare il seguente [sito Web](http://go.microsoft.com/fwlink/?linkid=33341). Per alcuni aggiornamenti per la protezione può essere necessario disporre di diritti amministrativi ed eseguire il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare lo strumento Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=33387) e in [SMS 2.0 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=21161).

#### Altre informazioni:

**Ringraziamenti**

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato con noi al fine di proteggere i sistemi dei clienti:

-   Martijn de Vries di Info Support per aver individuato la vulnerabilità legata allo spoofing e Thomas de Klerk di Info Support per aver segnalato questa vulnerabilità (CAN-2004-0892).

**Download di altri aggiornamenti per la protezione:**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch".
-   Gli aggiornamenti per i sistemi consumer sono disponibili nel [sito Web Windows Update](http://go.microsoft.com/fwlink/?linkid=21130).

**Supporto tecnico:**

-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Supporto Tecnico Microsoft](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Gli interventi di assistenza relativi agli aggiornamenti di protezione sono gratuiti. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il [sito Web del supporto internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

**Fonti di informazioni sulla sicurezza:**

-   Nella sezione dedicata alla sicurezza del sito Web [Microsoft TechNet](http://www.microsoft.com/italy/technet/security/default.mspx) sono disponibili ulteriori informazioni sulla protezione e la sicurezza dei prodotti Microsoft.
-   [Microsoft Software Update Services](http://go.microsoft.com/fwlink/?linkid=21133)
-   [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134) (MBSA)
-   [Windows Update](http://go.microsoft.com/fwlink/?linkid=21130)
-   Catalogo di Windows Update:per ulteriori informazioni sul catalogo di Windows Update, vedere l'articolo della Microsoft Knowledge Base [323166](http://support.microsoft.com/default.aspx?scid=kb;en-us;323166).
-   [Office Update](http://go.microsoft.com/fwlink/?linkid=21135)

**Dichiarazione di non responsabilità:**

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Conseguentemente, Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

**Versioni:**

-   V1.0 (9 novembre 2004): pubblicazione del bollettino

*Built at 2014-04-18T01:50:00Z-07:00*
