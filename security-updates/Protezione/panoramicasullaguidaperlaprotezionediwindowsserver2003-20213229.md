---
TOCTitle: Panoramica sulla Guida per la protezione di Windows Server 2003
Title: Panoramica sulla Guida per la protezione di Windows Server 2003
ms:assetid: '9911b568-c474-465f-998f-4f0fa31bebc6'
ms:contentKeyID: 20213229
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163140(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Panoramica

La *Guida per la protezione di Windows server 2003* aggiornata fornisce suggerimenti specifici su come aumentare il livello di protezione dei computer che eseguono Windows Server 2003 con SP1 in tre ambienti aziendali distinti: uno in cui devono essere supportati i sistemi operativi più datati come Windows NT 4.0 e Windows 98, uno in cui Windows 2000 è la versione meno aggiornata del sistema operativo Windows in uso, e uno in cui l'importanza della protezione delle informazioni è talmente critica che la perdita di funzionalità client e di semplicità di gestione è considerata un compromesso accettabile per conseguire la massima protezione. All'interno della guida, questi tre ambienti sono rispettivamente denominati Legacy Client (LC), Enterprise Client (EC) e Specialized Security – Limited Functionality (SSLF).

Per un gruppo di ruoli di server diversi vengono fornite le istruzioni su come aumentare la protezione dei computer in questi tre ambienti. Le contromisure descritte e gli strumenti forniti presumono che ogni server svolgerà un unico ruolo. Se è necessario abbinare i ruoli di alcuni dei server nell'ambiente in uso, è possibile personalizzare i modelli di protezione contenuti nella versione scaricabile della guida per creare la combinazione appropriata di servizi e di opzioni di protezione. I ruoli server descritti in questa guida comprendono:

-   Controller di dominio che forniscono anche servizi DNS

-   Server infrastruttura che forniscono servizi WINS e DHCP

-   File server

-   Server di stampa

-   Server Web con Microsoft Internet Information Services (IIS).

-   Server IAS (Internet Authentication Services)

-   Server Servizi certificati

-   Host Bastion

Le informazioni sono state organizzate in modo da risultare di facile accesso, consentendo di trovare rapidamente le informazioni necessarie e determinare le impostazioni appropriate per i computer dell'organizzazione. Sebbene questa guida sia rivolta a clienti aziendali, molte delle informazioni contenute sono idonee ad organizzazioni di qualsiasi dimensione.

Per utilizzare in modo ottimale il materiale, è necessario leggere l'intera guida. È inoltre possibile consultare la guida correlata, [Pericoli e contromisure: Impostazioni di Protezione in Windows Server 2003 e Windows XP](http://technet.microsoft.com/it-it/library/dd162275), che è disponibile all'indirizzo www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.

##### In questa pagina

[](#eeaa)[Destinatari della guida](#eeaa)
[](#edaa)[Panoramica della guida](#edaa)
[](#ecaa)[Risorse correlate](#ecaa)
[](#ebaa)[Commenti e suggerimenti](#ebaa)
[](#eaaa)[Servizi di consulenza e assistenza](#eaaa)

### Destinatari della guida

Questa guida è rivolta principalmente a consulenti, specialisti della protezione, architetti di sistema e professionisti IT responsabili delle fasi di pianificazione dello sviluppo di applicazioni o infrastrutture e dell'installazione di workstation Windows Server 2003. La guida non è destinata a utenti privati.

Gli specialisti della protezione e gli architetti IT possono avere bisogno di informazioni più dettagliate sulle impostazioni di protezione descritte in questa guida. Ulteriori informazioni sono riportate nella guida correlata, [Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP](http://technet.microsoft.com/it-it/library/dd162275), all'indirizzo www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della guida

#### Capitolo 1: Introduzione alla Guida per la protezione di Windows Server 2003

Questo capitolo fornisce una panoramica sulla *Guida per la protezione di Windows Server 2003* e contiene una breve panoramica di ogni capitolo. Descrive inoltre gli ambienti Legacy Client, Enterprise Client e SSLF (Specialized Security – Limited Functionality) e i computer in essi presenti.

#### Capitolo 2: Meccanismi di protezione avanzata di Windows Server 2003

Questo capitolo fornisce una panoramica dei principali meccanismi utilizzati per aumentare il livello di protezione di Windows Server 2003 con SP1 in questa guida: Configurazione guidata impostazioni di sicurezza (SCW) e criteri di gruppo Active Directory. Viene illustrata la modalità con cui SCW fornisce una struttura interattiva per creare, gestire e verificare i criteri di protezione per i computer basati su Windows Server 2003 che svolgono ruoli server diversi. Viene fornita anche una valutazione sulle capacità di SCW entro il contesto dei tre ambienti descritti nel Capitolo 1.

La seconda parte di questo capitolo contiene le descrizioni generali della struttura di Active Directory, di quella dell'unità organizzativa (OU), degli oggetti Criteri di gruppo (GPO), della struttura del gruppo amministrativo e del criterio di dominio. Questi argomenti sono discussi nel contesto dei tre ambienti descritti nel Capitolo 1 e forniscono una visione di un ambiente finale ideale e protetto.

Questo capitolo termina con un esame dettagliato di come questa guida combini le funzionalità migliori di SCW e gli approcci tradizionali basati su GPO per rafforzare Windows Server 2003 con SP1.

#### Capitolo 3: Criteri di dominio

In questo capitolo vengono analizzate le impostazioni del modello di protezione e le contromisure aggiuntive per i criteri a livello di dominio nei tre ambienti descritti nel Capitolo 1. Il capitolo non pone l'attenzione su un ruolo specifico del server, ma bensì sui criteri e sulle impostazioni specifiche utili per criteri di dominio di livello superiore.

#### Capitolo 4: Criterio di base per un server membro

L'obiettivo principale di questo capitolo è costituito dalla definizione di criteri di base dei server membro (MSBP) per i ruoli di server esaminati più avanti in questa guida.

#### Capitolo 5: Criterio di base per il controller di dominio

Il ruolo del server del controller di dominio è uno dei più importanti ruoli da proteggere in qualsiasi ambiente di Active Directory sui computer che eseguono Windows Server 2003 con SP1. La perdita o la compromissione di un controller di dominio potrebbe danneggiare seriamente i computer client, i server e le applicazioni che si affidano a tali controller per l’autenticazione, i criteri di gruppo e una directory LDAP (Lightweight Directory Access Protocol) centrale. Nei tre ambienti descritti nella guida, i controller di dominio forniscono anche i servizi di DNS.

#### Capitolo 6: Ruolo del server di infrastruttura

In questo capitolo, il ruolo del server infrastruttura è fornire servizi DHCP o WINS Vengono forniti dettagli su come il Windows Server 2003 con i server di infrastruttura SP1 nell'ambiente in uso possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dal criterio di base per un server membro (MSBP).

#### Capitolo 7: Ruolo di File server

Questo capitolo descrive come aumentare la protezione dei computer che fungono da file server e quali sono gli aspetti correlati più impegnativi. I servizi più essenziali per i file server richiedono l'uso di protocolli relativi a NetBIOS Windows e di protocolli SMB e CIFS. I protocolli SMB e CIFS sono di solito utilizzati per fornire l'accesso a utenti autenticati ma, se non sono protetti in modo adeguato, possono anche rivelare abbondanti informazioni a utenti non autenticati o a pirati informatici. A causa di questo pericolo, questi protocolli sono spesso disattivati negli ambienti con protezione elevata. Questo capitolo descrive come i file server che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dall'MSBP.

#### Capitolo 8: Ruolo del server di stampa

Questo capitolo si concentra sui server di stampa. Come i file server, i servizi più essenziali offerti dai server di stampa richiedono l'uso di protocolli relativi a NetBIOS Windows e di protocolli SMB e CIFS. Come accennato in precedenza, questi protocolli sono spesso disattivati in ambienti con protezione elevata. Questo capitolo descrive come le impostazioni di protezione del server di stampa di Windows Server 2003 con SP1 possono essere rafforzate in vari modi non eseguiti dall'MSBP.

#### Capitolo 9: Ruolo del server Web

Questo capitolo descrive come, per proteggere a fondo i siti Web e le applicazioni, sia necessario proteggere un intero server IIS (compreso ciascun sito Web e applicazione eseguiti sul server IIS) da computer client presenti nell'ambiente in uso. I siti Web e le applicazioni devono inoltre essere protetti da altri siti Web e applicazioni eseguiti sullo stesso server IIS. Nel presente capitolo sono descritte anche le procedure necessarie a garantire che queste misure siano realizzate dai server IIS che eseguono Windows Server 2003 con SP1 nell'ambiente in uso.

#### Capitolo 10: Ruolo del server IAS

I server IAS (Internet Authentication Servers) offrono il servizio RADIUS (Remote Authentication Dial-In User Services), un protocollo di autenticazione basato su standard, progettato per verificare l'identità di client che accedono alle reti in modalità remota. Questo capitolo descrive il modo in cui i server IAS che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dall'MSBP.

#### Capitolo 11: Ruolo del server dei servizi certificati

I servizi certificati offrono i servizi di gestione della crittografia e dei certificati necessari a sviluppare un'infrastruttura a chiave pubblica (PKI) nell'ambiente server in uso. Questo capitolo descrive come i server IAS che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione non applicate dal criterio MSBP.

#### Capitolo 12: Ruolo di host Bastion

I computer client possono accedere ai server host Bastion tramite Internet. In questo capitolo si spiega come questi computer esposti al pubblico siano esposti ad attacchi da parte di un vasto numero di utenti che possono rimanere completamente anonimi. Poiché molte organizzazioni non estendono la loro infrastruttura di dominio a Internet, il contenuto di questo capitolo si concentra su come rafforzare i computer autonomi con Windows Server 2003 con SP1 che non appartengono a un dominio di Active Directory

#### Capitolo 13: Conclusioni

Il capitolo finale riassume brevemente i punti salienti dei capitoli precedenti.

#### Appendice A: Formati e strumenti di protezione

Sebbene la *Guida per la protezione di Windows Server 2003* si concentri su come utilizzare SCW per creare i criteri che sono poi convertiti in modelli di protezione e in oggetti di Criteri di gruppo, esistono tutta una serie di altri strumenti e formati di file che possono essere usati per ampliare o sostituire questa metodologia. Questa appendice fornisce una lista ristretta di questi strumenti e formati.

#### Appendice B: Impostazioni principali da considerare

La *Guida per la protezione di Windows Server 2003* si occupa di molte contromisure e impostazioni di protezione, ma è importante comprendere che una parte di esse sono particolarmente importanti. Questa appendice descrive le impostazioni che avranno un maggiore impatto sulla protezione dei computer che utilizzano Windows Server 2003 con SP1.

#### Appendice C: Sommario di impostazione del modello di protezione

Questa appendice introduce il foglio di lavoro Microsoft Excel "[Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)" contenuta con gli strumenti e i modelli nella [versione scaricabile](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en) di questa guida all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14846 (in inglese). Il presente foglio di calcolo è una copia originale completa sotto forma di modulo compatto e facile da usare di tutte le impostazioni consigliate per i tre ambienti che sono definiti in questa guida.

#### Appendice D: Verifica della Guida per la protezione di Windows  Server  2003

La *Guida per la protezione di Windows Server 2003* contiene molte informazioni su come aumentare la protezione dei server con Windows Server 2003 con SP1, ma si consiglia il lettore di controllare e convalidare sempre tutte le impostazioni prima di implementarle in un ambiente di produzione.

Questa appendice contiene informazioni su come creare un ambiente di laboratorio di prova idoneo che può essere utilizzato per garantire la corretta implementazione delle impostazioni consigliate in un ambiente di produzione. Aiuta gli utenti a eseguire la convalida necessaria e minimizza l'ammontare di risorse necessarie a farlo.

#### Strumenti e modelli

Nella versione scaricabile della guida è allegata una raccolta di modelli di protezione, script e strumenti aggiuntivi per consentire all'organizzazione di valutare, verificare e implementare le contromisure consigliate. I modelli di protezione sono file di testo che possono essere importati nei criteri di gruppo basati sul dominio o applicati localmente tramite lo Snap-in Analisi e configurazione della protezione con Microsoft Management Console (MMC). Queste procedure sono descritte in dettaglio nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003". Tra gli script contenuti in questa guida vi sono quelli per creare e collegare oggetti Criteri di gruppo oltre a script di prova che sono usati per verificare le contromisure consigliate.

[](#mainsection)[Inizio pagina](#mainsection)

### Risorse correlate

Per ulteriori informazioni sulle impostazioni di protezione descritte in questa guida, scaricare la guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275) all'indirizzo www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx e la [*Guida per la protezione di Windows XP*](http://technet.microsoft.com/it-it/library/cc163061) all'indirizzo www.microsoft.com/italy/technet/security/prodtech/windowsxp/secwinxp/default.mspx. Sono inoltre disponibili [altre soluzioni per la protezione](http://technet.microsoft.com/en-us/security/bb977553.aspx) offerte dal team MSSC (Microsoft Solutions for Security and Compliance) all'indirizzo www.microsoft.com/technet/community/columns/sectip/st0805.msp.

[](#mainsection)[Inizio pagina](#mainsection)

### Commenti e suggerimenti

Il team MSSC (Microsoft Solutions for Security and Compliance) è interessato a eventuali commenti e suggerimenti offerti su questa e altre soluzioni per la protezione.

Opinioni e pareri Utilizzare il [Blog sulle soluzioni per la sicurezza per professionisti IT](http://blogs.technet.com/secguide) (in inglese).

Oppure inviare consigli e suggerimenti tramite posta elettronica all'indirizzo: [SecWish@microsoft.com.](mailto:secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003) Commenti e suggerimenti inviati a questa casella di posta ricevono spesso risposta.

Grazie della collaborazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Servizi di consulenza e assistenza

Sono disponibili molti servizi che forniscono assistenza alle organizzazioni impegnate a garantire la protezione dei propri sistemi. Utilizzare i seguenti collegamenti per individuare i servizi necessari:

Per Microsoft Gold Certified Partner, Microsoft Certified Technical Education Center, Microsoft Certified Partner e ISV (ISV, Independent Software Vendor) che utilizzano le tecnologie Microsoft, effettuare una ricerca in [Microsoft Solution Finder](https://solutionfinder.microsoft.com) all'indirizzo https://solutionfinder.microsoft.com.

Per trovare servizi di consulenza e assistenza adatti alle necessità della propria organizzazione, consultare [Microsoft Services](http://www.microsoft.com/services/microsoftservices/default.mspx) all'indirizzo http://support.microsoft.com/msservices.

**Download**

[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)

[](#mainsection)[Inizio pagina](#mainsection)
