---
TOCTitle: Testing della soluzione per reti LAN senza fili protette
Title: Testing della soluzione per reti LAN senza fili protette
ms:assetid: 'd4bd1089-c115-418e-ad32-3a12e5386d4b'
ms:contentKeyID: 20200835
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536236(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 7: Testing della soluzione per reti LAN senza fili protette

Aggiornato: 2 aprile 2004

##### In questa pagina

[](#eeaa)[Introduzione](#eeaa)
[](#edaa)[Procedura Microsoft per il testing della soluzione](#edaa)
[](#ecaa)[Verifica dell'implementazione](#ecaa)
[](#ebaa)[Strumenti di test](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

L'obiettivo primario del presente capitolo è quello di fornire ulteriori informazioni relative al testing della distribuzione della soluzione *Protezione delle reti LAN senza fili con PEAP e password.* I consigli forniti nel presente capitolo sono basati sulle informazioni acquisite da Microsoft® durante il testing della soluzione.

Nella prima parte del capitolo viene descritta la procedura di testing utilizzata da Microsoft. Nella seconda parte vengono indicati gli scenari di testing che è possibile utilizzare per verificare la soluzione prima di eseguirla nell'ambiente di produzione. Gli scenari di testing riportati nel capitolo integrano le procedure di verifica incluse nei capitoli da 3 a 6.

#### Prima di iniziare

Le informazioni operative relative alle aree seguenti possono risultare utili per il testing della soluzione:

-   Servizi di certificati Microsoft e concetti relativi all'infrastruttura PKI

-   Server IAS (Internet Authentication Service, Servizio di Autenticazione Internet) (server RADIUS).

-   Installazione dei driver della scheda di rete senza fili e configurazione delle impostazioni di rete senza fili in Microsoft Windows® XP.

-   Utilizzo e configurazione di Pocket PC 2003.

-   Servizio di directory Microsoft Active Directory® (inclusi la struttura di Active Directory e gli strumenti di gestione, l'utilizzo degli utenti, dei gruppi e di altri oggetti di Active Directory nonché i criteri di gruppo).

-   Microsoft Windows® Scripting Host e Microsoft Visual Basic® Scripting Edition (VBScript) (questi linguaggi saranno utili per la personalizzazione o l'utilizzo di script e strumenti forniti con la guida).

[](#mainsection)[Inizio pagina](#mainsection)

### Procedura Microsoft per il testing della soluzione

Il team di testing Microsoft ha rivolto particolare attenzione alla verifica del profilo della soluzione descritto nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili". Di seguito sono riportate le caratteristiche principali del profilo:

-   Insieme di strutture Active Directory a dominio singolo contenenti due controller di dominio con il livello funzionale del dominio nella modalità nativa di Windows 2000.

-   Server controller di dominio installati su Windows Server™ 2003, Standard Edition.

-   Windows XP Service Pack 1 Professional e Tablet Edition e Pocket PC 2003 (Hewlett Packard IPAQ 5550) utilizzati come client senza fili.

-   Server IAS installato nei controller di dominio.

-   Server CA (Certification Authority, Autorità di certificazione) installato in uno dei controller di dominio.

-   Sito della sede principale basato su una singola LAN e sito della filiale basato su una LAN separata.

-   Protezione dati della rete WLAN basata su WEP dinamico anziché su WPA.

-   Presenza di punti di accesso senza fili solo nella sede della filiale in quanto infrastruttura e latenza sono stati introdotti nella connessione per la sede principale in modo da simulare un tipo di connessione modem via cavo o DSL.

Questo profilo non comprende tutte le configurazioni possibili della soluzione (ad esempio l'adattamento a organizzazioni di dimensioni più estese), tuttavia ha garantito il testing di tutti i componenti delle configurazioni. Le modifiche all'architettura richieste per adattare questo profilo a quello di un'organizzazione con 5000 utenti sono relativamente inferiori.

**Nota:** il testing descritto di seguito include solo la verifica della soluzione eseguita da Microsoft e comprende il testing completo del prodotto eseguito dal team di sviluppo Microsoft, mentre il testing della soluzione viene considerato a parte.

#### Test del layout della rete

L'ambiente di laboratorio per i test si è basato sulla progettazione della rete descritta nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili". Nella figura sottostante viene indicato il layout fisico dell'istanza di laboratorio che presenta la configurazione di rete più semplice descritta nel capitolo 2.

[![](images/Dd536236.PEAP_701(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536236.peap_701_big(it-it,technet.10).gif)

**Figura 7.1 Architettura di rete del laboratorio**

Per la sede principale è stata prevista una singola rete con server di dominio e client senza fili su una singola subnet. Il sito della filiale disponeva di una rete separata e si trovava su una subnet diversa. Il router richiesto per il collegamento della sede principale alla filiale includeva limitazione della larghezza di banda e latenza WAN simulate. I punti di accesso senza fili presentavano una distanza tale da consentire agli utenti di muoversi liberamente.

Benché per il testing sia stata utilizzata una LAN singola non segmentata, è consigliabile separare la rete interna mediante l'utilizzo di subnet differenti, LAN virtuali (VLAN) e switch in modo da migliorare la gestione della protezione e delle prestazioni della rete.

Dopo aver sviluppato la rete di base costituita da controller di dominio, sistema DNS, protocollo DHCP, file, stampa e servizi Web con WEP senza fili statico, per l'installazione e la configurazione dei componenti sono state utilizzate le procedure di implementazione descritte nei capitoli da 3 a 6. In questi capitoli sono incluse le procedure di verifica che sono state eseguite così come descritte. Un gran numero di test è stato eseguito prima, durante e dopo la creazione. Gli scenari più importanti utilizzati per i test sono riportati nella sezione successiva e possono essere impiegati per verificare l'implementazione della soluzione.

La soluzione creata, gli script di generazione e gestione e la documentazione sono stati sottoposti a tre serie di testing e i problemi rilevati sono stati evidenziati come bug. Il testing è stato considerato valido e completo solo quando tutti i bug sono stati risolti.

[](#mainsection)[Inizio pagina](#mainsection)

### Verifica dell'implementazione

Nella presente sezione vengono descritti gli scenari di testing principali utilizzati da Microsoft per eseguire il testing della soluzione.

Gli scenari di testing non sono esaustivi ed è possibile sviluppare scenari personalizzati in base ai requisiti dell'organizzazione. Alcuni scenari di verifica descritti nei capitoli precedenti sono stati ripetuti nel presente capitolo per maggiore completezza. Prima di utilizzare gli scenari di testing indicati, è consigliabile leggere i capitoli precedenti. Se il test per uno degli scenari non dovesse riuscire, vedere la sezione "Risoluzione dei problemi" del capitolo 8 "Gestione della soluzione per reti LAN senza fili protette" per individuare gli errori e cercare di risolverli.

#### Scenario 1: Verifica della distribuzione dei certificati server IAS

Questo scenario consente di verificare se nei server IAS creati e configurati viene ricevuto il certificato di autenticazione server registrato automaticamente dalla CA della rete.

**Procedura**

1.  Aprire una shell comandi utilizzando il collegamento MSS WLAN Tools.

2.  Eseguire il seguente comando per aprire la MMC **Certificati**:

    **ComputerCerts.msc**

3.  Nella struttura della console fare doppio clic su **Certificati (computer locale)**, quindi fare doppio clic su **Personale**. Fare clic su **Certificati**.

4.  Verrà visualizzato almeno un certificato con il nome del server IAS nella colonna **Rilasciato a** nonché il nome della CA nella colonna **Rilasciato da**. Scorrere l'elenco verso destra e verificare che il valore per il certificato nella colonna **Modello di certificato** sia **Computer**.

5.  Se il certificato richiesto non viene visualizzato nella MMC **Certificati**, selezionare **Certificati (computer locale)** dalla struttura della console nel riquadro sinistro, quindi scegliere **Tutte le attività** dal menu **Azione** e infine **Registra automaticamente certificati**. Aggiornare la visualizzazione della MMC **Certificati**.

#### Scenario 2: Verifica del certificato CA principale nel client senza fili Windows XP

Questo scenario consente di verificare se nell'archivio dell'Autorità di certificazione principale attendibile di un client Windows XP senza fili viene ricevuto il certificato CA principale della rete. Il certificato viene scaricato e aggiunto nell'archivio all'aggiornamento del criterio di gruppo.

**Procedura**

1.  Accedere al computer client come amministratore.

2.  Scegliere **Start, Esegui...**, quindi digitare **MMC.exe** e premere **INVIO**.

3.  Nella MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.

4.  Nella finestra **Aggiungi/Rimuovi snap-in...** scegliere il pulsante **Aggiungi...**. Selezionare **Certificati** dall'elenco degli snap-in disponibili.

5.  Selezionare **Account computer**, quindi scegliere **Avanti**.

6.  Scegliere **Fine**.

7.  Chiudere le finestre **Aggiungi snap-in autonomo** e **Aggiungi/Rimuovi snap-in...**.

8.  Nel riquadro a sinistra passare a Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati.

9.  Individuare il certificato della propria CA. (Verrà indicato sotto il nome assegnato alla CA durante l'installazione).

10. Se il certificato non viene visualizzato nell'elenco, eseguire il comando seguente dal prompt dei comandi:

    **Gpupdate /force**

11. Ritornare alla MMC **Certificati**. Fare clic con il pulsante destro del mouse sul nodo **Certificati (computer locale)**, quindi scegliere **Aggiorna** e infine controllare di nuovo il certificato CA.

#### Scenario 3: Verifica dell'autenticazione utente nella rete senza fili

Si tratta dello scenario di testing più importante. Consente di verificare se, al termine dell'installazione e della configurazione della soluzione, l'utente di una rete WLAN è in grado di completare l'autenticazione e la connessione alla rete.

**Procedura**

1.  Controllare che un utente del dominio sia membro del gruppo Utenti LAN senza fili o del gruppo Domain Users (che è membro del primo gruppo).

2.  Chiedere all'utente di accedere a un computer client non connesso alla rete cablata e in cui sia installata una scheda WLAN. L'utente deve immettere le credenziali di dominio all'accesso.

3.  Aprire il pannello **Connessioni di rete** dal **Pannello di controllo** e controllare lo stato di **Connessione rete senza fili**. Lo stato visualizzato per la connessione senza fili dovrebbe essere **Autenticazione riuscita**.

4.  Dal prompt dei comandi specificare il comando ping per verificare la connettività a un altro computer della rete.

5.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione dell'utente.

#### Scenario 4: Verifica dell'autenticazione di un computer nella rete senza fili

Questo scenario consente di verificare l'autenticazione di un computer nella rete quando l'utente non è connesso.

**Procedura**

1.  Verificare che l'account del computer sia membro del gruppo Computer LAN senza fili o del gruppo Computer del dominio (che è membro del primo gruppo).

2.  Riavviare il computer dopo aver verificato che sia installata una scheda WLAN e che non sia stata stabilita la connessione alla rete senza fili.

3.  Nella schermata di accesso non immettere le informazioni richieste e lasciare il computer inattivo per alcuni minuti.

4.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1 per il nome host del computer. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione del computer.

#### Scenario 5: Verifica dell'autenticazione di un Pocket PC nella rete senza fili

Questo scenario di testing consente di verificare se un utente è in grado di completare la connessione alla rete WLAN da una periferica Pocket PC.

**Procedura**

1.  Controllare che un utente del dominio sia membro del gruppo Utenti LAN senza fili o del gruppo Domain Users (che è membro del primo gruppo).

2.  Abilitare la connessione senza fili nel Pocket PC e configurare le impostazioni 802.1X sul Pocket PC seguendo le informazioni fornite nel capitolo 6, "Configurazione dei client delle reti LAN senza fili".

3.  Selezionare e tenere premuto il nome della rete indicato nell'elenco delle reti senza fili finché non vengono visualizzate le opzioni per la connessione. Scegliere **Connetti** per stabilire la connessione.

4.  Quando viene richiesto di immettere le credenziali di dominio nella schermata **Accesso alla rete**, specificare il nome, la password e il dominio dell'utente.

5.  Se l'autenticazione viene completata, nell'icona con lo stato della rete non verrà visualizzato alcun segno di croce. Per verificare lo stato, è sufficiente eseguire **Internet Explorer** dal menu **Start** e visualizzare un sito Web intranet.

6.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione dell'utente.

#### Scenario 6: Blocco dei client WLAN mediante l'utilizzo dei criteri di accesso remoto IAS

Questo scenario si basa sulle informazioni fornite nel capitolo 8, "Gestione della soluzione per reti LAN senza fili protette". Un amministratore, se necessario, è in grado di bloccare l'accesso senza fili alla rete mediante l'utilizzo di un criterio che nega l'accesso remoto (questa procedura viene descritta nei dettagli nella sezione "Impedire l'accesso alla rete LAN senza fili a un utente o a un computer" del capitolo 8). Prima di eseguire questo scenario di testing, è necessario configurare il criterio che nega l'accesso remoto sui server IAS.

**Procedura**

1.  Verificare che un account computer specifico sia membro del gruppo Rifiuta utenti LAN senza fili.

2.  Chiedere all'utente di accedere a un computer client non connesso alla rete cablata e in cui sia installata una scheda WLAN. L'utente deve immettere le credenziali di dominio all'accesso.

3.  L'accesso al dominio non sarà consentito e verrà visualizzato il messaggio di errore "Accesso negato".

4.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 2. Esaminare la descrizione del registro in quanto include le informazioni degli errori di autenticazione dell'utente.

#### Scenario 7: Accesso negato alla rete WLAN se l'utente non è membro di gruppi di accesso alla rete WLAN

Questo tipo di test consente di verificare se all'utente viene negato l'accesso senza fili alla rete se non è membro del gruppo Utenti senza fili. Si tratta di un metodo alternativo per bloccare l'accesso senza fili alla rete.

**Procedura**

1.  Aprire la console **Utenti e computer di Active Directory** dal pannello **Strumenti di amministrazione**.

2.  Rimuovere il gruppo Domain Users dal gruppo Utenti LAN senza fili oppure rimuovere un utente specifico se gli utenti vengono aggiunti direttamente al gruppo Utenti LAN senza fili.

3.  Chiedere all'utente di accedere a un computer client non connesso alla rete cablata e in cui sia installata una scheda WLAN. L'utente deve immettere le credenziali di dominio all'accesso.

4.  L'accesso alla rete non sarà consentito e verrà visualizzato il messaggio di errore "Accesso negato".

5.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 2. Esaminare la descrizione del registro in quanto include le informazioni degli errori di autenticazione dell'utente.

#### Scenario 8: Verifica del failover dei servizi IAS

Questo scenario di testing consente di verificare la disponibilità del servizio IAS nei client senza fili quando uno dei server IAS diventa indisponibile. Questi problemi non devono causare problemi alla connettività di rete nei client senza fili. Si tratta di uno scenario di testing importante che consente di verificare se i punti di accesso vengono assegnati a server IAS secondari quando il server IAS primario diventa indisponibile.

**Procedura**

1.  Aprire la **MMC** IASnel server IAS primario della rete e selezionare il nome del server. Quindi arrestare il servizio IAS scegliendo il pulsante **Stop** sulla barra dei menu.

2.  Utilizzando un account utente di dominio con accesso autorizzato alla WLAN, accedere alla rete mediante una connessione senza fili.

3.  L'utente dovrebbe riuscire a completare l'autenticazione e la connessione alla rete. Per verificare, aprire il pannello **Connessioni di rete** dal **Pannello di controllo** e controllare lo stato di **Connessione rete senza fili**. Lo stato visualizzato per la connessione senza fili dovrebbe essere **Autenticazione riuscita**.

4.  Dal prompt dei comandi specificare il comando **ping** per verificare la connettività di rete a un altro computer della rete.

5.  Nel server IAS secondario aprire il **Visualizzatore eventi**.Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione dell'utente.

#### Scenario 9: Mobilità dei client senza fili tra i punti di accesso e riautenticazione nella rete WLAN

Questo scenario consente di verificare la mobilità dei client senza fili tra i punti di accesso e la relativa riautenticazione (o riconnessione rapida, se abilitata). È importante che questo scenario sia testato prima della distribuzione della soluzione nell'ambiente di produzione. Il test consente di verificare l'affidabilità della connettività di rete senza fili.

**Procedura**

1.  Utilizzando un account utente di dominio con accesso autorizzato alla WLAN, accedere alla rete mediante una connessione senza fili. Controllare che la connessione di rete sia stata stabilita.

2.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione dell'utente.

3.  Tra le informazioni di autenticazione dell'utente annotare l'indirizzo IP del punto di accesso a cui l'utente è connesso. Il valore viene visualizzato nel campo **Indirizzo IP client**.

4.  Eseguire il roaming con il computer in un'altra posizione in modo che il client si trovi in prossimità di un punto di accesso adiacente e lontano dal punto di accesso a cui era connesso.

5.  Verrà eseguita la riautenticazione e la connessione del client Windows XP al nuovo punto di accesso.

6.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di riautenticazione dell'utente e il campo **Indirizzo IP client** in cui è indicato l'indirizzo IP del nuovo punto di accesso.

#### Scenario 10: Riautenticazione del client senza fili a causa del timeout di una sessione di IAS

Questo scenario consente di verificare la rotazione delle chiavi WEP dinamiche configurata nel criterio di richiesta di connessione IAS. Il test verifica se i client vengono riautenticati periodicamente (dopo il periodo di tempo configurato) in modo che le rispettive chiavi WEP vengano sostituite.

**Procedura**

1.  Utilizzando un account utente di dominio con accesso autorizzato alla WLAN, accedere alla rete mediante una connessione senza fili. Controllare che la connessione di rete sia stata stabilita.

2.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi del **sistema** dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di autenticazione dell'utente.

3.  Lasciare il client connesso alla rete per più di un'ora. Per confermare che la connessione è attiva, è possibile avviare una richiesta ICMP continua a un altro computer della rete.

4.  Dopo un'ora circa, aprire il **Visualizzatore eventi** e controllare il registro degli eventi di sistema. Il registro degli eventi di sistema dovrebbe contenere una voce di registro IAS (tipo di informazione) con ID evento 1. Esaminare la descrizione del registro in quanto include le informazioni di riautenticazione dell'utente.

#### Scenario 11: Avvisi di posta elettronica per errori di backup di IAS

Questo tipo di test consente di verificare la corretta configurazione degli avvisi di posta elettronica per i server IAS come indicato nella soluzione. Quando vengono implementati in modo corretto, gli avvisi migliorano in modo significativo la gestione del servizio IAS che rappresenta un punto critico per la connettività delle reti senza fili. In teoria, il test dovrebbe essere eseguito dopo l'implementazione per verificare se l'esecuzione dei servizi di notifica procede in modo corretto.

Per il test di questo scenario viene simulato un errore di backup di IAS per generare gli avvisi di posta elettronica richiesti. Le istruzioni per la configurazione del backup di IAS richieste in questo scenario sono fornite nel capitolo 8, "Gestione della soluzione per reti LAN senza fili protette". Prima di eseguire questo tipo di test, è consigliabile consultare il capitolo 8 e configurare gli script necessari.

**Procedura**

1.  Aprire una shell comandi utilizzando il collegamento MSS WLAN Tools.

2.  Modificare il file **Constants.vbs** e impostare il parametro **ALERT\_EMAIL\_ENABLED** su **True**.

3.  Configurare il parametro **ALERT\_EMAIL\_RECIPIENTS** con gli indirizzi di posta elettronica delle persone che devono essere avvisate.

4.  Configurare il parametro **ALERT\_EMAIL\_SMTP** con l'indirizzo IP o il nome DNS del server SMTP.

5.  Eseguire il seguente comando di backup di IAS per alcune cartelle non esistenti:

    **MSSTools BackupIAS /path:***C:\\PercorsoIASNoncorretto.*

6.  Nel server IAS aprire il **Visualizzatore eventi**. Il registro eventi dell'applicazione dovrebbe contenere le operazioni di IAS (tipo di errore) con ID evento 211.

7.  Le persone identificate riceveranno un avviso di posta elettronica.

#### Scenario 12: Avvisi di posta elettronica per errori del servizio CA

Questo tipo di test è simile a quello relativo agli errori di backup di IAS. Consente di verificare se gli avvisi di posta elettronica vengono inviati ai responsabili dell'amministrazione in caso di errore del servizio CA.

Le istruzioni per la configurazione del backup della CA richieste in questo scenario sono fornite nel capitolo 8, "Gestione della soluzione per reti LAN senza fili protette". Prima di eseguire questo tipo di test, è consigliabile consultare il capitolo 8 e configurare gli script necessari.

**Procedura**

1.  Aprire una shell comandi utilizzando il collegamento MSS WLAN Tools.

2.  Modificare il file **Constants.vbs** e impostare il parametro **ALERT\_EMAIL\_ENABLED** su **True**.

3.  Configurare il parametro **ALERT\_EMAIL\_RECIPIENTS** con gli indirizzi di posta elettronica delle persone che devono essere avvisate.

4.  Configurare il parametro **ALERT\_EMAIL\_SMTP** con l'indirizzo IP o il nome DNS del server SMTP.

5.  Aprire **Autorità di certificazione** dal pannello **Strumenti di amministrazione**. Selezionare il nome della CA, quindi scegliere **Azione**, **Tutte le attività** e infine **Arresta servizio**.

6.  Aprire la MMC **Servizi** dal pannello **Strumenti di amministrazione**.

7.  Fare clic con il pulsante destro del mouse su **Servizi certificati** e scegliere **Proprietà**. Passare il tipo di **Avvio** su **Disabilita** e scegliere **OK** per chiudere.

8.  Eseguire il seguente comando CA:

    **MSSTools CheckCA**

9.  Nel server CA aprire il **Visualizzatore eventi**.Il registro eventi dell'applicazione dovrebbe contenere le operazioni della CA (tipo di errore) con ID evento 1.

10. Le persone identificate riceveranno un avviso di posta elettronica a ogni errore del servizio CA.

11. Ripristinare il tipo di **AvvioServizi certificati** su **Automatico** nella MMC **Servizi**.

12. Avviare il servizio nella MMC **Autorità di certificazione** facendo clic sul pulsante **Start** nella barra dei menu.

[](#mainsection)[Inizio pagina](#mainsection)

### Strumenti di test

Durante il testing della soluzione sono stati utilizzati gli strumenti riportati di seguito. Alcuni di questi strumenti vengono usati anche durante le fasi di creazione e gestione:

1.  **Certutil:** strumento multifunzione utilizzato per la configurazione della CA, il dump e la visualizzazione delle informazioni di configurazione della CA, il backup e il ripristino dei componenti della CA nonché per la verifica di certificati, coppie di chiavi e catene di certificati.

2.  **Dcdiag:** strumento che consente di analizzare lo stato dei controller di dominio in un insieme di strutture o in un'organizzazione.

3.  **Event Log Viewer:** strumento che consente di controllare e acquisire i registri relativi all'applicazione, alla protezione e al sistema.

4.  **Group Policy Management Console:** strumento utilizzato per visualizzare e modificare gli oggetti Criteri di gruppo in Active Directory.

5.  **NetMon:** utilità che acquisisce e filtra i frame del traffico di rete in ingresso e in uscita dal computer in cui è installata. Questo strumento non è richiesto direttamente ma è utile per il debug dei problemi di autenticazione. Per eseguirne l'installazione dal **Pannello di controllo**, è sufficiente selezionare **Installazione applicazioni**, quindi **Componenti di Windows**, **Strumenti di gestione e controllo** e infine **Strumenti per il monitoraggio della rete**.

6.  **Netsh:** utilità di script della riga di comando che consente di visualizzare o modificare, sia in locale che in remoto, la configurazione di rete dei computer in esecuzione. Si tratta di uno strumento multifunzione utilizzato per le operazioni correlate a IAS.

7.  **Windows Backup:** strumento di backup e ripristino fornito con Windows che consente di eseguire operazioni di backup e ripristino su file, cartelle e stato del sistema. Può essere eseguito tramite procedura guidata o dalla riga di comando.

8.  **PerfMon:** strumento che consente di visualizzare registri, avvisi e contatori relativi alle prestazioni del sistema. Può essere utilizzato per il monitoraggio delle prestazioni di IAS.

9.  **Ping:** strumento che consente di verificare la connettività a livello IP in un altro computer TCP/IP mediante l'invio di messaggi di richiesta echo ICMP. I messaggi di replica echo ricevuti vengono visualizzati insieme ai tempi di andata e ritorno.

10. **Schtasks:** strumento utilizzato per pianificare l'esecuzione di comandi e programmi periodicamente o in base a un orario specifico. Consente di aggiungere e rimuovere le attività dalla pianificazione, avviare e arrestare le attività su richiesta nonché visualizzare e modificare le attività pianificate.

La maggior parte di questi strumenti viene installata automaticamente insieme al sistema operativo Windows. L'installazione degli altri strumenti viene descritta nel capitolo 3, "Predisposizione dell'ambiente".

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Nel presente capitolo viene descritto il testing della soluzione di rete WLAN protetta. Nella prima parte è inclusa una breve descrizione dei parametri utilizzati da Microsoft durante il testing della soluzione nella fase di sviluppo. Nella seconda parte vengono fornite le istruzioni relative all'esecuzione degli scenari di testing più importanti utilizzati per eseguire il test della soluzione. Questi scenari di testing consentono di verificare il corretto funzionamento dell'infrastruttura di protezione della rete WLAN prima che ne venga eseguita la distribuzione nell'ambiente di produzione.

**Scarica la soluzione completa**

[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)

[](#mainsection)[Inizio pagina](#mainsection)
