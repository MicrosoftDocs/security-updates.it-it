---
TOCTitle: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Capitolo 4'
Title: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Capitolo 4'
ms:assetid: '7371d0f8-e181-4f8a-a550-ea829c64c2e7'
ms:contentKeyID: 20200898
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536299(v=TechNet.10)'
---

Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft
==============================================================================================================

### Capitolo 4: Progettazione della soluzione

Aggiornato: 24 maggio 2005

##### In questa pagina

[](#eeaa)[Introduzione](#eeaa)
[](#edaa)[Implementazione dell'accesso remoto per i telelavoratori](#edaa)
[](#ecaa)[Considerazioni aggiuntive](#ecaa)
[](#ebaa)[Implementazione di monitoraggio e gestione](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Una volta acquisita familiarità con i fattori di cui è necessario tenere conto per l'implementazione di una soluzione con rete privata virtuale (VPN), è possibile dedicarsi al processo di progettazione. La progettazione prevede l'individuazione degli elementi di pianificazione essenziali e l'esecuzione di un'analisi dei requisiti della soluzione.

In Woodgrove National Bank si sono identificati i problemi di natura aziendale, tecnica e di protezione che è necessario affrontare con la soluzione. In questo capitolo vengono illustrati i problemi di pianificazione che gli architetti di sistema hanno esaminato, le conclusioni a cui sono giunti e le decisioni che hanno preso per la creazione della soluzione prescelta.

[](#mainsection)[Inizio pagina](#mainsection)

### Implementazione dell'accesso remoto per i telelavoratori

I telelavoratori di Woodgrove National Bank che operano da postazioni remote necessitano di connessioni alla rete aziendale coerenti e affidabili. Le eventuali difficoltà o dei ritardi eccessivi nella connessione provocano disagio e un calo della fiducia nel servizio. L'implementazione della quarantena sulla VPN può anche aumentare il disagio percepito dall'utente, a causa dell'aumento dei tempi necessari per la connessione alla rete. Il reparto IT di Woodgrove National Bank deve sottoporre a monitoraggio i ritardi di connessione e intraprendere delle azioni per ridurre al minimo tali ritardi. È necessario creare script di connessione che consentano di tenere gli utenti informati su tutte le fasi del processo di connessione.

Per gli amministratori di rete è fondamentale che, prima di accedere alle risorse della rete, i computer in accesso remoto soddisfino tutti i criteri di accesso alla rete. Il modo migliore di proteggere la rete aziendale consiste nel mettere in quarantena i computer in accesso remoto e nel verificare che questi soddisfino i criteri di protezione della rete prima di concedere l'accesso alle risorse di rete.

#### Soluzione concettuale

Per la soluzione si utilizza una combinazione di script pre-connessione, agenti client e componenti di Microsoft® Windows Server™ 2003 con Service Pack 1 (SP1). I computer client avviano la connessione VPN utilizzando un profilo di Connection Manager personalizzato. Un profilo di Connection Manager è un eseguibile autoestraente creato con CMAK (Connection Manager Administration Kit) che comprende script e impostazioni. Uno script di azione pre-tunnel richiede che il client aggiorni le impostazioni di protezione prima di creare la connessione VPN. I computer in accesso remoto ottengono gli aggiornamenti da server connessi a Internet gestiti da Woodgrove National Bank, dal fornitore dell'antivirus e dal sito Web Windows Update.

Sul computer client, dopo l'esecuzione degli aggiornamenti richiesti, viene creata una connessione VPN e vengono autenticate le credenziali dell'utente a fronte dei servizi di directory di Active Directory® utilizzando il Servizio autenticazione Internet (IAS). Sul server di accesso remoto la connessione in ingresso viene quindi limitata tramite l'utilizzo di filtri di pacchetti di quarantena che consentono solo un accesso alle risorse limitato. Dopo la conferma da parte dall'agente del client della conformità del computer ai necessari criteri di protezione, il server di accesso remoto rimuove le limitazioni della quarantena e il computer client ha la possibilità di accedere a tutte le risorse autorizzate della Intranet.

#### Prerequisiti della soluzione

Prima di avviare un progetto di questa natura, è necessario rispettare alcuni prerequisiti. Nella sezione che segue sono riportati alcuni prerequisiti di carattere generale per la connessione VPN in quarantena.

##### Consultare gli utenti e i gruppi

Quando si pianifica una modifica che influisce sui servizi offerti agli utenti, è essenziale consultare gli utenti e i gruppi coinvolti. Gli utenti possono offrire utili commenti e suggerimenti relativi a problemi e livelli di prestazioni dei servizi esistenti. Sempre dagli utenti possono giungere indicazioni su funzioni e aspettative che riguardano il nuovo servizio. È necessario, d'altra parte, che gli utenti comprendano cosa possono o non possono aspettarsi realmente dal servizio. La gestione delle aspettative è un aspetto chiave da curare per ottenere l'accettazione della novità da parte degli utenti. L'organizzazione può giudicare realisticamente il successo del progetto solo se si definiscono degli obiettivi misurabili.

Woodgrove opera in diversi paesi e regioni in tutto il mondo e si avvale di servizi di supporto tecnico regionali. Il team iniziale ha raccolto molti commenti degli utenti e dei team di supporto per individuare possibili utenti, gruppi e personale di supporto da includere nei progetti pilota.

##### Reclutare il team del progetto

Prima di implementare un progetto di questo tipo, è importante accertarsi di disporre del giusto mix di personale e competenze. Il team del progetto deve valutare con attenzione se le competenze necessarie sono già presenti in azienda oppure se è necessario assumere personale aggiuntivo. Dal momento che di norma non è richiesta la partecipazione dell'intero organico a ogni fase del progetto, è necessario determinare il livello di disponibilità che ciascuno deve assicurare per tutta la durata del progetto. Le funzioni aziendali necessarie sono architetti di rete, gestori della rete, team di gestione dei server, sviluppatori di script, team di protezione dell'infrastruttura e team di gestione del progetto.

#### Pianificazione della soluzione

Durante il processo di pianificazione, Woodgrove ha previsto la necessità di:

-   Implementare progetti pilota o test.

-   Amministrare i server della rete perimetrale con Servizi terminal.

-   Aggiornare gli script di quarantena.

-   Raccogliere i dati relativi alle prestazioni.

##### Implementare progetti pilota o test

Il numero e l'ampiezza dei progetti pilota dipendono dalle dimensioni e dalla scala dell'organizzazione. In Woodgrove sono stati implementati due progetti pilota. Lo scopo del primo era di effettuare una verifica funzionale e coinvolgere utenti di accesso remoto esperti per mettere in evidenza i potenziali punti deboli e minimizzare gli eventuali problemi di carattere aziendale e tecnologico. Durante il progetto pilota iniziale, si è concesso un accesso limitato alle risorse aziendali per verificare che nessuno dei computer risultati conformi ai criteri di protezione introducesse dei rischi. In qualsiasi organizzazione che decida di implementare una soluzione con connessione VPN in quarantena è necessario accertarsi che nessun computer infetto oppure non dotato degli aggiornamenti appropriati possa superare la barriera della quarantena, prima che nell'organizzazione venga implementata la soluzione e che la rete aziendale resti quindi esposta. Nel secondo progetto pilota è stata coinvolta una base di utenti molto più ampia, con la partecipazione di alcuni utenti privi di esperienza, nell'intento di creare un ambiente di test più realistico con tutti i problemi di assistenza che è probabile che sorgano.

##### Amministrare i server della rete perimetrale con Servizi terminal

Il team IT di Woodgrove utilizza la modalità di amministrazione di Servizi terminal per la gestione dei server esistenti nella rete perimetrale. A tale elenco vanno ora aggiunti i server di aggiornamento connessi a Internet e i server di accesso remoto VPN. A tale elenco, sono stati aggiunti dal team IT di Woodgrove i server di aggiornamento connessi a Internet e i server di accesso remoto VPN. È stato quindi necessario affrontare il problema dell'aggiornamento e manutenzione di questi importanti server.

##### Aggiornare gli script di quarantena

Nel corso del tempo è necessario aggiornare gli script di quarantena con nuove build dei profili di Connection Manager. In Woodgrove si è deciso di distribuire i profili di Connection Manager tramite un server Web che richiede un'autenticazione dell'utente. Agli utenti in accesso remoto viene inviato un messaggio di posta elettronica come notifica di un punto di distribuzione.

##### Raccogliere i dati relativi alle prestazioni

La misurazione delle prestazioni è una componente chiave per il continuo miglioramento del servizio. Prestazioni, affidabilità e protezione dei server in Woodgrove devono essere sottoposti a monitoraggio continuo. È necessario che il team di gestione della rete sia in grado di integrare la soluzione di connessione VPN in quarantena nella struttura esistente di monitoraggio e gestione.

#### Architettura della soluzione

Per la soluzione di connessione VPN in quarantena di Woodgrove National Bank sono necessari i seguenti componenti:

-   Computer client che utilizzino Windows XP Professional con SP2 o versioni successive.

-   Profili di Connection Manager creati con CMAK.

-   Script lato client integrati nei pacchetti client di Connection Manager.

-   Componente client della connessione VPN in quarantena.

-   Un server di accesso remoto che utilizzi Windows Server 2003 con SP1 o versione successiva e con installato Servizio quarantena accesso remoto.

-   Un filtro della porta IP di quarantena.

-   IAS (Internet Authentication Service, servizio di autenticazione Internet) in esecuzione su Windows Server 2003.

-   Active Directory

Nel reparto IT di Woodgrove si era inizialmente deciso di fornire il supporto per tutte le versioni di Windows distribuite. Tuttavia, la maggiore consapevolezza delle minacce cui sono soggetti i computer connessi a Internet ha convinto il personale IT a scegliere Windows XP Professional con SP2 come opzione standard. Sebbene sia possibile connettersi tramite VPN con computer che utilizzano Windows XP Home Edition con SP2, in Woodgrove si è deciso di non supportare tale configurazione, dal momento che non è possibile unire a un dominio un computer basato su Windows XP Home Edition. Quando la soluzione iniziale verrà implementata dal reparto IT, in Woodgrove si intende estendere tale soluzione anche ai computer dei telelavoratori.

Una delle verifiche di pre-connessione consiste nel confermare l'attivazione di Windows Firewall. In Woodgrove non viene specificata alcuna eccezione nello script, ma sono impostate eccezioni come post-connessione di Desktop remoto.

CMAK è lo strumento utilizzato per la configurazione del profilo di Connection Manager che contiene tutto il software concesso in licenza necessario per avviare il tentativo di connessione, compresi il componente di notifica del client (RQC.exe) e lo script di quarantena iniziale. In Woodgrove National Bank si utilizza un server Web per la distribuzione dei profili. Quando in Woodgrove National Bank viene aggiornato il profilo di Connection Manager, agli utenti viene notificato tramite posta elettronica che è obbligatorio adottare il nuovo profilo entro una certa data.

**Nota:** è possibile adottare strategie alternative che prevedano dei meccanismi di distribuzione del software, ad esempio Criteri di gruppo, Microsoft Systems Management Server (SMS) 2003 oppure, per gli utenti che si connettono alla rete aziendale utilizzando i propri computer domestici, la memorizzazione del profilo su una chiave USB protetta da password.

Con l'accesso remoto di Windows Server 2003 vengono fornite funzionalità che consentono di impostare host e router VPN. In Windows Server 2003 con SP1 è presente Servizio quarantena accesso remoto (RQS), un componente chiave della soluzione di connessione VPN in quarantena. RQS è il componente listener del server, implementato come file eseguibile, RQS.exe. In CMAK è compreso il componente di notifica (RQC.exe).

Il filtro della porta di quarantena consente solo comunicazioni tra un client VPN in quarantena e alcune risorse limitate della rete. I filtri dei pacchetti consentono all'agente client di comunicare con il componente listener sul server di accesso remoto e rendono possibile l'autenticazione dell'utente.

Il servizio IAS in esecuzione su Windows Server 2003 rappresenta l'implementazione Microsoft di un server e di un proxy RADIUS. L'IETF (Internet Engineering Task Force) descrive RADIUS negli RFC 2865 e 2866. Con IAS vengono autenticate le richieste di accesso remoto e vengono fornite le informazioni sugli account. Woodgrove ha sottoscritto dei contratti con diversi ISP, che forniscono il servizio di accesso Internet in roaming in più paesi e aree geografiche. Presso gli ISP i server RADIUS sono configurati in modo da passare le richieste di autenticazione ai server IAS di Woodgrove. Il processo di autenticazione richiede l'impiego presso gli ISP di un proxy RADIUS con i server RADIUS configurato in modo da puntare verso i server IAS di Woodgrove. Grazie all'adozione del servizio IAS per le autorizzazioni, è possibile sfruttare le funzionalità di gestione degli account di RADIUS per la registrazione dell'utilizzo della VPN di accesso remoto.

Gli account utente e l'appartenenza ai gruppi in Active Directory regolano la connettività remota e il conseguente accesso alle risorse aziendali di Woodgrove National Bank. In Woodgrove National Bank vengono inoltre utilizzati gli oggetti Criteri di gruppo (GPO) per configurare le workstation Windows affinché soddisfino i criteri di protezione della rete aziendale.

#### Funzionamento della soluzione

Nella figura seguente viene illustrata l'implementazione della soluzione di connessione VPN in quarantena adottata in Woodgrove National Bank.

[![](images/Dd536299.vppgch04_PGFG0401(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536299.vppgch04_pgfg0401_big(it-it,technet.10).gif)

**Figura 4.1 Processo di connessione VPN in quarantena in Woodgrove National Bank**

La soluzione di connessione VPN in quarantena di Woodgrove National Bank funziona nel modo seguente:

1.  L'utente seleziona il profilo di connessione VPN. In alternativa, un'applicazione richiede una risorsa presente sull'Intranet aziendale.

2.  Il profilo di Connection Manager avvia una connessione a Internet utilizzando una voce di accesso remoto. Se il client è già connesso a Internet, questo passaggio viene ignorato in Connection Manager.

3.  Le azioni pre-tunnel personalizzate avviano degli script per verificare che il computer sia dotato degli aggiornamenti e delle firme dei virus per il programma antivirus utilizzato più recenti. Il computer client si connette a Windows Update per l'installazione degli aggiornamenti. Per esaminare degli esempi di script personalizzati utilizzabili come azioni pre-tunnel personalizzate, consultare l'appendice A, "Esempi di script di quarantena" in questa guida.

4.  Se gli aggiornamenti vengono applicati in modo corretto, con il profilo di Connection Manager verrà avviata la connessione al server VPN. In caso di errori durante l'aggiornamento, l'utente viene informato dal profilo di Connection Manager e il tentativo di connessione VPN viene interrotto.

5.  Il computer client di accesso remoto passa le credenziali di autenticazione al server di accesso remoto, che invia un messaggio di richiesta di accesso RADIUS al server IAS. Con IAS si autenticano le credenziali dell'utente a fronte di Active Directory. Se le credenziali sono valide, verranno verificati i criteri di accesso remoto per l'utente.

6.  Il server VPN accetta la connessione e imposta timeout di quarantena e attributi del filtro IP. Il server IAS invia un messaggio di accettazione accesso RADIUS che contiene gli attributi MS-Quarantine-IPfilter e MS-Quarantine-Session-Timeout. Il server VPN applica tali attributi al filtro di quarantena e azzera il timer della sessione. A questo punto al computer client in accesso remoto è consentito di trasmettere solo traffico che corrisponda ai filtri di quarantena. Il client in accesso remoto deve notificare al server di accesso remoto che lo script di quarantena è stato eseguito in modo corretto entro il numero di secondi specificato nell'attributo MS-Quarantine-Session-Timeout.

7.  Il componente listener notifica al server di accesso remoto che il client è conforme ai requisiti dei criteri. Il server di accesso remoto riceve la notifica perché rispetta la regola del traffico (porta 7250) specificata nell'attributo MS-Quarantine-IPfilter. Sul server di accesso remoto vengono rimosse le impostazioni MS-Quarantine-IPfilter e MS-Quarantine-Session-Timeout dalla connessione e vengono configurate le normali limitazioni per la connessione, definite nei criteri per l'accesso remoto.

8.  A questo punto l'utente può accedere a tutti i contenuti per cui è autorizzato.

**Nota:** uno script di post-connessione controlla la versione di Connection Manager. Se l'applicazione sul computer remoto è precedente di due o più versioni principali, oppure di tre o più versioni secondarie, rispetto alla versione corrente, il computer remoto scarica il pacchetto di Connection Manager più recente, informa l'utente e interrompe la connessione. Non appena sul computer remoto sarà disponibile l'elenco di aggiornamenti rapidi più recente, l'utente remoto potrà rieseguire la connessione.

Per l'implementazione di questa soluzione, è necessario che sui lati client e server vengano eseguiti alcuni processi. Nella sezione seguente vengono descritti tali requisiti.

##### Implementazione di azioni personalizzate tramite l'utilizzo di script

La maggior parte delle operazioni sul lato client per la soluzione di connessione VPN in quarantena vengono eseguite dagli script avviati in alcune fasi del ciclo di connessione. Un elemento fondamentale della soluzione dipende dall'esecuzione di determinate verifiche come pre-tunnel o post-connessione. Se una determinata verifica non viene eseguita nella sequenza prevista, il computer resterà esposto a vulnerabilità evitabili creando ulteriori difficoltà. Nella sezione che segue è riportato un elenco dei controlli progettati per questa soluzione.

###### Implementazione delle verifiche pre-tunnel

Se il client non è ancora connesso a Internet, la connessione a Internet viene avviata da Connection Manager. Dopo la connessione del client a Internet, le azioni pre-tunnel eseguono sincronicamente le eventuali verifiche di protezione obbligatorie prima della creazione del tunnel VPN.

Connection Manager esegue tutte le necessarie verifiche di protezione in sequenza, implementando ogni verifica come una serie di script. Le operazioni riportate di seguito illustrano la logica di lavoro a cui è necessario attenersi per gli script.

1.  **Il sistema operativo del client è supportato?**

    -   Se non lo è, visualizzare un messaggio per l'utente e interrompere la connessione.

    -   Se lo è, continuare.

2.  **Il software antivirus è installato e in esecuzione?** 

    -   Se non lo è, visualizzare un messaggio per l'utente e interrompere la connessione. Se un'azione pre-tunnel necessita di applicazioni software con licenza, queste devono essere incluse nell'installazione di Connection Manager, in modo da evitare la necessità di eseguire l'installazione da un server remoto.

    -   Se lo è, continuare.

3.  **Aggiornare i file delle firme antivirus**

    -   Se l'esito è positivo, continuare.

    -   Se non lo è, procedere con un'avvertenza oppure visualizzare un messaggio per l'utente e interrompere la connessione.

4.  **Il client di Aggiornamenti automatici di Windows è configurato?**

    -   Se non lo è, configurare il client di Aggiornamenti automatici di Windows.

    -   Se l'esito è positivo, continuare.

    -   In caso contrario, procedere con un avviso oppure visualizzare un messaggio per l'utente e interrompere la connessione.

    -   Se lo è, continuare.

5.  **Scaricare e installare gli aggiornamenti ad alta priorità.**

    -   Se l'esito è positivo, continuare.

    -   Se non lo è, procedere con un'avvertenza oppure visualizzare un messaggio per l'utente e interrompere la connessione.

6.  **Richiedere l'utilizzo di "Accesso con connessione remota" (facoltativo)**

    -   Se è già utilizzato, continuare.

    -   Se non lo è, procedere con un'avvertenza oppure visualizzare un messaggio per l'utente e interrompere la connessione. L'utilizzo di questa opzione comporta che possono connettersi solo i computer del dominio e che i client remoti devono essere aggiunti al dominio eseguendo almeno una volta la connessione alla LAN aziendale. Se si utilizza questa opzione, l'accesso al dominio su una connessione remota non sarà possibile a meno che dal reparto IT di Woodgrove non venga definita un'eccezione temporanea alle verifiche di protezione obbligatorie (vedere l'argomento Gestione di eccezioni ed esclusioni in questo capitolo).

7.  **Eseguire le eventuali altre verifiche di protezione personalizzate (facoltativo)**

    Poiché a questo punto del processo di connessione è disponibile solo l'accesso a Internet, è necessario progettare le verifiche di protezione personalizzate tenendo presente questa limitazione.

**Nota:** per esaminare una serie di script di esempio, consultare l'appendice A, "Esempi di script di quarantena" in questa guida.

Connection Manager memorizza i risultati delle azioni pre-tunnel nella seguente chiave del Registro di sistema:

**HKEY\_CURRENT\_USER\\Software\\MyCompany\\MyConnectionManager\\PreTunnelResults.**

Le azioni pre-tunnel devono sempre avere esito positivo ed è sempre necessario verificare i risultati con l'azione post-connessione dell'agente Servizio quarantena accesso remoto per determinare lo stato da inviare al server VPN. Un approccio di questo tipo consente di gestire le eccezioni in modo flessibile, senza alcuna modifica di Connection Manager. Nella figura seguente è illustrata la logica dello script dell'azione personalizzata pre-tunnel utilizzata in Woodgrove National Bank.

[![](images/Dd536299.vppgch04_PGFG0402(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536299.vppgch04_pgfg0402_big(it-it,technet.10).gif)

**Figura 4.2 Azioni pre-tunnel utilizzate in Woodgrove National Bank**

###### Implementazione delle verifiche post-connessione

Dopo che il client ha superato tutte le verifiche pre-tunnel, Connection Manager procede a stabilire una connessione VPN. Con gli script post-connessione è possibile eseguire eventuali verifiche aggiuntive non obbligatorie e azioni di gestione dopo che il client ha ottenuto l'accesso alla rete aziendale.

1.  **Connessione VPN**

    Dopo il completamento delle azioni pre-tunnel, Connection Manager procede a stabilire una connessione con il server VPN.

2.  **Invio della notifica**

    In Connection Manager viene utilizzato il componente client (RQC.exe) per inviare la chiave condivisa a Servizio quarantena accesso remoto (RQS.exe) sul server VPN, che quindi non terrà più conto dei criteri di quarantena.

3.  **Scadenza della password**

    In Woodgrove National Bank viene eseguito uno script per la verifica della scadenza delle password, con conseguente notifica agli utenti della necessità di cambiare la password.

    **Nota:** la notifica di scadenza della password viene inviata solo quando il client utilizza l'opzione **Accesso con connessione remota** per la connessione remota alla rete aziendale.

4.  **Aggiornamento di Criteri di gruppo**

    Se un client aggiunto al dominio non utilizza l'opzione **Accesso con connessione remota** per la connessione remota alla rete aziendale, gli aggiornamento di Criteri di gruppo non vengono applicati. Ne può conseguire una falla nella protezione quando si utilizza Criteri di gruppo per impostare opzioni di protezioni fondamentali sui client. Per limitare gli effetti negativi causati da questo problema, in Woodgrove National Bank viene eseguito uno script di post-connessione per l'aggiornamento di Criteri di gruppo dopo l'accesso dell'utente. Lo script utilizza il comando **gpupdate.exe /force /wait:0** ** **per aggiornare immediatamente le impostazioni di Criteri di gruppo. Per ulteriori informazioni sulle utilità di aggiornamento di Criteri di gruppo, vedere [Descrizione dell'utilità di aggiornamento dei criteri di gruppo](http://support.microsoft.com/default.aspx?scid=kb;it-it;298444) all'indirizzo http://support.microsoft.com/default.aspx?scid=kb;it-it;298444.

Nella figura seguente sono illustrati i dettagli della logica dello script dell'azione personalizzata post-connessione.

[![](images/Dd536299.PGFG0403(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536299.pgfg0403_big(it-it,technet.10).gif)

**Figura 4.3 Azioni post-connessione utilizzate in Woodgrove National Bank**

##### Creazione e distribuzione di profili di Connection Manager

In Connection Manager è disponibile un comodo meccanismo per fornire agli utenti un accesso rapido, semplice e affidabile alle risorse aziendali. In Woodgrove National Bank si è deciso di implementare le connessioni VPN personalizzate utilizzando i profili di Connection Manager creati dal reparto IT con CMAK.

Poiché presso Woodgrove National Bank si configurano connessioni per decine di migliaia di client e centinaia di numeri di telefono di accesso, prima di procedere alla configurazione, devono essere esaminate dal reparto IT le seguenti informazioni:

-   Le configurazioni in accesso remoto o le connessioni VPN variano, in base a fattori quali la posizione, l'ora del giorno e così via.

-   Per prevenire eventuali errori, agli utenti non è consentito configurare o modificare le proprietà di accesso remoto o della connessione VPN.

-   Alcune funzioni devono essere dinamiche e i valori corrispondenti vengono gestiti dallo staff IT di Woodgrove in modo da garantire la conformità ai criteri di protezione.

-   È necessario scalare il metodo di configurazione per le esigenze di un'azienda che opera a livello globale.

Nella tabella seguente sono illustrate alcune delle funzionalità di Connection Manager per le connessioni di accesso remoto utilizzate dal reparto IT di Woodgrove.

**Tabella 4.1: Funzionalità di Connection Manager utilizzate dal reparto IT di Woodgrove**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Funzionalità</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Personalizzazione</p></td>
<td style="border:1px solid black;"><p>Elementi grafici, icone, messaggi e guida in linea personalizzati conferiscono al pacchetto un aspetto conforme all'immagine aziendale. Con i pacchetti di Connection Manager è possibile garantire numeri di supporto locali per gli utenti che viaggiano molto.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Azioni personalizzate</p></td>
<td style="border:1px solid black;"><p>Per eseguire registrazione e aggiornamento delle applicazioni.</p></td>
</tr>
</tbody>
</table>
  
In Woodgrove è possibile distribuire agli utenti remoti i profili di Connection Manager tramite CD, posta elettronica, sito Web o condivisione dei file. Presso Woodgrove National Bank si è già affermata l'abitudine di distribuire software e aggiornamenti tramite un sito Web connesso a Internet. Dal momento che l'infrastruttura di supporto esiste già, si è deciso di utilizzare questo metodo anche per distribuire i profili di Connection Manager.
  
##### Utilizzo dei filtri IP per l'accesso in rete in quarantena
  
La combinazione di azioni personalizzate e supporto per attributi specifici dei fornitori consente a Connection Manager di supportare l'accesso alla rete in quarantena. Gli attributi specifici dei fornitori sono estensioni consentite dello standard RADIUS RFC 2138, ma da questo non definite. Gli attributi del fornitore Microsoft che la versione per Windows Server 2003 di IAS specifica sono:
  
-   MS-Quarantine-IPFilter
  
-   MS-Quarantine-Session-Timeout
  
###### Impostazione di MS-Quarantine-IPFilter
  
Questa impostazione consente di accettare traffico in ingresso proveniente dal componente di notifica del client (RQC) dopo il corretto completamento dello script. Sulla rete di Woodgrove National Bank, ad esempio, devono essere consentiti i protocolli DNS e DHCP, in modo che i client remoti possano comunicare con i server dell'infrastruttura durante le operazioni di quarantena.
  
**Nota:** l'utilizzo di filtri per consentire protocolli specifici comporta una riduzione complessiva del livello di protezione. È preferibile includere tali protocolli nella definizione della quarantena solo quando strettamente necessario.
  
Nella tabella seguente sono indicate le porte TCP/IP aperte dal filtro IP della soluzione di quarantena di Woodgrove National Bank.
  
**Tabella 4.2: Porte TCP/IP aperte dal filtro di connessione VPN in quarantena**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Numero di porta</p></th>
<th><p>Uso</p></th>
<th><p>Commenti</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>UDP 67, 68</p></td>
<td style="border:1px solid black;"><p>DHCP</p></td>
<td style="border:1px solid black;"><p>Richiede un indirizzo IP per il client</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>UDP 53</p></td>
<td style="border:1px solid black;"><p>DNS</p></td>
<td style="border:1px solid black;"><p>Risoluzione dei nomi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>UDP 137</p></td>
<td style="border:1px solid black;"><p>WINS</p></td>
<td style="border:1px solid black;"><p>Risoluzione nomi NetBIOS</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>TCP 139, 445</p></td>
<td style="border:1px solid black;"><p>Condivisione file</p></td>
<td style="border:1px solid black;"><p>Attivare solo se strettamente necessario, attiva sessione NetBIOS e condivisione file SMB</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>TCP 7250</p></td>
<td style="border:1px solid black;"><p>RQC, RQS</p></td>
<td style="border:1px solid black;"><p>Attiva la comunicazione tra agente client di connessione VPN in quarantena e componente listener sul lato server</p></td>
</tr>
</tbody>
</table>
  
###### MS-Quarantine-Session-Timeout
  
Con questo attributo si imposta il timeout massimo per la quarantena del computer client. Se lo script non viene portato a termine entro questo periodo di tempo, il computer client viene disconnesso dal server di accesso remoto. In Woodgrove National Bank è stato implementato un limite di timeout di 120 secondi, che consente di ridurre a meno dell'1% le connessioni in ingresso scartate.
  
Nella figura seguente vengono illustrati gli attributi specifici del fornitore per cui è necessaria una configurazione nei criteri di accesso remoto per il supporto della connessione VPN in quarantena.
  
[![](images/Dd536299.PGFG0404(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536299.pgfg0404_big(it-it,technet.10).gif)
  
**Figura 4.4 Attributi specifici del fornitore MS-Quarantine necessari per la connessione VPN in quarantena.**
  
Durante i test del progetto pilota, verificare se la rimozione di ciascuna delle porte consentite nel filtro IP della quarantena impedisce al client di connettersi. Ridurre il valore del timeout all'impostazione minima praticabile, quindi aggiungere un ulteriore periodo di tempo per l'incremento della latenza di rete o per i collegamenti più lenti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni aggiuntive
  
In questa sezione vengono esaminate le altre aree prese in considerazione dal reparto IT di Woodgrove durante l'implementazione della connessione VPN in quarantena.
  
#### Configurazione di registrazione e account
  
Un indubitabile vantaggio dell'utilizzo di IAS è costituito dal supporto integrato per la registrazione delle connessioni client tramite RADIUS. Woodgrove National Bank intende monitorare le connessioni dei dipendenti alla rete aziendale. La registrazione non è un requisito per l'implementazione di una soluzione di accesso remoto che utilizzi la connessione VPN in quarantena, ma Microsoft ne consiglia caldamente l'adozione. Grazie a RADIUS/IAS, Woodgrove è in grado di analizzare le tendenze di connessione con lo scopo di migliorare il servizio.
  
Su ciascun server IAS RADIUS vengono raccolti i dati delle sessioni utente in SQL Server 2000 Desktop Engine (MSDE 2000), che è un database SQL Server 2000 locale semplificato. All'interno del database è possibile raccogliere i dati delle prestazioni di server infrastruttura e i dati specifici dei client ed è possibile eseguire il database su ciascuno dei server IAS con cui si raccolgono i dati delle sessioni utente.
  
Con il server IAS si trasferiscono i dati da MSDE a un database SQL Server 2000 centrale quasi in tempo reale. Questa impostazione garantisce un utilizzo conveniente delle licenze SQL Server e non influisce negativamente sulle prestazioni.
  
Woodgrove National Bank ha distribuito nelle varie aree geografiche i server preposti alla raccolta dati basati su SQL Server per raccogliere i dati delle sessioni di accesso remoto. Per ulteriori informazioni sulla configurazione di SQL Server per la registrazione con IAS, vedere l'argomento [Distribuzione della registrazione SQL Server con Servizio autenticazione Internet (IAS) di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=6e4357f7-4070-4902-95f1-3ad411d963b2&displaylang=en) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyId=6E4357F7-4070-4902-95F1-3AD411D963B2&displaylang=en (informazioni in lingua inglese).
  
#### Implementazione di distribuzioni pilota
  
Prima di procedere alla distribuzione di una soluzione di accesso remoto in un ambiente di produzione, è necessario sottoporre la soluzione a test in una distribuzione pilota. La distribuzione pilota ideale è una versione in scala ridotta della soluzione pianificata.
  
In Woodgrove National Bank si sono implementati due programmi pilota: un programma pilota iniziale per utenti esperti e un programma pilota più generale aperto a una più ampia gamma di partecipanti. Il programma pilota è stato monitorato dal team IT di Woodgrove e i risultati sono stati utilizzati per correggere il progetto finale.  
  
#### Garanzia di un'elevata disponibilità
  
Poiché Woodgrove National Bank opera su mercati globali con sedi in tutto il mondo, lo scenario di soluzione deve essere estremamente affidabile. Quindi in Woodgrove National Bank è necessario valutare soluzioni che garantiscano un'elevata disponibilità del sistema:
  
-   Più server VPN con bilanciamento del carico.
  
-   Server IAS con bilanciamento del carico.
  
-   Server con tolleranza d'errore per l'aggiornamento di software e antivirus.
  
-   Percorsi di rete interni ridondanti per garantire che un guasto a un router o switch non impedisca l'accesso ai server interni.
  
In Woodgrove si utilizza Microsoft Application Center 2000 per fornire supporto a cluster di applicazioni Web e a Bilanciamento carico di rete (NLB) per i siti Web. Con Application Center e NLB è inoltre possibile garantire la tolleranza d'errore per i server di aggiornamento connessi a Internet. In Woodgrove National Bank si utilizza NLB, una funzionalità standard di Windows Server 2003 Enterprise Edition che consente di bilanciare il carico tra i server IAS.
  
#### Garanzia di una larghezza di banda adeguata per la rete
  
Gli architetti di sistema devono valutare i percorsi di rete esistenti, i tempi di connessione previsti e il tipo e l'estensione del traffico di accesso remoto previsto. La larghezza di banda aggiuntiva di cui necessitano gli utenti remoti non deve essere sottovalutata.
  
Le implementazioni dei progetti pilota devono contribuire all'analisi del traffico ad accesso remoto e dell'effetto che tale traffico può avere sull'infrastruttura di rete esistente. È importante che nelle prove siano coinvolti utenti ordinari che fanno un uso generico del sistema, perché l'adozione della soluzione non può avere successo se la qualità del servizio offerto è scadente. Gli switch di rete che includono dei profili per la larghezza di banda possono ridurre gli effetti del traffico ad accesso remoto sugli altri utenti.
  
La connettività Internet in Woodgrove National Bank è buona e la larghezza di banda disponibile più che sufficiente. La maggior parte della larghezza di banda della banca viene impiegata per l'accesso interno a Internet, per la navigazione sul Web e la posta elettronica, quindi potrebbe essere necessario intervenire per gestire al meglio il traffico in accesso remoto aggiuntivo.
  
#### Gestione di eccezioni ed esclusioni
  
Gli architetti di sistema di Woodgrove National Bank sono consapevoli che qualsiasi soluzione deve essere in grado di affrontare anche situazioni in cui le esigenze aziendali richiedono che uno o più dispositivi siano esonerati dal rispetto dei requisiti di quarantena adottati di solito. Potrebbe essere necessario, ad esempio, definire un'eccezione per l'accesso dei dirigenti durante una riunione importante. Per questo motivo è opportuno che la soluzione di accesso VPN supporti le eccezioni.
  
L'impossibilità di prevedere eccezioni per singoli computer potrebbe costringere l'amministratore a rimuovere i requisiti di accesso remoto. La soluzione potrà essere distribuita dal team IT solo quando l'organizzazione sarà in grado di gestire le singole eccezioni.
  
**Nota:** il gruppo di protezione del reparto IT di Woodgrove è l'unica autorità che può determinare se le esigenze aziendali giustificano il rischio di protezione che un eventuale esonero comporta.
  
Nell'organizzazione è necessario considerare i seguenti scenari di eccezione:
  
-   **Membri esterni al dominio**. Nelle aziende può essere necessario consentire l'accesso alla rete anche a client remoti che non sono membri di un dominio. Tuttavia tali eccezioni comportano un ulteriore lavoro di gestione dal momento che per molte altre opzioni di protezione e gestione è richiesto Criteri di gruppo, che è disponibile solo per i computer membri di un dominio.
  
-   **Opzione di accesso al dominio**. Se un utente di un computer aggiunto a un dominio non seleziona l'opzione accesso Windows quando si connette utilizzando Connection Manager, in Windows l'accesso viene eseguito con le credenziali memorizzate nella cache. Quando le password vengono cambiate o scadono, è possibile che le credenziali memorizzate nella cache non consentano di ottenere l'autenticazione.
  
-   **Timeout dell'applicazione**. Quando un computer resta in quarantena troppo a lungo provocando il timeout di un'applicazione, è possibile che l'applicazione provochi dei problemi. Il risultato potrebbe essere il danneggiamento dei dati.
  
Una possibile soluzione per questo problema consiste nel creare filtri dei pacchetti in ingresso che consentano il normale passaggio del traffico dell'applicazione durante la quarantena del client di accesso remoto. Lo svantaggio di questo tipo di approccio è rappresentato dall'ulteriore carico di lavoro necessario per l'identificazione del traffico di rete dell'applicazione e la creazione di ulteriori filtri dei pacchetti.
  
Per risolvere il problema, è consigliabile ridurre al minimo necessario il numero di filtri dei pacchetti di quarantena e utilizzare le azioni personalizzate pre-tunnel. L'implementazione non corretta di filtri dei pacchetti di quarantena potrebbe esporre i controller di dominio alla rete di quarantena.
  
Con alcune configurazioni è possibile ridurre il ritardo che le applicazioni subiscono quando si connettono a una rete di quarantena. Anche se Microsoft non consiglia di adottare configurazioni che espongano la rete, è necessario prevedere soluzioni adatte per le applicazioni essenziali all'interno delle organizzazioni. Le soluzioni da prendere in considerazione sono le seguenti:
  
-   Fornire indicazioni agli utenti
  
-   Utilizzare solo un timeout della sessione di quarantena
  
-   Utilizzare notifiche immediate
  
##### Fornire indicazioni agli utenti
  
È possibile fornire delle indicazioni agli utenti sfruttando l'interfaccia di Connection Manager, per informarli sullo stato di avanzamento del processo di connessione. In tal modo si riduce il senso di disagio provato dagli utenti quando sembra che non stia accadendo nulla.
  
##### Utilizzare solo un timeout della sessione di quarantena
  
Per questo tipo di configurazione è necessario impostare l'attributo MS-Quarantine-Session-Timeout, ma non l'attributo MS-Quarantine-IPFilter. Il server di accesso remoto consente al client di accesso remoto di accedere immediatamente in modo normale, senza le limitazioni imposte dai filtri dei pacchetti di quarantena. Tuttavia, il client di accesso remoto deve comunque inviare un messaggio di notifica che confermi la conformità ai criteri di rete. Il computer client che non invia la notifica entro il periodo di timeout della sessione di quarantena viene disconnesso dal server di accesso remoto.
  
I vantaggi di una configurazione di questo tipo consistono nella possibilità di evitare l'impostazione dei filtri di pacchetti di quarantena e nel superamento dei problemi di ritardo delle applicazioni. L'accesso remoto avviene come se non vi fosse alcuna quarantena. Gli svantaggi di questa configurazione sono rappresentati dalla concessione di un accesso normale alla rete da parte del server di accesso remoto per il periodo di timeout della sessione di quarantena, anche se il client non è conforme ai criteri di protezione. Questa situazione è ovviamente una falla aperta nel sistema di protezione.
  
##### Utilizzare la notifica immediata
  
In questa configurazione lo script di quarantena avvia l'eseguibile RQC.exe per inviare la notifica prima del completamento dei test. Sul server di accesso remoto vengono rimosse le limitazioni della quarantena dalla connessione, mentre il client di accesso remoto ottiene un accesso normale immediato. All'interno dello script di quarantena, vengono intanto eseguiti i test di conformità ai criteri della rete. Se l'esito di uno di tali test è negativo, verrà inviata una notifica all'utente relativa alle azioni correttive da intraprendere e il client dell'utente verrà disconnesso automaticamente dopo un periodo di tempo specifico, emulando la modalità di quarantena e l'utilizzo di un timer della sessione di quarantena.
  
**Nota:** in questa configurazione è ancora necessario impostare l'attributo MS-Quarantine-Session-Timeout o MS-Quarantine-IPFilter per la definizione delle limitazioni di quarantena necessarie nel caso in cui sul computer sia disponibile solo un pacchetto o uno script di Connection Manager obsoleto.
  
Il vantaggio della notifica immediata è costituito dall'assenza di ritardi nelle applicazioni. L'accesso remoto avviene come se non vi fosse alcuna quarantena. Non è tuttavia consigliabile adottare questo approccio.
  
#### Procedure consigliate
  
In questa sezione vengono illustrate le procedure consigliate principali della soluzione di Woodgrove. Tali procedure consigliate comprendono:
  
-   Utilizzare un criterio di quarantena che preveda il blocco totale del traffico.
  
-   Supportare l'accesso tramite connessioni di accesso remoto.
  
-   Utilizzare le azioni pre-tunnel personalizzate per le verifiche di protezione obbligatorie.
  
-   Includere il software concesso in licenza nel pacchetto per il client.
  
##### Utilizzare un criterio di quarantena che preveda il blocco totale del traffico
  
Al momento della connessione, il server DHCP assegna al client un indirizzo IP. Il componente di notifica al client (RQC.exe) tenta di passare la chiave condivisa al componente listener del server (RQS.exe) sul server di accesso remoto. RQS resta in ascolto solo sull'indirizzo IP interno del server di accesso remoto, ossia sull'unico indirizzo IP a cui deve essere concesso di comunicare in base ai criteri di quarantena. Tutto l'altro traffico deve essere bloccato dal filtro IP fino a che la chiave condivisa di RQC non viene ricevuta da RQS e il server di accesso remoto non annulla la quarantena.
  
##### Supportare l'accesso tramite connessioni di accesso remoto
  
Quando gli utenti selezionano l'opzione di accesso Windows **Accesso con connessione remota**, i client VPN possono ricevere gli aggiornamenti di Criteri di gruppo in modo simile ai client della LAN. Grazie a questa impostazione è possibile unificare l'amministrazione dei client interni e remoti.
  
**Nota: **non è disponibile alcun metodo che consenta di applicare script di avvio e assegnazioni di software su una connessione di accesso remoto.
  
L'utilizzo di questa opzione consente agli utenti di ricevere notifiche sulla scadenza delle password e di aggiornare, quando necessario, gli account dei computer. Poiché le impostazioni di Criteri di gruppo vengono applicate ai client remoti dopo il processo di connessione, la prima azione di post-connessione in Connection Manager deve consistere nella rimozione della connessione VPN in quarantena. Un ritardo nella rimozione della quarantena può impedire l'aggiornamento dei Criteri di gruppo, la notifica della scadenza della password e l'aggiornamento dell'account del computer.
  
Se si disattiva l'impostazione **Rilevamento collegamento lento Criteri di gruppo** in almeno un oggetto di Criteri di gruppo che viene applicato a tutti i client, sarà possibile configurare le impostazioni di Criteri di gruppo in modo che vengano applicate allo stesso modo sia ai client VPN che ai client LAN. Prima di procedere all'implementazione, è necessario eseguire dei test all'interno dell'organizzazione per valutare in modo approfondito l'impatto di questa impostazione. È d'altra parte consigliabile implementare questa opzione solo se assolutamente necessario. Per ulteriori informazioni sulle impostazioni di Criteri di gruppo, vedere [Introduction to Group Policy in Windows Server 2003](http://www.microsoft.com/windowsserver2003/techinfo/overview/gpintro.mspx) all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/gpintro.mspx (informazioni in lingua inglese).
  
Per ulteriori informazioni su Rilevamento collegamento lento Criteri di gruppo, vedere [Specifying Group Policy for Slow Link Detection](http://technet.microsoft.com/en-us/library/cc781031.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/all/deployguide/en-us/dmebb\_gpu\_fvfu.asp (informazioni in lingua inglese).
  
##### Utilizzare le azioni pre-tunnel personalizzate per le verifiche di protezione obbligatorie
  
Per evitare ritardi nella modalità di quarantena, eseguire tutte le verifiche di protezione previste mediante le azioni personalizzate pre-tunnel. Se gli aggiornamenti vengono elaborati dal client di accesso remoto prima della connessione, l'interazione dell'utente risulterà più piacevole.
  
##### Includere il software concesso in licenza nel pacchetto per il client
  
È necessario verificare che il computer remoto disponga di tutto il software concesso in licenza necessario per portare a termine la connessione. Il software deve essere distribuito come parte del pacchetto di Connection Manager, in modo da ridurre richieste di supporto e problemi di configurazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Implementazione di monitoraggio e gestione
  
In una soluzione di connessione VPN in quarantena deve essere prevista l'assegnazione e il monitoraggio di allarmi e soglie appropriati per il controllo dell'operatività della soluzione. La soluzione deve consentire di controllare l'intera rete, una singola risorsa o un elenco di risorse in tempo reale. Il monitoraggio deve comprendere gli indicatori necessari all'organizzazione che si occupa del supporto tecnico operativo. Il mancato rispetto di questi requisiti impedisce al reparto che si occupa della protezione del sistema di determinare se la soluzione è in grado di proteggere le connessioni di accesso remoto.
  
#### Controllo delle operazioni di quarantena
  
Nella sezione che segue sono riportate altre considerazioni sul monitoraggio delle operazioni di connessione VPN in quarantena. Ad esempio:
  
-   È importante stabilire una stretta collaborazione tra più team distribuiti su diversi fusi orari per la risoluzione dei problemi dei client remoti in organizzazioni molto estese. Test rigorosi e un'implementazione adeguata dei progetti pilota contribuiscono a ridurre le richieste di risoluzione dei problemi.
  
-   È necessario comprendere gli scenari di accesso remoto e le minacce alla protezione dell'organizzazione e trovare un giusto compromesso. I dirigenti di più alto livello devono assegnare la priorità ai beni che richiedono la protezione maggiore e definire un giusto equilibrio tra costi e rischi.
  
-   È opportuno anticipare le difficoltà tecniche, come le routine di installazione e la distribuzione di CD. Considerare l'opportunità di adottare ulteriori strumenti di gestione aziendale all'interno del processo di pianificazione.
  
-   È fondamentale istituire procedure di monitoraggio e gestione dei possibili problemi di prestazioni, tenendo sempre in primo piano le aspettative degli utenti. Agli utenti remoti che, ad esempio, non si sono connessi di recente alla rete utilizzando l'accesso remoto può capitare di dover affrontare tempi di accesso prolungati se hanno attivato l'opzione di accesso Windows. Se è necessario applicare un Service Pack al client, l'accesso può durare alcune ore, a seconda della velocità di connessione del client. Problemi di questo tipo possono essere superati dal team IT di Woodgrove inviando dei messaggi di posta elettronica agli utenti e offrendo loro l'alternativa di ricevere un CD o utilizzare un sito per il download.
  
-   È opportuno aggiornare computer server e client alle tecnologie più recenti appena possibile all'interno della pianificazione del progetto. In tal modo si costituisce una piattaforma per la soluzione di base, eliminando alla radice la maggior parte delle variabili dei problemi che possono verificarsi durante la distribuzione della soluzione. La stabilità del servizio aumenta e il costo del supporto tecnico agli utenti si riduce grazie a questo sforzo.
  
-   È utile suddividere l'implementazione del progetto in un certo numero di fasi e prevedere un lasso di tempo ragionevole tra le diverse fasi quali l'adozione da parte degli utenti, la stabilizzazione di sistemi e processi di rete e l'ottimizzazione. La sovrapposizione di più fasi potrebbe influire negativamente sugli utenti del servizio. Allo stesso modo potrebbero aggravarsi i problemi di individuazione e isolamento dei problemi del servizio.
  
-   Ricordare che i computer di casa dei dipendenti sono di loro proprietà e non vengono gestiti dal reparto IT dell'azienda. Se un dipendente non desidera o non è in grado di installare l'hardware e il software necessari per supportare l'accesso remoto dal proprio computer, è possibile vagliare altre opzioni. Microsoft Outlook® Web Access, ad esempio, costituisce un'alternativa sicura, utilizzabile in tutto il mondo, che consente ai dipendenti di stabilire connessioni crittografate verso i propri dati personali (posta elettronica, contatti, attività e funzioni di calendario) e verso le cartelle pubbliche di Microsoft Exchange Server 2003.
  
#### Estensione della soluzione
  
L'adozione di una soluzione di connessione VPN in quarantena non impedisce a un malintenzionato di appropriarsi delle credenziali di un utente e di tentare di accedere alla rete. Per ridurre tali eventualità, è opportuno prendere in considerazione l'estensione della soluzione in modo da prevedere l'impiego di certificati digitali memorizzati su smart card.
  
L'utilizzo di meccanismi di autenticazione a due fattori, quale una smart card, per l'autenticazione delle connessioni di accesso remoto, consente di migliorare la protezione della rete e di concedere ad altri utenti la possibilità di lavorare da postazioni remote. Per implementare le autenticazioni con smart card è necessario adottare il protocollo EAP-TLS (Extensible Authentication Protocol - Transport Layer Security).
  
In Woodgrove National Bank esiste già un'infrastruttura a chiave pubblica PKI matura, quindi è possibile procedere a un'estensione della soluzione di accesso remoto che preveda l'utilizzo di smart card. Per ulteriori informazioni sulla pianificazione dell'autenticazione a due fattori, vedere [Guida alla pianificazione dell'accesso protetto mediante smart card](http://technet.microsoft.com/it-it/library/cc170941) all'indirizzo http://www.microsoft.com/italy/technet/security/topics/networksecurity/securesmartcards/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Le nuove funzionalità di Windows Server 2003 con SP1 consentono alle organizzazioni di implementare soluzioni di connessione VPN in quarantena in modo affidabile e completamente supportato. La pianificazione corretta della distribuzione di una soluzione di connessione VPN in quarantena è essenziale per prevenire interruzioni non necessarie del servizio offerto agli utenti remoti. In questa guida sono stati esaminati i fattori e i processi che intervengono nella pianificazione di un'implementazione di connessione VPN in quarantena ed è stata descritta la soluzione adottata da Woodgrove National Bank per la propria rete. Per ulteriori informazioni sull'implementazione di soluzioni di connessione VPN in quarantena, vedere l'appendice C "Collegamenti correlati" in questo documento.
  
##### Download
  
[![](images/Dd536299.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft](http://go.microsoft.com/fwlink/?linkid=41308)
  
[](#mainsection)[Inizio pagina](#mainsection)
