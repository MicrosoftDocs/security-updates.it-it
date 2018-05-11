---
TOCTitle: 'Capitolo 7: Servizi di sistema'
Title: 'Capitolo 7: Servizi di sistema'
ms:assetid: '1b142203-e909-4f8c-a554-e634bc67fadd'
ms:contentKeyID: 20200878
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536279(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 7: Servizi di sistema

I servizi di sistema sono descritti in maniera diversa dalle altre impostazioni descritte in questa guida, in quanto la vulnerabilità, le contromisure e il potenziale impatto sono pressoché identici per tutti i servizi.

Quando si installa Microsoft Windows Server 2003 o Microsoft Windows XP per la prima volta, alcuni servizi sono installati e configurati per essere eseguiti, come impostazione predefinita all'avvio del computer. È presente un numero minore di servizi predefiniti rispetto a Windows 2000 Server e, per quanto riguarda Windows Server 2003, i servizi specifici varieranno in base al ruolo assegnato a ciascun server. Nell'ambiente potrebbero non essere essenziali tutti i servizi predefiniti e per migliorare la protezione, è consigliabille disattivare quelli non necessari.

Il presente capitolo faciliterà l'identificazione della funzione e dello scopo di ciascun servizio e descriverà i servizi rimasti attivati in Windows Server 2003 e Windows XP al fine di garantire la compatibilità dell'applicazione e del client o di semplificare la gestione del sistema del computer. La cartella di lavoro Microsoft Excel "Windows Default Security and Services Configuration" (contenuta nella versione scaricabile della presente guida) descrive le impostazioni predefinite dei servizi di sistema.

##### In questa pagina

[](#edaa)[Panoramica dei servizi](#edaa)  
[](#ecaa)[Non impostare le autorizzazioni sugli Oggetti servizio](#ecaa)  
[](#ebaa)[Descrizione dei servizi di sistema](#ebaa)  
[](#eaaa)[Ulteriori informazioni](#eaaa)  

### Panoramica dei servizi

Per poter accedere alle risorse e agli oggetti del sistema operativo, un servizio deve avere accesso, e la maggior parte dei servizi non è progettata in modo da poter modificare l’account di accesso predefinito. Se l'account predefinito viene modificato, è probabile che il servizio non venga eseguito correttamente. Se si seleziona un account che non dispone dell’autorizzazione ad accedere come servizio, lo snap-in Servizi di Microsoft Management Console (MMC) gli concede automaticamente la possibilità di accedere come servizio per il computer. Tuttavia, questa configurazione automatica non garantisce che il servizio si avvii. In Windows Server 2003 sono inclusi tre account locali predefiniti, utilizzati come account di accesso per vari servizi di sistema:

-   **Account di sistema locale** l’account di sistema locale è un account potente, che dispone dell’accesso completo al computer e agisce in qualità del computer nella rete. Se un servizio accede all’account di sistema locale in un controller di dominio, avrà accesso all’intero dominio. Alcuni servizi sono configurati per impostazione predefinita per utilizzare l'account di sistema locale e non deve essere modificata. L'account di sistema locale non ha una password accessibile all'utente.

-   **Account del servizio locale**. I Servizio locale è un account predefinito speciale, simile a un account utente autenticato. Esso ha lo stesso livello di accesso per le risorse e gli oggetti come i membri del gruppo **Users**. L’accesso limitato contribuisce a salvaguardare il computer nel caso vengano compromessi singoli servizi o processi. I servizi che utilizzano l’account Servizio locale accedono alle risorse di rete come sessione Null con credenziali anonime. Il nome di questo account è T AUTHORITY\\Local Service, e non ha una password accessibile all'utente.

-   **Account del servizio di rete**. Il Servizio di rete è anche un account predefinito speciale, simile a un account utente autenticato. Come l'account del servizio locale, ha lo stesso livello di accesso per le risorse e gli oggetti come membri del gruppo **Users**, che facilita la protezione del computer. I servizi che usano l’account Servizio di rete accedono alle risorse di rete utilizzando le credenziali dell’account del computer. Il nome di questo account è NT AUTHORITY\\Network Service, e non ha una password accessibile all'utente.

**Importante**: modificando le impostazioni predefinite del servizio è possibile che servizi importanti smettano di funzionare correttamente. È necessario prestare molta attenzione quando si modificano le impostazioni relative al **tipo di avvio** e all’**accesso** di servizi configurati in modo da avviarsi automaticamente.

È possibile configurare le impostazioni dei servizi di sistema nella seguente posizione nell'Editor criteri di gruppo:

**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Servizi sistema\\**

#### Vulnerabilità

Qualsiasi servizio o applicazione è un potenziale punto di attacco. Disattivare o rimuovere quindi i servizi o file eseguibili non necessari nell’ambiente di sistema. Con Windows Server 2003 sono inoltre disponibili servizi opzionali aggiuntivi, ad esempio Servizi certificati, che nell'installazione predefinita del sistema operativo non vengono installati.

È possibile aggiungere questi servizi opzionali a un computer esistente con Installazione applicazioni nel Pannello di controllo, oppure con la Configurazione guidata server di Windows Server 2003. È inoltre possibile creare un'installazione automatica personalizzata di Windows Server 2003. Nei Criteri di base dei server membro (MSBP, Member Server Baseline Policy) descritti nella [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140) (disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845), questi servizi opzionali e tutti i servizi sono disabilitati.

**Importante**: se si attivano nuovi servizi, è necessario valutare eventuali dipendenze da altri servizi. Aggiungere tutti i servizi necessari per un ruolo di server specifico nei criteri relativi al ruolo svolto dal server nell’organizzazione.

#### Contromisura

Disabilitare tutti i servizi non necessari.

Per ciascun servizio di sistema, è possibile assegnare tramite i Criteri di gruppo uno stato di servizio. I possibili valori per queste impostazioni dei criteri di gruppo sono:

-   Automatica

-   Manuale

-   Disabilitato

-   Non definito

Un altro modo di gestire la protezione del servizio è quello di configurare un elenco di controllo di accesso (ACL) per ciascun servizio con un elenco di account definito dall'utente. Questo metodo offre un modo per controllare l'avvio del servizio e per accedere al servizio in esecuzione.  

#### Impatto potenziale

Se alcuni servizi (ad esempio la Gestione account di protezione) sono disattivati, non sarà possibile riavviare il computer. Se gli altri servizi critici sono disattivati, il computer potrebbe non riuscire ad autenticarsi presso i controller di dominio. Per disattivare alcuni servizi di sistema, prima di modificarli in un ambiente di produzione, è necessario verificare le impostazioni modificate sui computer di prova.

[](#mainsection)[Inizio pagina](#mainsection)

### Non impostare le autorizzazioni sugli Oggetti servizio

È possibile utilizzare strumenti basati sull'interfaccia utente grafica (GUI) per modificare i servizi. Tuttavia, le versioni di questi strumenti, incluse nelle versioni precedenti del sistema operativo di Windows (in particolare di Windows Server 2003), applicano automaticamente le autorizzazioni a ogni servizio quando se ne configurano le proprietà. Strumenti quali l'Editore dell'oggetto Criteri di gruppo e lo snap-in Modelli di protezione di MMC per applicare tali autorizzazioni utilizzano il DLL dell'Editor di configurazione della protezione.

Ad esempio, quando si utilizza lo snap-in Modelli di protezione di MMC per configurare lo stato di avvio di un servizio in Windows XP, sarà visualizzata la seguente finestra di dialogo:

[![](images/Dd536279.tcfg0701(it-it,TechNet.10).gif "Figura 7.1 Finestra di dialogo della protezione dei servizi")](https://technet.microsoft.com/it-it/dd536279.tcfg0701_big(it-it,technet.10).gif)

**Figura 7.1 Finestra di dialogo della protezione dei servizi**

A prescindere che si selezioni **OK** o **Annulla**, le autorizzazioni saranno applicate al servizio configurato. Sfortunatamente, le autorizzazioni proposte da questa finestra di dialogo non corrispondono alle autorizzazioni predefinite della maggior parte dei servizi inclusi in Windows. Di conseguenza, le autorizzazioni causeranno una serie di problemi per molti servizi. Microsoft consiglia di non modificare le autorizzazioni sui servizi inclusi in Windows XP o Windows Server 2003, perché le autorizzazioni predefinite sono già abbastanza restrittive.

Questa funzionalità è stata rettificata in Windows Server 2003 e la nuova versione del DLL di Editor di configurazione della protezione non obbliga a configurare le autorizzazioni quando le proprietà di un servizio vengono modificate. Esistono molti modi diversi di affrontare questa difficile situazione:

-   Utilizzare la Configurazione guidata impostazioni di sicurezza, un componente opzionale di Windows incluso in Windows Server 2003 Service Pack 1 (SP1). Microsoft consiglia questo approccio quando è necessario configurare i filtri porta dei servizi e della rete per vari ruoli server di Windows Server 2003.

-   Utilizzare lo Snap-in Modelli di protezione MMC e l'Editor oggetti Criteri di gruppo su un server dotato di Windows Server 2003 con SP1. Microsoft consiglia questo approccio quando è necessario configurare i servizi per i modelli di protezione o i criteri di gruppo che saranno applicati a Windows XP.

-   Utilizzare un editor di testo come il Blocco note per modificare i modelli di protezione o i criteri di gruppo su un computer dotato di Windows XP Professional. Questo metodo è il meno auspicabile, ma alcuni clienti non possono fare altrimenti. Istruzioni dettagliate sono fornite nella sezione seguente.

#### Modifica manuale dei modelli di protezione

Anche se è possibile utilizzare un editor di testo come il Blocco note per modificare i modelli di protezione, si tratta di file complessi. I modelli di protezione creati con una specifica relativa al modello definita in modo errato possono rendere impossibile l'avvio del computer. Sebbene la maggior parte degli errori non causa un problema così serio, è necessario essere pazienti e fare attenzione ai dettagli se è necessario modificare manualmente i modelli di protezione.

Quando si utilizza uno degli strumenti basati su GUI per configurare i servizi in un modello di protezione, le informazioni di configurazione vengono memorizzate nella sezione del file relativa alle impostazioni generali del servizio. Il seguente testo di esempio proviene da un modello di protezione in cui lo stato di avvio dei servizi Avvisi, Cartella Appunti e Browser di computer è stato configurato su **Disabilitato** e quello del servizio Client DHCP su **Automatico.**

```
	[Service General Setting]
	Alerter,4,"D:AR(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)
	(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)(A;;CCLCSWLOCRRC;;;IU)
	S:(AU;FA;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;WD)"
	ClipSrv,4,"D:AR(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)
	(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)(A;;CCLCSWLOCRRC;;;IU)
	S:(AU;FA;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;WD)"
	Browser,4,"D:AR(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)
	(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)(A;;CCLCSWLOCRRC;;;IU)
	S:(AU;FA;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;WD)"
	Dhcp,2,"D:AR(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)
	(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)(A;;CCLCSWLOCRRC;;;IU)
	S:(AU;FA;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;WD)"
```

Il formato di ciascuna voce contiene tre campi separati da virgole.

-   Il primo campo specifica il nome del servizio. Ad esempio, ClipSrv indica il servizio Cartella Appunti.

-   Il secondo campo definisce lo stato di avvio:

    -   4 indica Disabilitato

    -   3 indica Manuale

    -   2 indica Automatico

-   Il terzo campo definisce le autorizzazioni per l'oggetto del servizio in linguaggio SDDL (Security Descriptor Definition Language).

Non è necessario conoscere i dettagli del linguaggio SDDL per utilizzare la Configurazione guidata impostazioni di sicurezza. Ulteriori informazioni sul linguaggio SDDL sono disponibili nell'articolo "[Security Descriptor Definition Language](http://msdn.microsoft.com/en-us/library/aa379567.aspx)" (in inglese) su MSDN all'indirizzo http://msdn.microsoft.com/library/en-us/secauthz/
security/security\_descriptor\_definition\_language.asp.

Per risolvere i potenziali problemi relativi alle autorizzazioni sugli oggetti del servizio, rimuovere la stringa SDDL nel terzo campo, ma lasciare le virgolette doppie. L'esempio seguente mostra il testo corretto per i quattro servizi citati:

```
        [Service General Setting]
        Alerter,4,""
        ClipSrv,4,""
        Browser,4,""
        Dhcp,2,""
```
       
Una volta rimosse le informazioni SDDL da tutti i servizi nel modello di protezione, salvare il file. È quindi possibile applicare il modello di protezione seguendo uno dei metodi comunemente utilizzati. È estremamente importante verificare in modo esaustivo i modelli di protezione prima di applicarli ai computer di produzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Descrizione dei servizi di sistema

Le sottosezioni seguenti descrivono i servizi di Windows Server 2003 e di Windows XP in ordine alfabetico. Sono inclusi anche i servizi installati per impostazione predefinita e quelli che possono essere aggiunti al computer.

**Nota**: se un servizio non viene avviato, non sarà possibile avviare neanche quelli che dipendono da esso. Perciò, se si modifica lo stato di un servizio, è possibile influenzare anche altri servizi apparentemente non collegati ad esso. Tali dipendenze esistono per tutti i servizi descritti in questa sezione. Per controllare le dipendenze di un servizio, fare clic sulla scheda **Relazioni di dipendenza** nella finestra di dialogo delle proprietà del servizio nello snap-in Servizi MMC.

#### Avvisi

Il servizio **Avvisi** notifica avvisi amministrativi agli utenti e ai computer selezionati. È possibile utilizzare il servizio Avvisi per inviare messaggi di avviso agli utenti specificati connessi alla rete.

I messaggi di avviso avvertono gli utenti di problemi di protezione, accesso e sessione utente I messaggi di avviso vengono inviati da un server a un computer client, sul quale deve essere in esecuzione il servizio **Messenger** perché l'utente li riceva (il servizio **Messenger** è disattivato per impostazione predefinita in Windows XP e in Windows Server 2003, in modo che gli utenti malintenzionati non possano inviare false notifiche).

Se il servizio **Avvisi** viene disattivato, le applicazioni che utilizzano le API NetAlertRaise o NetAlertRaiseEx non saranno più in grado di notificare a utenti o computer, mediante una finestra di messaggio del servizio **Messenger**, che è stato generato un avviso amministrativo. Molti strumenti per la gestione dei gruppi di continuità utilizzano il servizio **Avvisi** per notificare all’amministratore gli eventi significativi. Se si desidera utilizzare questo servizio, configurare lo stato di avvio su **Automatico**, in modo che i componenti esterni possano utilizzarlo quando necessario.

#### Servizio di verifica compatibilità applicazioni

Il **Servizio di verifica compatibilità applicazioni** (AELookupSvc) fa parte di Application Compatibility Administrator. Questo servizio elabora le richieste di verifica della compatibilità delle applicazioni quando vengono avviate, fornisce supporto per i computer Windows Server 2003 su un dominio, genera un report sui problemi di compatibilità e applica automaticamente gli aggiornamenti del software ai programmi.

Il **Servizio di verifica compatibilità applicazioni** deve essere attivo perché vengano applicati gli aggiornamenti del software per la compatibilità delle applicazioni. Non è possibile personalizzare questo servizio, in quanto il sistema operativo lo utilizza internamente. Questo servizio non si serve di reti, di Internet o delle risorse di Active Directory.

Se si disattiva il **Servizio di verifica compatibilità applicazioni**, questo continuerà a essere in esecuzione, ma non gli verrà inviata alcuna richiesta. Il processo non può essere arrestato.

#### Servizio Gateway di livello applicazione

Il **Servizio Gateway di livello applicazione** è un sottocomponente del sottosistema di rete di Windows. Fornisce supporto per i plug-in che consentono ai protocolli di rete di attraversare il firewall e di operare alle spalle della condivisione della connessione Internet. I plug-in Gateway di livello applicazione possono aprire le porte e modificare i dati incorporati nei pacchetti, ad esempio le porte e gli indirizzi IP. Il protocollo FTP (File Transfer Protocol) è l'unico protocollo di rete con un plug-in incluso in Windows Server 2003, Standard Edition, e Windows Server 2003, Enterprise Edition.

Il plug-in ALG FTP è stato progettato per supportare sessioni FTP attive tramite il modulo NAT (Network Address Translation) integrato in Windows. Il plug-in ALG FTP svolge tale funzione reindirizzando tutto il traffico che passa attraverso NAT ed è destinato alla porta 21 a una porta di ascolto privata compresa nell'intervallo 3000-5000 sulla scheda Loopback. Successivamente, il plug-in ALG FTP esegue il monitoraggio e l'aggiornamento del traffico del canale di controllo FTP in modo che il plug-in FTP possa canalizzare il mapping delle porte attraverso NAT per i canali di dati FTP. Il plug-in FTP aggiornerà anche le porte nel flusso del canale di controllo FTP.

Se il **servizio Gateway di livello applicazione** viene arrestato, non sarà più disponibile la connettività di rete per questi protocolli, il che si ripercuote negativamente sulla rete. Ad esempio, se si disattiva questo servizio, non sarà possibile utilizzare le applicazioni di messaggistica istantanea Windows Messenger e MSN Messenger.

#### Gestione applicazione

Il servizio di sistema **Gestione applicazione** fornisce i servizi per l’installazione del software, vale a dire Assegna, Pubblica e Rimuovi. Elabora richieste per enumerare, installare e rimuovere le applicazioni implementate attraverso la rete di un'organizzazione. Quando si fa clic su **Aggiungi** in Installazione applicazioni del Pannello di controllo in un computer che appartiene a un dominio, viene richiamato questo servizio per recuperare l’elenco delle applicazioni distribuite. Il servizio viene richiamato anche quando si utilizza Installazione applicazioni per installare o rimuovere un'applicazione e nel caso un componente, quale la shell o COM, effettui una richiesta di installazione affinché un’applicazione gestisca un’estensione di file, classe COM (Component Object Model) o ProgID non presente nel computer. Il servizio viene avviato la prima volta che viene richiamato e dopo l’avvio non termina.

**Nota**: per ulteriori informazioni su COM, classi COM e ProgID, vedere il kit SDK (Software Development Kit) nella libreria MSDN sulla pagina [Windows Resource Kits - Web Resources](http://www.microsoft.com/windows/reskits/webresources/) all'indirizzo www.microsoft.com/windows/reskits/webresources.

Se il servizio **Gestione applicazione** viene arrestato o disattivato, gli utenti non potranno installare, rimuovere o enumerare le applicazioni implementate in Active Directory attraverso le tecnologie di gestione Microsoft IntelliMirror. Se questo servizio viene disabilitato, le informazioni relative alle applicazioni distribuite non saranno recuperate e non saranno visualizzate nella sezione **Aggiungi nuovi programmi** di Installazione applicazioni nel Pannello di controllo. Nella finestra di dialogo **Aggiungi programmi** **dalla rete dell'azienda** sarà visualizzato il messaggio riportato di seguito:

Nessun programma disponibile in rete.

Non è possibile arrestare questo servizio dopo che è stato avviato senza riavviare il computer. Se questo servizio non è necessario e non si desidera che venga avviato, è necessario disabilitarlo.

#### Servizio Stato di ASP.NET

Il servizio **Stato ASP.NET** assicura il supporto per gli stati di sessione out-of-process di ASP.NET. In ASP.NET il concetto degli stati di sessione esiste e si concretizza tramite un elenco di valori associati alla sessione client, accessibile dalle pagine ASP.NET attraverso l'impostazione **Session.** I dati di sessione possono essere memorizzati in tre modi: nel processo, nel database Microsoft SQL Server e nello stato della sessione out-of-process.

**Questo servizio archivia** i dati di sessione in modalità out-of-process. Il servizio comunica con ASP.NET mentre è in esecuzione su un server Web provvisto di socket. Se questo servizio viene arrestato o disattivato, non sarà elaborata alcuna richiesta out-of-process. Il codice eseguibile per questo servizio è installato per impostazione predefinita, ma il servizio stesso è disattivato finché non si imposta manualmente il tipo di avvio su Automatico o Manuale.

#### Aggiornamenti automatici

Il servizio **Aggiornamenti automatici** consente il download e l'installazione dei modelli di protezione per Windows e Office. Fornisce automaticamente gli aggiornamenti più recenti, i driver e i miglioramenti ai computer Windows. Non è più necessario ricercare manualmente informazioni e aggiornamenti sulla protezione, che vengono forniti direttamente dal sistema operativo. Il sistema operativo è in grado di riconoscere quando un utente è connesso a Internet e di utilizzare tale connessione per cercare gli aggiornamenti necessari resi disponibili dal servizio Windows Update. In base alle impostazioni di configurazione in uso, il servizio invierà un avviso agli utenti prima di un download o un'installazione o installerà gli aggiornamenti automaticamente.

È possibile disattivare la funzionalità Aggiornamenti automatici attraverso l'impostazione **Sistemi** nel Pannello di controllo. In alternativa, è possibile fare clic con il tasto destro del mouse su **Risorse del computer** e selezionare **Proprietà**.

È inoltre possibile utilizzare lo snap-in Editor oggetti Criteri di gruppo di MMC per configurare un server Intranet impostato con Windows Server Update Services per ospitare gli aggiornamenti provenienti dai siti Microsoft Update. L'impostazione consente di specificare un server della rete da utilizzare come servizio di aggiornamento interno. Il client Aggiornamenti automatici utilizzerà questo servizio per la ricerca di aggiornamenti validi per i computer della rete.

**Nota:** per ulteriori informazioni su Windows Server Update Services, vedere il sito Web [Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=21133) (in inglese) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=21133.

Se il servizio **Aggiornamenti automatici** viene arrestato o disattivato, gli aggiornamenti non verranno scaricati automaticamente sul computer. Sarà necessario cercare, scaricare e installare le correzioni e gli aggiornamenti necessari sul sito Web [Windows Update](http://windowsupdate.microsoft.com/) all'indirizzo http://update.microsoft.com.

#### Servizio trasferimento intelligente in background (BITS, Background Intelligent Transfer Service)

Il **Servizio trasferimento intelligente in background** è un meccanismo di trasferimento di file in background e un gestore di coda. Il servizio **BITS** viene utilizzato per trasferire i file in modo asincrono tra un client e un server HTTP. Per impostazione predefinita le richieste al servizio **BITS** vengono sottoposte e i file vengono trasferiti sfruttando la larghezza di banda della rete che resterebbe inutilizzata, così da non interferire sulle altre attività di rete, ad esempio l'esplorazione.

Il servizio **BITS** sospende il trasferimento in caso di perdita della connessione o disconnessione dell’utente. La connessione al servizio **BITS** è persistente. Il trasferimento delle informazioni continua mentre l’utente è disconnesso, fra una connessione alla rete e l’altra e un riavvio del computer e l’altro. Quando l’utente si riconnette il servizio **BITS** riprende il processo di trasferimento.

Per la gestione del trasferimento di file, **BITS** utilizza una coda. È possibile attribuire una priorità ai processi di trasferimento inclusi nella coda e specificare se i file debbano essere trasferiti in primo piano o in background. Il trasferimento in background è ottimizzato dal servizio **BITS**, che aumenta e diminuisce (o *limita*) la velocità di trasferimento in base alla larghezza di banda della rete disponibile. Se un’applicazione di rete inizia a utilizzare maggiore larghezza di banda, il servizio **BITS** riduce la velocità di trasferimento per salvaguardare l’interattività dell’utente.

Il servizio **BITS** offre un livello di priorità in primo piano e tre in background, utilizzabili per i processi di trasferimento. I processi con priorità più elevata hanno la precedenza rispetto a quelli con priorità minore. In caso di processi con lo stesso livello di priorità i tempi di trasferimento vengono condivisi e la pianificazione round robin impedisce ai processi più grandi di bloccare la coda di trasferimenti. Ai lavori con priorità minore non viene dedicato tempo finché tutti i processi con priorità maggiore sono stati completati o finché per essi si verificano errori.

**BITS** è impostato per essere avviato manualmente sia su Windows Server 2003 sia su Windows XP. Viene avviato su richiesta quando è stato inoltrato il primo processo. Una volta completati tutti i processi in sospeso, il servizio **BITS** si arresta.

Se **BITS** viene arrestato, le funzionalità come Aggiornamenti automatici non saranno in grado di scaricare programmi e altre informazioni. Questa funzione implica inoltre che il computer non potrà ricevere gli aggiornamenti automatici dai servizi SUS (Software Update Services) aziendali, nel caso in cui un servizio sia stato configurato mediante i criteri di gruppo. Disabilitando questo servizio, tutti i servizi che ne dipendono esplicitamente non saranno in grado di trasferire file, a meno che, come Internet Explorer, non dispongano di un meccanismo alternativo di trasferimento diretto.

#### Servizi certificati

**Servizi certificati** fa parte del nucleo del sistema operativo e consente a un’entità di fungere da autorità di certificazione ed emettere e gestire certificati digitali per applicazioni come Secure/Multipurpose Internet Mail Extensions (S/MIME), Secure Sockets Layer (SSL), Encrypting File System (EFS), IP Security (IPsec) e l'accesso con smart card. Windows Server 2003 supporta più livelli di una gerarchia CA e una rete di trust a certificazione incrociata, comprese le autorità di certificazione in linea e non in linea.

**Servizi certificati** non è installato per impostazione predefinita. Gli amministratori devono installarlo attraverso Installazione applicazioni nel Pannello di controllo. Se **Servizi certificati** viene arrestato o disattivato dopo l'installazione, le richieste di certificati non saranno accettate e gli elenchi di revoca certificati (CRL, Certificate Revocation List) e Delta CRL non verranno pubblicati. Se il servizio viene arrestato per un tempo sufficientemente lungo perché i CRL scadano, i certificati esistenti non saranno convalidati.

#### Servizio Client per NetWare

I server sui quali è installato il **Servizio Client per NetWare** forniscono l'accesso agli utenti connessi interattivamente a file e risorse di stampa sulle reti NetWare. Con il servizio **Client per Netware** è possibile accedere dal proprio computer a file e risorse di stampa in server Netware che eseguono Novell Directory Service (NDS) o la protezione del bindery (NetWare versioni 3.x o 4.x).

Il servizio **Client per NetWare** non supporta il protocollo IP e pertanto non può essere utilizzato per l’interoperabilità con NetWare 5.x in ambienti che supportano esclusivamente IP. Per poterlo utilizzare in questo contesto è necessario caricare il protocollo IPX (Internetwork Packet Exchange) nel server NetWare 5.x o utilizzare un redirector compatibile con NCP (Netware Core Protocol) che supporti IP nativo.

Se il **Servizio Client per NetWare** viene arrestato o disattivato, non sarà più possibile accedere ai file e alle risorse di stampa sulle reti NetWare, a meno che non si installi il client Novell per NetWare. Per impostazione predefinita, questo servizio non è installato o abilitato.

#### Cartella Appunti

Il servizio **Cartella Appunti** consente al Visualizzatore Cartella Appunti di creare e condividere pagine di dati che possono essere visualizzate da computer remoti. Questo servizio dipende da **Network Dynamic Data Exchange (NetDDE)** per la creazione delle condivisioni del file reale a cui gli altri computer possono connettersi, mentre l'applicazione e il servizio Cartella Appunti consentono di creare le pagine di dati da condividere.

Il servizio **Cartella Appunti** è installato per impostazione predefinita, ma il suo stato di avvio è configurato su **Disabilitato.** Quando questo servizio viene disattivato, il Visualizzatore Cartella Appunti non è più in grado di condividere informazioni con i computer remoti. È tuttavia possibile continuare a utilizzare clipbrd.exe per visualizzare gli Appunti locali in cui sono memorizzati i dati selezionati e copiati tramite **Copia** del menu **Modifica** o premendo CTRL+C.

#### Servizio cluster

Il **Servizio cluster** controlla le operazioni relative ai cluster di server e gestisce il database dei cluster. Un cluster è un insieme di computer indipendenti che collaborano di fornire il supporto relativo al bilanciamento del carico e al failover. Le applicazioni abilitate ai cluster, come Microsoft Exchange Server e Microsoft SQL Server, utilizzano il cluster per mettere a disposizione degli utenti un unico computer virtuale. Il Servizio cluster distribuisce i dati e le operazioni tra i nodi del cluster. In caso di problemi di un nodo, gli altri nodi si occupano di fornire i servizi e i dati che venivano forniti dal nodo in cui si sono verificati i problemi. Quando un nodo è stato aggiunto o riparato, il software del cluster esegue la migrazione di alcuni dati e delle operazioni di calcolo in tale nodo.

Nella piattaforma Windows sono disponibili due diversi tipi di soluzioni cluster che supportano diversi stili di applicazione: cluster di server e cluster di bilanciamento del carico di rete (NLB, Network Load Balancing). I cluster di server offrono un ambiente altamente disponibile per le applicazioni con esecuzione prolungata, quali database o file server, fornendo supporto di failover con una gestione del cluster strettamente integrata. I cluster NLB offrono un ambiente altamente affidabile e scalabile per altri tipi di applicazioni, quali i server Web di front-end, e bilanciano il carico costituito dalle richieste dei client su un insieme di server identici.

Il **Servizio cluster** fornisce il supporto per i cluster di server. È il componente software essenziale che controlla tutti gli aspetti del funzionamento del cluster e ne gestisce il database. Ciascun nodo di un cluster esegue una istanza del **Servizio cluster**.

In Windows Server 2003 sono supportati fino a otto server di cluster di nodo sia nella versione Enterprise Server sia in quella Datacenter Server di Windows. Un cluster può tuttavia essere costituito solo da nodi che eseguono una versione di Windows o l’altra, in quanto versioni diverse non possono operare all'interno di un singolo cluster.

I cluster di server possono essere configurati in tre modi diversi:

-   **Nodo singolo**: questi cluster di server possono essere configurati con o senza periferiche di archiviazione di cluster esterne. Per i cluster a nodo singolo, senza periferiche di archiviazione di cluster esterne, come periferica di archiviazione viene configurato il disco locale. Utilizzare le configurazioni a nodo singolo per sviluppare applicazioni abilitate ai cluster oppure in ambito di produzione per conferire alle applicazioni capacità di monitoraggio dell’integrità locale o di riavvio.

-   **Periferica quorum singola**. Questi cluster di server dispongono di uno o più nodi e sono configurati in modo che ogni nodo sia collegato a una o più periferiche di archiviazione di cluster. I dati di configurazione del cluster sono archiviati in un’unica periferica di archiviazione di cluster, detta disco quorum.

-   **Maggioranza dei nodi**: Questi cluster di server dispongono di uno o più nodi, i quali possono essere o non essere collegati a una o più periferiche di archiviazione di cluster. I dati di configurazione del cluster sono archiviati in vari dischi del cluster e il **Servizio cluster** garantisce la coerenza di tali dati sui diversi dischi.

Per impostazione predefinita, **questo servizio** non è installato o abilitato. Se il **Servizio cluster** viene disattivato dopo l'installazione, i cluster non saranno disponibili. Per ulteriori informazioni sulla configurazione della protezione dei cluster di Windows, consultare i relativi collegamenti nella sezione "Ulteriori informazioni" alla fine del presente capitolo.

#### COM+ Event System

Il servizio **COM+ Event System** fornisce la distribuzione automatica degli eventi ai componenti COM che hanno sottoscritto il servizio stesso. Gli eventi COM+ estendono il modello di programmazione COM+, offrendo il supporto per eventi o chiamate di metodi ad associazione tardiva tra l’autore o il sottoscrittore e il sistema di eventi. Il sistema di eventi provvede a informare della disponibilità di informazioni, evitando ripetuti polling del server.

I **Servizi eventi COM+** gestiscono gran parte della semantica degli eventi per l’autore e il sottoscrittore. L’autore offre di pubblicare i tipi di eventi e i sottoscrittori richiedono tipi di eventi ad autori specifici. Le sottoscrizioni vengono gestite al di fuori dell’autore e del sottoscrittore e recuperate quando necessario, il che semplifica il modello di programmazione per entrambi. Il sottoscrittore non deve necessariamente contenere la logica per costruire le sottoscrizioni. Costruire un sottoscrittore è tanto semplice quanto costruire un componente COM. Il ciclo di vita della sottoscrizione è separato da quello dell’autore o del sottoscrittore. È possibile costruire sottoscrizioni prima ancora di attivare il sottoscrittore o l’autore.

Questo servizio è installato per impostazione predefinita, ma non viene avviato finché un'applicazione non lo richiede. Quando i **Servizi eventi COM+** vengono arrestati, il servizio **Notifica eventi di sistema** viene chiuso e non potrà fornire le notifiche di accesso e disconnessione. Il servizio **Copia shadow del volume**, necessario per l'utilità di backup di Windows e per le applicazioni di backup che si affidano alle API dell'utilità stessa, richiede questo servizio.

#### Applicazione di sistema COM+

Il servizio di sistema **Applicazione di sistema COM+** gestisce la configurazione e le informazioni di analisi dei componenti basati su COM+. Se il servizio viene disattivato, la maggior parte dei componenti basati su COM+ non funzionerà in modo corretto. Il servizio **Copia shadow del volume**, necessario per l'utilità di backup di Windows e per le applicazioni di backup che si affidano alle API dell'utilità stessa, richiede questo servizio. Per impostazione predefinita, questo servizio è installato e abilitato.  

#### Browser di computer

Il servizio **Browser di computer** gestisce un elenco aggiornato dei computer in rete, che fornisce ai programmi che lo richiedono. Il servizio **Browser di computer** viene utilizzato dai computer basati su Windows per visualizzare risorse e domini di rete. I computer designati come browser gestiscono elenchi di ricerca che contengono tutte le risorse condivise utilizzate in rete. Per tutte le versioni precedenti delle applicazioni Windows, quali Risorse di rete, il comando NET VIEW e Gestione risorse/Esplora risorse, sono richieste capacità di esplorazione. Ad esempio, se si apre Risorse di rete su un computer dotato di Windows 95, un computer impostato come browser genera l'elenco dei domini e dei computer che vengono visualizzati.

Un computer può rivestire diversi ruoli in un ambiente di esplorazione. In alcune condizioni, ad esempio in caso di errori o arresto di un computer designato per uno specifico ruolo di browser, i browser o i potenziali browser potrebbero passare a un ruolo operativo differente.

Il servizio **Browser di computer** è attivato e avviato per impostazione predefinita. Se viene disattivato, l'elenco di ricerca non verrà aggiornato o gestito.

#### Servizi di crittografia

Il servizio di sistema **Servizi di crittografia** fornisce i servizi di gestione delle chiavi per il computer. In **Servizi di crittografia** sono compresi tre diversi servizi di gestione:

-   **Servizio Database catalogo**. Questo servizio aggiunge, rimuove ed esegue ricerche sui file di catalogo, che sono utilizzati per firmare tutti i file del sistema operativo. Protezione file di Windows, Firma driver e il programma di installazione utilizzano questo servizio per verificare i file firmati. Non è possibile arrestare questo servizio durante l’installazione. Se il servizio viene disattivato dopo l’installazione, verrà riavviato su richiesta.

-   **Servizio Archivio principale protetto**. Questo servizio aggiunge e rimuove i certificati delle autorità di certificazione principali attendibili. Il servizio visualizza una finestra di messaggio con il nome e l’identificazione personale del certificato. Se si seleziona **OK**, il certificato viene aggiunto o rimosso dall’elenco corrente di autorità principali attendibili. Solo gli account LocalSystem dispongono dell’accesso in scrittura all’elenco. se viene arrestata questa parte del servizio, l’utente corrente non sarà in grado di aggiungere o rimuovere certificati delle autorità di certificazione principali attendibili.

-   **Servizio Chiave**. Questo servizio consente agli amministratori di registrarsi per i certificati da parte dell’account del computer locale. Il servizio offre varie funzionalità necessarie per la registrazione: enumerazione delle autorità di certificazione disponibili, enumerazione dei modelli di computer disponibili, capacità di creare e inoltrare una richiesta di certificato nel contesto del computer locale, e così via. Solo gli amministratori possono registrarsi da parte dell’account del computer locale. Il servizio Chiave consente inoltre agli amministratori di installare remotamente nel computer file di scambio di informazioni personali (PFX, Personal Information Exchange). Se il servizio viene disattivato, la registrazione automatica non potrà inoltre acquisire automaticamente l’insieme predefinito di certificati del computer.

Il servizio **Servizi di crittografia** è attivato e avviato automaticamente per impostazione predefinita. Se il servizio viene interrotto, i servizi di gestione elencati nel paragrafo precedente non funzioneranno in modo corretto.

#### Utilità di avvio processo server DCOM

Nelle versioni precedenti di Windows, il servizio Remote Procedure Call (RPC) service (RPCSS) veniva eseguito come sistema locale. Per ridurre la superficie di attacco di Windows e per aumentare il livello di protezione, la funzionalità del servizio RPC è stata divisa in due servizi in Windows XP Service Pack 2 e Windows Server 2003 Service Pack 1.

Il servizio RPCSS conserva tutte le funzionalità originali che non richiedevano i privilegi del sistema locale e viene ora eseguito sotto l'account Servizi di rete. Il servizio **Utilità di avvio processo server DCOM** (DCOMLaunch) incorpora le funzioni del precedente servizio RPC che richiedeva i privilegi del sistema locale e viene eseguito sotto l'account Servizi di rete. Questo servizio è attivato e avviato per impostazione predefinita.

Se il servizio **Utilità di avvio processo server DCOM** viene disattivato, le richieste RPC e DCOM sul computer locale non funzioneranno correttamente. In particolare, non sarà possibile utilizzare il servizio Windows Firewall.

#### Client DHCP

Il servizio **Client DHCP** gestisce la configurazione di rete. Registra e aggiorna gli indirizzi IP e i nomi DNS per il computer. Non è necessario modificare manualmente le impostazioni IP per un computer client, come un computer portatile, che si connette da postazioni diverse sulla rete. Al computer client viene automaticamente fornito un nuovo indirizzo IP, a prescindere dalla sottorete alla quale si riconnette (se un server DHCP è accessibile dalle sottoreti). Non è necessario configurare manualmente le impostazioni per DNS o WINS. Il server DHCP può fornire queste impostazioni al client, purché questo sia stato configurato per il rilascio di queste informazioni. Per attivare l'opzione sul client, selezionare **Ottieni indirizzo server DNS automaticamente**. Gli indirizzi IP duplicati non causano conflitti.

Se il servizio **Client DHCP** viene disattivato, il computer non riceverà gli indirizzi IP dinamici e gli aggiornamenti DNS dinamici automatici non verranno più registrati nel server DNS.

#### Server DHCP

Il servizio di sistema **Server DHCP** assegna gli indirizzi IP e consente la configurazione avanzata di parametri di rete, ad esempio assegnando automaticamente indirizzi per i server DNS e WINS ai client DHCP. Il protocollo DHCP utilizza il modello client/server. L'amministratore di rete stabilisce uno o più server DHCP che mantengono le informazioni di configurazione TCP/IP e le inviano ai client. Il database del server include:

-   Parametri di configurazione validi per tutti i client della rete.

-   Indirizzi IP validi, mantenuti in pool per l’assegnazione ai client, oltre a indirizzi riservati all’assegnazione manuale.

-   Durata del lease offerto dal server. Il lease definisce il periodo di validità dell’indirizzo IP assegnato.

Il protocollo DHCP è uno standard IP, progettato per ridurre la complessità derivante dall’amministrazione delle configurazioni di indirizzi, che prevede l’utilizzo di un server per gestire centralmente gli indirizzi IP e altri dettagli di configurazione correlati, utilizzati nella rete. La famiglia di sistemi operativi Windows Server 2003 fornisce il servizio DHCP, che consente al computer utilizzato come server di agire da server DHCP, oltre che di configurare i computer client abilitati a DHCP nella rete, come descritto nello standard DHCP attualmente in fase di bozza, Internet Engineering Task Force (IETF) RFC (Request for Comments) 2131.

DHCP comprende il protocollo MADCAP (Multicast Address Dynamic Client Assignment Protocol), utilizzato per l’allocazione degli indirizzi in ambito multicast. Quando ai client registrati vengono dinamicamente assegnati indirizzi IP attraverso MADCAP, questi possono partecipare efficientemente al processo del flusso di dati, ad esempio per le trasmissioni di audio e video in tempo reale sulla rete.

Se in rete è installato e configurato un server DHCP, i client abilitati DHCP possono ottenere dinamicamente l’indirizzo IP e i relativi parametri di configurazione ogni volta che si avviano e accedono alla rete. I server DHCP forniscono questa configurazione ai client richiedenti sotto forma di un’offerta di lease degli indirizzi.

Se il servizio **Server DHCP** viene disattivato, il server non rilascerà automaticamente indirizzi IP o altri parametri di configurazione. Questo servizio viene installato e attivato solo se si configura un computer Windows Server 2003 come server DHCP.

#### File system distribuito

Il servizio **File System distribuito** gestisce i volumi logici distribuiti su una rete locale o WAN (Wide Area Network) ed è necessario per la condivisione del volume di sistema (SYSVOL) Active Directory. File system distribuito (DFS) è un servizio distribuito che integra diverse condivisioni di file in un singolo spazio dei nomi logico.

Tale spazio dei nomi è una rappresentazione logica delle risorse di archiviazione della rete a disposizione degli utenti di quest’ultima. Se il servizio **File System distribuito** viene disattivato, non sarà possibile accedere a condivisioni di file o dati di rete attraverso lo spazio dei nomi logico. Quando il servizio non è in esecuzione, per accedere ai dati è necessario conoscere i nomi di tutti i server e le condivisioni presenti nello spazio dei nomi e accedere indipendentemente a ognuna di queste destinazioni. Questo servizio è installato ed eseguito sui computer Windows Server 2003 per impostazione predefinita.

#### Manutenzione collegamenti distribuiti client

Il servizio di sistema **Manutenzione collegamenti distribuiti client** gestisce i collegamenti tra il file system NTFS nel computer o tra computer del dominio di rete. Il servizio garantisce che i collegamenti e i collegamenti OLE funzionino anche se il file di destinazione viene rinominato o spostato.

Quando si crea un collegamento a un file in un volume NTFS, il servizio di manutenzione dei collegamenti distribuiti inserisce nel file di destinazione un identificatore oggetto univoco, detto origine del collegamento. Nel file che fa riferimento al file di destinazione, detto client di collegamento, vengono memorizzate informazioni relative all’ID dell’oggetto. Nelle situazioni descritte di seguito, il servizio di manutenzione dei collegamenti distribuiti può utilizzare l’ID dell’oggetto per individuare il file di origine del collegamento:

-   Il file di origine del collegamento viene rinominato.

-   Il file di origine del collegamento viene spostato in un’altra cartella nello stesso volume o in un volume diverso dello stesso computer.

-   Il file di origine del collegamento viene spostato in un altro computer della rete.

    **Nota**: se il computer non fa parte del dominio in cui è disponibile il servizio **Manutenzione collegamenti distribuiti server**, questa forma di controllo dei collegamenti diviene meno affidabile nel tempo.

-   La cartella di rete condivisa che contiene il file di origine del collegamento viene rinominata.

In un dominio con Windows 2000 o Windows Server 2003 in cui è disponibile il servizio **Manutenzione collegamenti distribuiti server**, il file di origine del collegamento può essere presente nelle seguenti ulteriori situazioni:

-   Il computer che contiene il file di origine del collegamento viene rinominato.

-   Il volume contenente il file di origine del collegamento viene spostato in un altro computer dello stesso dominio.

Gli scenari in cui si trova il servizio **Manutenzione collegamenti distribuiti server** richiedono che nel computer client, cioè quello sul quale è in esecuzione il servizio **Manutenzione collegamenti distribuiti client**, sia configurato il criterio di sistema **DLT\_AllowDomainMode** per i client dotati di Windows XP con SP1 o SP2. In tutte le situazioni descritte in precedenza, il file di origine del collegamento deve trovarsi in un volume NTFS con Windows 2000, Windows XP o la famiglia di sistemi operativi Windows Server 2003. I volumi NTFS non possono essere in supporti rimovibili.

**Nota**: il servizio **Manutenzione collegamenti distribuiti client** controlla l’attività nei volumi NTFS e memorizza le informazioni di manutenzione in un file denominato Tracking.log, incluso nella cartella nascosta delle informazioni del volume di sistema, contenuta nella cartella principale di ogni volume. Questa cartella è protetta da autorizzazioni che ne consentono l’accesso esclusivamente da parte del computer. Tale cartella viene utilizzata anche da altri servizi di Windows, ad esempio il **Servizio di indicizzazione**.

Se il servizio **Manutenzione collegamenti distribuiti client** viene disattivato, i collegamenti al contenuto su quel computer non verranno più aggiornati.

#### Manutenzione collegamenti distribuiti server

Il servizio **Manutenzione collegamenti distribuiti server** memorizza le informazioni utili per tenere traccia dei file spostati tra i volumi del dominio. Quando attivo, il servizio **Manutenzione collegamenti distribuiti server** viene eseguito in ogni controller di un dominio e consente al servizio **Manutenzione collegamenti distribuiti client** di registrare i documenti collegati che sono stati spostati in un percorso di un altro volume NTFS nello stesso dominio.

Il servizio **Manutenzione collegamenti distribuiti server** è disabilitato per impostazione predefinita. Se lo si abilita, deve essere abilitato in tutti i controller del dominio. Se il servizio **Manutenzione collegamenti distribuiti server** viene abilitato in un controller di dominio aggiornato a una versione più recente Windows Server, sarà necessario riabilitarlo manualmente.

Se è abilitato il servizio **Manutenzione collegamenti distribuiti server**, sarà necessario abilitare il criterio di sistema **DLT\_AllowDomainMode** perché i computer client con Windows XP possano utilizzarlo. Se inizialmente si abilita il servizio **Manutenzione collegamenti distribuiti server** e in seguito lo si disabilita, eliminare le relative voci in Active Directory. Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Servizio Manutenzione collegamenti distribuiti sui controller di dominio basati su Windows](http://support.microsoft.com/kb/312403/it)" all'indirizzo http: //support.microsoft.com/kb/312403/.

Se il servizio **Manutenzione collegamenti distribuiti server** viene arrestato o disattivato, alla fine i collegamenti conservati dal servizio **Manutenzione collegamenti distribuiti client** perderanno di affidabilità.

In Windows Server 2003, il servizio **Manutenzione collegamenti distribuiti server** è installato ma disattivato per impostazione predefinita.

#### Distributed Transaction Coordinator

Il servizio **Distributed Transaction Coordinator** coordina le transazioni distribuite su più computer e/o gestori di risorse, quali database, code di messaggi, file system o altri gestori di risorse basati su transazioni. Questo servizio è necessario se i componenti delle transazioni dovranno essere configurati tramite COM+. È necessario inoltre per le code di transazioni in Accodamento messaggi (MSMQ) e per operazioni di SQL Server distribuite tra più computer.

Il servizio **Distributed Transaction Coordinator** è installato e attivato per impostazione predefinita. Se lo si disabilita, le transazioni che utilizzano questo servizio non verranno eseguite. Le installazioni cluster di Microsoft Exchange e SQL Server o le altre applicazioni che utilizzano i servizi di transazione potrebbero essere influenzate se questo servizio viene disattivato.

#### Client DNS

Il servizio **Client DNS** risolve i nomi DNS e li memorizza nella cache del computer. Il servizio **Client DNS** deve essere eseguito in tutti i computer che eseguono la risoluzione dei nomi DNS. La risoluzione dei nomi DNS è necessaria per localizzare i controller di dominio di Active Directory. Il servizio **Client DNS** è necessario anche per attivare la localizzazione delle periferiche identificate attraverso la risoluzione dei nomi DNS.

Il servizio **Client DNS** in esecuzione in Windows Server 2003 implementa le funzionalità riportate di seguito:

-   **Cache in tutto il sistema**. I record di risorse derivanti dalle risposte alle query vengono inseriti nella cache del client quando le applicazioni inviano query ai server DNS. Queste informazioni vengono conservate nella cache per una durata impostata e potranno essere utilizzate nuovamente per rispondere ad altre query.

-   **Supporto per l’inserimento nella cache delle risposte negative come da RFC**. Oltre alle risposte positive alle query, fornite dai server DNS, le quali contengono informazioni relative ai record delle risorse, il servizio **Client DNS** inserisce nella cache anche le risposte negative.

    La risposta negativa si verifica quando non esistono record di risorse per il nome oggetto della query. L’inserimento delle risposte negative nella cache impedisce che vengano ripetute query relative a nomi inesistenti, le quali possono avere ripercussioni sulle prestazioni del computer client. Le informazioni relative a query negative vengono conservate nella cache per un periodo più breve rispetto alle risposte positive, non più di 5 minuti, per impostazione predefinita. Questa configurazione evita in tal modo che nella cache permangano informazioni non aggiornate nel caso i record divenissero disponibili in seguito.

-   **I server DNS che non rispondono vengono evitati**. Il servizio **Client DNS** utilizza un elenco di ricerca dei server, ordinato in base alla preferenza. Nell’elenco sono contenuti tutti i server DNS preferiti e alternativi, configurati per ciascuna connessione di rete attiva nel sistema. Questi elenchi, in Windows Server 2003, vengono riordinati in base ai criteri riportati di seguito:

    -   Ai server DNS preferiti viene attribuita la priorità più alta.

    -   Se non sono disponibili server DNS preferiti, vengono utilizzati quelli alternativi.

    -   I server che non rispondono vengono temporaneamente rimossi dagli elenchi.

Se il servizio **Client DNS** viene disattivato, il computer non sarà in grado di risolvere i nomi DNS e di individuare i controller di dominio Active Directory e gli utenti potrebbero non riuscire ad accedere al computer.

#### Server DNS

Il servizio **Server DNS** consente la risoluzione dei nomi DNS, rispondendo alle query e aggiornando le richieste di nomi DNS. I server DNS sono necessari per localizzare le periferiche identificate attraverso i nomi DNS e i controller di dominio in Active Directory.

Se il servizio **Server DNS** viene arrestato o disattivato, gli aggiornamenti DNS non verranno eseguiti. Non è necessario che il servizio **Server DNS** venga eseguito su ogni computer; se tuttavia non esiste un server autorevole per una parte specifica dello spazio dei nomi DNS, non sarà possibile individuare le periferiche utilizzando i nomi DNS in tale parte dello spazio dei nomi. L’assenza di un server DNS autorevole per lo spazio dei nomi DNS utilizzato per attribuire un nome ai domini Active Directory ha come conseguenza l’incapacità di individuare i controller del dominio.

Il servizio **Server DNS** viene installato e attivato solo se si configura un computer Windows Server 2003 come server DNS.

#### Servizio di segnalazione errori

Il **Servizio di segnalazione errori** raccoglie, archivia e segnala a Microsoft gli eventi imprevisti di chiusura o gli errori delle applicazioni, nonché autorizza la segnalazione di errori per servizi e applicazioni in esecuzione in ambienti non standard. Questo servizio fornisce ai gruppi che sviluppano i prodotti Microsoft informazioni importanti e utili per il debug di driver e applicazioni.

È possibile configurare questo servizio in modo da inviare informazioni su errori specifiche per Microsoft e da segnalare gli errori del sistema operativo, dei componenti di Windows o dei programmi. Gli errori del sistema operativo fanno sì che venga visualizzata una schermata di arresto contenente codici di errore. Gli errori di programmi o componenti fanno sì che il programma o componente smetta di funzionare.

Se si dispone di una connessione Internet è possibile segnalare questi errori direttamente a Microsoft. È possibile configurare la segnalazione errori per gli errori dei programmi procedendo in uno dei due seguenti modi: non appena si verifica l’errore, viene visualizzata la finestra di dialogo **Segnalazione errori** che avvisa l’utente di inviare l’errore a Microsoft, oppure la finestra di dialogo **Segnalazione errori** viene visualizzata al successivo accesso dell’amministratore, per avvisarlo di inviare la segnalazione dell’errore a Microsoft.

In Windows gli errori del sistema operativo e gli arresti non pianificati vengono trattati diversamente dagli errori dei programmi. Quando si verificano errori del sistema operativo o arresti non pianificati, l’errore viene scritto in un file di registro. Al successivo accesso dell’amministratore verrà visualizzata la finestra di dialogo **Segnalazione errori** per avvisarlo di segnalare l’errore. Inviando a Microsoft una segnalazione di errore via Internet, si forniscono a Microsoft informazioni tecniche che potranno utilizzare per le versioni future del prodotto. Questi dati vengono utilizzati esclusivamente a scopo di controllo di qualità e non per tenere traccia dei singoli utenti o installazioni a fini commerciali. Se sono disponibili informazioni per risolvere il problema, in Windows viene visualizzata un **’altra finestra di dialogo** Segnalazione errori contenente un collegamento a tali informazioni.

Se, in alternativa, l’organizzazione ha configurato i criteri di gruppo, gli amministratori del reparto IT potranno utilizzare Segnalazione errori a server interno per raccogliere le informazioni e segnalare solo gli errori che ritengono importanti. Per configurare Segnalazione errori a server interno, gli amministratori abilitano l’impostazione del criterio Segnala errori e configurano Percorso file caricamento aziendale con il file server locale in cui è installato lo strumento Segnalazione errori a server interno. Quando si verifica un errore, le informazioni sono automaticamente reindirizzate al file server impostato. Gli amministratori potranno riesaminare le informazioni relative agli errori, identificare i dati importanti e inoltrarli a Microsoft utilizzando lo strumento Segnalazione errori a server interno. È possibile scaricare lo strumento Segnalazione errori a server interno dal sito Web del [Resource Kit di Office XP](http://www.microsoft.com/downloads/details.aspx?familyid=25b30c79-b248-4eb9-8057-be0043f5b881&displaylang=en) all’indirizzo www.microsoft.com/office/ork/xp/default.htm.

Se il **Servizio di segnalazione errori** viene arrestato, la segnalazione errori non avviene. Se l'impostazione **Visualizza notifica errori** è attivata nella finestra di dialogo **Segnalazione errori**, gli utenti ricevono un messaggio quando si verifica un problema, ma non possono segnalare l’errore a Microsoft o a una condivisione della rete locale. Per impostazione predefinita, questo servizio è installato ed eseguito.

#### Registro eventi

Il servizio di sistema **Registro eventi** consente di visualizzare nel Visualizzatore eventi i messaggi del registro eventi generati da componenti e programmi basati su Windows. Questi messaggi del registro eventi contengono informazioni che consentono di identificare i problemi relativi alle applicazioni, ai servizi e al sistema operativo. È possibile visualizzare i registri mediante le API di registro eventi o attraverso lo snap-in Visualizzatore eventi MMC.

Per impostazione predefinita, in un computer che esegue un sistema operativo della famiglia di prodotti Windows Server 2003, gli eventi vengono registrati in tre tipi di registri:

-   **Registro dell’applicazione**. Questo registro conserva gli eventi delle applicazioni. Un programma di database potrebbe, ad esempio, registrare nel registro dell’applicazione un errore di file. Sono gli sviluppatori di programmi a decidere quali eventi registrare.

-   **Registro di protezione**. Questo registro conserva eventi quali i tentativi di accesso validi e non validi, oltre a eventi correlati all’utilizzo delle risorse, quali la creazione, l’apertura e l’eliminazione di file e altri oggetti. Se è abilitato, ad esempio, il controllo dell’accesso, nel registro di protezione vengono registrati i tentativi di accesso al computer.

-   **Registro del sistema**. Questo registro conserva eventi relativi ai componenti di Windows. Nel registro del sistema vengono, ad esempio, registrati errori di caricamento di un driver o altro componente all’avvio. I tipi di eventi registrati dai componenti di Windows sono predeterminati dal server.  

In un computer basato su Windows Server 2003 configurato come controller di dominio, gli eventi vengono registrati in due registri aggiuntivi:

-   **Registro dei servizi directory**. Questo registro conserva eventi relativi ad Active Directory. Qui vengono registrati, ad esempio, i problemi di connessione fra il server e il catalogo globale.

-   **Registro del servizio Replica file**. Questo registro conserva gli eventi del servizio Replica file di Windows. Qui vengono registrati, ad esempio, gli eventi e gli errori di replica dei file che si verificano mentre è in corso l’aggiornamento dei controller di dominio con informazioni relative a modifiche del volume di sistema.

In un computer che esegue Windows, configurato come server DNS, gli eventi vengono registrati in un ulteriore registro:

-   **Registro del server DNS**. Questo registro contiene gli eventi registrati dal servizio DNS di Windows.

Non è possibile arrestare il servizio **Registro eventi**. Se il servizio viene disabilitato, sarà impossibile tenere traccia degli eventi, cosa che ridurrebbe in modo significativo la capacità di individuare correttamente i problemi del computer. Non sarà inoltre possibile controllare gli eventi di protezione e visualizzare i registri eventi precedenti utilizzando lo snap-in Visualizzatore eventi di MMC.

#### Compatibilità di Cambio rapido utente

Il servizio **Compatibilità di Cambio rapido utente** consente di gestire le applicazioni che richiedono assistenza in un ambiente multi-utente. La funzionalità Cambio rapido utente in Windows XP consente agli utenti che hanno effettuato contemporaneamente l'accesso al computer di passare con facilità da una sessione all'altra. Non è necessario arrestare le applicazioni e disconnettersi.

Molti programmi non sono stati progettati per essere eseguiti in un ambiente multi-utente e potrebbero verificarsi dei problemi quando più utenti effettuano l'accesso al computer. Il servizio **Compatibilità di Cambio rapido utente** effettua una delle seguenti procedure quando è in uso un programma che presenta problemi e quando Cambio rapido utente è attivato:

-   Con i programmi di Tipo 1, il servizio consente all'utente di chiudere la prima istanza di questi programmi quando ne viene avviata una seconda. Questa procedura è la meno intrusiva, ma l'utente deve disporre di privilegi amministrativi.

-   Con i programmi di Tipo 2, questi vengono chiusi dal servizio quando ci si disconnette dalla sessione (attraverso la procedura Cambio rapido utente o quando il computer torna alla schermata Welcome dopo che lo screen saver è stato eliminato).

-   Con i programmi di Tipo 3, questi vengono chiusi quando ci si disconnette dalla sessione e riavviati al momento della riconnessione. Questa opzione è utile per i programmi che utilizzano risorse che non vengono facilmente condivise tra sessioni multiple, come le porte COM.

-   Con i programmi di Tipo 4, questi vengono chiusi quando un altro utente effettua l'accesso. Questa opzione è adatta ai programmi che possono essere intrusivi verso il computer ma che non è necessario chiudere quando si torna alla schermata Welcome. Il programma continuerà a essere in esecuzione quando l'utente si disconnette e verrà chiuso solo quando un altro utente effettuerà l'accesso.

Se si disattiva il servizio **Compatibilità di Cambio rapido utente**, alcune applicazioni potrebbero non funzionare correttamente su un computer in cui la funzionalità Cambio rapido utente è attivata.

#### Servizio fax

Il **servizio Fax**, un servizio compatibile con TAPI (Telephony Application Programming Interface), fornisce funzionalità fax al computer. Il **Servizio Fax** consente agli utenti di inviare e ricevere fax dalle applicazioni del desktop, utilizzando una periferica FAX locale o condivisa in rete. Questo servizio offre le seguenti funzionalità:

-   Invio e ricezione di fax

-   Controllo dell’attività fax

-   Routing dei fax in ingresso

-   Gestione della configurazione di server e periferiche

-   Archiviazione dei fax inviati

Se il servizio di telefonia o dello spooler di stampa è disabilitato, il **servizio Fax** non si avvierà correttamente. Se questo servizio viene disattivato, gli utenti non saranno in grado di inviare o ricevere fax. Il **Servizio Fax** si arresta quando non vi sono fax e si riavvia secondo necessità.

#### Replica file

Il servizio **Replica file** consente la copia automatica e la gestione dei file simultanea su più server. Il servizio Replica file (FRS) è il servizio di replica automatica dei file nella famiglia di prodotti Windows 2000 e Windows Server 2003 e la sua funzione è replicare il contenuto del volume di sistema (SYSVOL) tra tutti i controller di un dominio. Può essere configurato anche per la replica di file in destinazioni alternative, associate al servizio DFS con tolleranza d'errore.

Se il servizio **Replica file** viene arrestato, la replica dei file non ha luogo e i dati dei server non vengono sincronizzati. Inoltre, se si arresta questo servizio, la funzionalità di un controller di dominio potrebbe essere seriamente compromessa. Il servizio **Replica file** è installato per impostazione predefinita su Windows Server 2003, ma il suo stato di avvio è configurato su **Manuale.**

#### File server per Macintosh

Il servizio **File server per Macintosh** consente agli utenti di Macintosh di memorizzare e accedere ai file sui computer dotati di Windows Server 2003. Se questo servizio viene disattivato, i computer client Macintosh non saranno in grado di memorizzare e accedere ai file dei computer basati su Windows Server 2003. Per impostazione predefinita, questo servizio non è installato o attivato.

#### Servizio Pubblicazione FTP

Il **servizio Pubblicazione FTP** fornisce la connettività FTP e funzionalità di amministrazione attraverso lo snap-in Microsoft Internet Information Server (IIS). Le funzionalità includono la tecnologia di limitazione della larghezza di banda, account di protezione e registrazione estendibile. È inoltre inclusa la nuova funzionalità di isolamento dell’utente FTP, che consente agli utenti di accedere solo ai propri file in un sito FTP. Il supporto internazionale è inoltre stato migliorato.

Se il **servizio Pubblicazione FTP** viene arrestato, il server non potrà fungere da server FTP. Questo servizio non è installato per impostazione predefinita.

#### Guida in linea e supporto tecnico

Il servizio **Guida in linea e supporto tecnico** consente l’esecuzione dell’applicazione Guida in linea e supporto tecnico sui computer degli utenti, supporta l’applicazione e consente la comunicazione tra l’applicazione client e i dati della Guida in linea. Il servizio comprende l’accesso ad archivi e servizi, quali database di tassonomia contenenti metadati, informazioni riguardanti gli argomenti della Guida in linea, l’infrastruttura per l’automazione del supporto che consente di raccogliere dati per provider di supporto registrati, informazioni sulla cronologia e le preferenze dell’utente, nonché la gestione del motore di ricerca. Quando si interagisce con funzionalità di Guida in linea e supporto tecnico quali ricerca, indice e sommario, il servizio attiva il supporto per le transazioni di dati per tutte queste funzionalità.

Se il servizio **Guida in linea e supporto tecnico** è configurato su **Manuale**, questo si avvierà quando un utente accede alla Guida in linea e supporto tecnico dal desktop. Se questo servizio viene disattivato o arrestato, gli utenti non potranno utilizzare l'applicazione Guida in linea e supporto tecnico e sarà visualizzato il seguente messaggio:

Impossibile aprire la Guida in linea e supporto tecnico perché un servizio di sistema non è in esecuzione.

Gli utenti saranno in grado di accedere ad alcuni argomenti di alto livello che potrebbero essere memorizzati nella cache sul computer locale, ma la maggior parte delle funzionalità dell'applicazione Guida in linea e supporto tecnico (compresa l'Assistenza remota) non può essere eseguita se il servizio **Guida in linea e supporto tecnico** non è attivato. Tuttavia, gli utenti possono visualizzare i file \*.HLP e \*.CHM presenti nella cartella **Windows\\Help.** Il servizio **Guida in linea e supporto tecnico** è installato e avviato automaticamente per impostazione predefinita in Windows XP e in Windows Server 2003.

#### SSL HTTP

Il servizio **SSL HTTP** consente l'esecuzione di funzioni SSL (Secure Sockets Layer) in IIS. SSL è uno standard aperto per stabilire un canale di comunicazione protetto in modo da impedire l'intercettazione di informazioni critiche, ad esempio i numeri delle carte di credito. In primo luogo abilita le transazioni finanziarie elettroniche protette sul World Wide Web, nonostante sia progettato per funzionare anche con altri servizi Internet.

Se il servizio di sistema **SSL HTTP** viene arrestato, in IIS non sarà possibile eseguire le funzioni SSL. Questo servizio è installato quando IIS è installato e non è presente in altre posizioni e non è stato attivato in altro modo.

#### Accesso periferica Human Interface

Il servizio **Accesso periferica Human Interface** consente l’accesso con input generico alle periferiche USB (Universal Serial Bus) come le tastiere e i mouse. Il servizio attiva e gestisce l’uso dei pulsanti speciali di tastiere, telecomandi e altre periferiche multimediali. Questo servizio è installato e avviato per impostazione predefinita sui computer Windows XP e Windows Server 2003.

Se il servizio di sistema **Accesso periferica Human Interface** viene arrestato, i pulsanti speciali da esso controllati non funzionano più. Ad esempio, non funzioneranno i pulsanti delle tastiere USB (Universal Serial Bus) come Avanti, Indietro, Volume, Brano precedente ecc. e quelli del volume degli altoparlanti USB.

#### IAS Jet Database Access

Il servizio **IAS Jet Database Access** utilizza il protocollo RADIUS (Remote Authentication Dial-in User Service) per fornire servizi di autenticazione, autorizzazione e accounting. È disponibile solo nelle versioni di Windows a 64 bit. Con IAS (Internet Authentication Services) è possibile gestire centralmente l’autenticazione, l’autorizzazione e l’accounting degli utenti. È inoltre possibile utilizzare IAS per autenticare gli utenti relativamente ai controller di dominio che eseguono i sistemi operativi Windows NT 4.0, Windows 2000 o Windows Server 2003. IAS funziona correttamente sia in reti omogenee sia eterogenee.

È possibile utilizzare IAS come proxy per il routing dei messaggi fra client (server di accesso) e server RADIUS che eseguono l’autenticazione, l’autorizzazione e l’accounting di utenti per il tentativo di connessione. Se utilizzato come proxy RADIUS, IAS costituisce un punto di routing o commutazione centrale attraverso cui fluiscono l’accesso RADIUS e i messaggi di accounting. IAS registra le informazioni relative ai messaggi inoltrati in un file di accounting.

Un’infrastruttura di autenticazione, autorizzazione e accounting RADIUS è costituita dai componenti riportati di seguito:

Esistono due database Jet per IAS: Ias.mdb, utilizzato per configurare IAS, e Dnary.mdb, utilizzato per convalidare il dizionario utilizzato da IAS per tenere traccia di attributi specifici del fornitore di server NAS compatibili con RADIUS. Non modificare i database Jet.

Se il servizio di sistema **IAS Jet Database Access** viene arrestato, non sarà disponibile la connessione remota alla rete che prevede l’autenticazione degli utenti. Non funzioneranno, ad esempio, l’Accesso remoto, VPN, LAN senza fili (802.1x) ed Ethernet 802.1x. Se questo servizio è disabilitato, sia il **servizio Routing e accesso remoto (RRAS, Routing and Remote Access Service)** sia **IAS** non si avvieranno. Non sarà inoltre possibile amministrare RRAS o IAS sia localmente sia remotamente. Per impostazione predefinita, questo servizio non è installato su nessuna versione di Windows; è disponibile soltanto sulle versioni basate su Itanium della famiglia di prodotti Windows Server 2003.

#### Servizio Amministrazione di IIS

Il **Servizio Amministrazione di IIS** consente di amministrare componenti di IIS quali FTP, Pool di applicazioni, siti Web, estensioni dei servizi Web e server virtuali NNTP (Network News Transfer Protocol) e SMTP (Simple Mail Transfer Protocol). Se questo servizio viene arrestato o disabilitato, non sarà possibile eseguire siti Web, FTP, NNTP o SMTP.

In Windows 2000, il **servizio Amministrazione di IIS** e servizi correlati vengono installati per impostazione predefinita. Nella famiglia di prodotti Windows Server 2003 i componenti di IIS devono essere installati utilizzando Installazione componenti di Windows o Configurazione server.

#### Servizio COM di masterizzazione CD IMAP

Il **servizio COM di masterizzazione CD IMAPI** gestisce la creazione dei CD tramite l’interfaccia COM IMAPI (Image Mastering Applications Programming Interface) ed esegue operazioni di scrittura su CD scrivibili (CD-R) quando richiesto dall'utente tramite Esplora risorse, Windows Media Player (WMP) o applicazioni di terze parti che utilizzano questa API. IMAPI consente alle applicazioni di salvare temporaneamente e masterizzare immagini di semplice audio o dati su periferiche CD-R e CD-RW. API supporta dischi audio e di dati Redbook, sia con Joliet sia con ISO 9660. L’architettura consente una futura espansione dell’insieme di formati supportati.

Se il **servizio COM di masterizzazione CD IMAPI** viene arrestato o disattivato, il computer non sarà in grado di registrare CD con le funzionalità incorporate in Windows XP e Windows Server 2003. Se si utilizza un’applicazione di terze parti per la scrittura su CD-RW, disattivando questo servizio non si avrà alcun impatto sulla registrazione dei CD-R, purché il software di terze parti non vi faccia affidamento. Se il servizio viene avviato dopo l’accesso, è necessario disconnettersi dal computer e riconnettersi nuovamente per scrivere dati su supporti CD-R, mediante la periferica CD-R, utilizzando Esplora risorse di Windows. Questo servizio è installato per impostazione predefinita su Windows XP, ma non viene avviato finché un utente non richiede la scrittura su CD-R attraverso Esplora Risorse. Su Windows Server 2003 è installato ma disattivato per impostazione predefinita.

#### Servizio di indicizzazione

Il **Servizio di indicizzazione** indicizza contenuti e proprietà di file in computer locali e remoti e consente di accedere rapidamente ai file tramite un linguaggio di query flessibile. Il **Servizio di indicizzazione** consente, inoltre, di cercare rapidamente documenti in computer locali e remoti e mette a disposizione un indice di ricerca per contenuti condivisi sul Web. Il servizio crea indici di tutte le informazioni testuali contenute in file e documenti. Una volta completata la creazione iniziale dell’indice, il **Servizio di indicizzazione** lo aggiorna ogni volta che viene creato, modificato o eliminato un file.

L’indicizzazione iniziale può richiedere molte risorse. Per impostazione predefinita, il **Servizio di indicizzazione** è impostato per essere avviato manualmente. Quando il servizio è abilitato, esso crea gli indici solo quando il computer è inattivo, sebbene sia possibile utilizzare lo snap-in MMC Indici per configurare il servizio in modo da funzionare quando il computer è attivo. MMC consente inoltre di ottimizzare la configurazione dell’allocazione di risorse al servizio per gli schemi di utilizzo dell’indicizzazione o delle query.

Se il **Servizio di indicizzazione** viene arrestato, le ricerche basate sul testo risulteranno rallentate.

#### Monitor infrarossi

Il servizio **Monitor infrarossi** consente la condivisione di file e immagini con le connessioni a infrarossi. Questo servizio viene installato per impostazione predefinita su Windows XP soltanto se, durante l’installazione del sistema operativo, viene rilevata una periferica a infrarossi. Il servizio non è disponibile in Windows Server 2003 Web Edition, Enterprise Edition e Datacenter Edition.

Se il servizio **Monitor infrarossi** viene arrestato, non è possibile condividere file e immagini utilizzando la tecnologia a infrarossi.

#### Servizio autenticazione Internet

Il **Servizio autenticazione Internet** (IAS) esegue l'autenticazione, l'autorizzazione, il controllo e la creazione di account a livello centralizzato degli utenti che si connettono a una rete LAN o remota mediante una rete privata virtuale (VPN), l'Amministrazione Accesso remoto (RAS) o i punti di accesso 802.1x Wireless e Ethernet/Switch.

**IAS** implementa lo standard IETF per il protocollo RADIUS, che consente di utilizzare apparecchiature eterogenee per l’accesso alla rete. Disattivando o arrestando **IAS**, si causa il failover delle richieste di autenticazione a un server IAS di backup, se disponibile. Se non sono disponibili server IAS di backup, gli utenti non saranno in grado di connettersi alla rete. Questo servizio deve essere installato manualmente ed è disponibile soltanto sui prodotti della famiglia Windows Server 2003.

#### Messaggistica tra siti

Il servizio di sistema **Messaggistica tra siti** consente lo scambio di messaggi tra computer in cui sono in esecuzione siti basati su Windows Server. Questo servizio viene utilizzato per la replica tra siti basata sulla posta elettronica. In Active Directory per supportare la replica tra siti viene utilizzato SMTP sul trasporto IP. Il supporto SMTP è fornito dal servizio **SMTP**, il quale è un componente di IIS.

L’insieme di trasporti utilizzato per le comunicazioni fra siti deve essere estensibile, pertanto ogni trasporto è definito in un file DLL (Dynamic Link Library) aggiuntivo. Questi file DLL aggiuntivi vengono caricate nel servizio **Messaggistica tra siti**, in esecuzione in tutti i controller di dominio in grado di comunicare tra siti. Il servizio **Messaggistica tra siti** indirizza le richieste di invio e ricezione alle DLL aggiuntive di trasporto corrette, che quindi indirizzano i **messaggi** al corrispondente servizio del computer di destinazione.

Se il servizio **Messaggistica tra siti** viene arrestato, i messaggi non verranno scambiati, la replica della messaggistica tra siti non funzionerà e non verranno calcolate le informazioni di routing dei siti per gli altri servizi. Questo servizio è installato per impostazione predefinita sui computer Windows Server 2003, ma è disattivato finché il server non viene convertito in controller di dominio.

#### Servizio Helper IPv6

Il **servizio Helper IPv6** offre la connettività IPv6 (Internet Protocol Version 6) in reti IPv4. IPv6 è una nuova suite di protocolli standard per il livello di rete di Internet, progettata per risolvere molti problemi di IPv4 relativi alla svalutazione degli indirizzi, protezione, configurazione automatica ed estensibilità. Questo servizio, spesso definito "6to4", consente ai siti e agli host abilitati a IPv6 di comunicare utilizzando IPv6 in una infrastruttura IPv4, ad esempio Internet. I siti e gli host IPv6 possono utilizzare il proprio prefisso di indirizzo 6to4 e Internet per comunicare, senza ottenere un prefisso di indirizzo globale IPv6 da un provider di servizi Internet (ISP, Internet Service Provider)e connettersi a 6bone, la parte di Internet abilitata a IPv6.

6to4 è una tecnica di tunneling descritta nella RFC 3056. Gli host 6to4 non richiedono configurazione manuale e creano indirizzi 6to4 utilizzando la configurazione automatica standard. 6to4 utilizza il prefisso di indirizzo globale 2002:WWXX:YYZZ::/48, dove WWXX:YYZZ è la rappresentazione esadecimale separata da due punti di un indirizzo IPv4 pubblico (w.x.y.z) assegnato a un sito o host, detta anche parte NLA (Next Level Aggregator) di un indirizzo 6to4.

Il **servizio Helper IPv6** supporta 6over4, definito anche tunneling multicast IPv4, una tecnica descritta nella RFC 2529. 6over4 consente a nodi IPv6 e IPv4 di comunicare utilizzando IPv6 in una struttura IPv4. 6over4 utilizza l’infrastruttura IPv4 come collegamento abilitato al multicast. Perché 6over4 funzioni correttamente, l’infrastruttura IPv4 deve essere abilitata al multicast IPv4.

Se il **servizio Helper Ipv6** viene arrestato, il computer disporrà esclusivamente della connettività IPv6, se è connesso a una rete IPv6 nativa. Per impostazione predefinita, questo servizio non è installato o attivato.

#### Agente criteri IPSec (servizio IPSec)

Il servizio **Agente criteri IPSec (servizio IPSec)** fornisce la protezione end-to-end fra client e server su reti TCP/IP, gestisce i criteri IPSec, avvia IKE (Internet Key Exchange) e coordina le impostazioni dei criteri IPSec con il driver di protezione IP. Il servizio viene controllato utilizzando i comandi NET START e NET STOP.

IPSec funziona al livello IP ed è trasparente agli altri servizi e applicazioni del sistema operativo. Questo servizio fornisce il filtraggio dei pacchetti ed è in grado negoziare la protezione fra i computer in reti IP. È possibile configurare IPSec in modo da fornire:

-   Filtraggio dei pacchetti, con azioni per consentire, bloccare o negoziare la protezione.

-   Comunicazione IP protetta e attendibile negoziata. Il protocollo IKE autentica reciprocamente il mittente e il destinatario dei pacchetti di dati IP in base alle impostazioni dei criteri. Per l’autenticazione può essere utilizzato il protocollo Kerberos, certificati digitali o una chiave segreta condivisa (password). IKE genera automaticamente chiavi di crittografia e associazioni di protezione IPSec.

-   Protezione dei pacchetti IP attraverso formati IPSec che offrono l’integrità crittografica, l’autenticità e, se lo si desidera, la crittografia dei pacchetti IP.

-   Connessioni end-to-end protette utilizzando la modalità di trasporto IPSec.

-   Tunnel IP protetti con la modalità di tunneling IPSec.

IPSec fornisce inoltre la protezione per le connessioni VPN L2TP (Layer Two Tunneling Protocol).

Se il servizio **Agente criteri IPSec (servizio IPSec)** viene arrestato, la protezione TCP/IP fra e client e server della rete viene compromessa. Questo servizio è installato e attivato per impostazione predefinita sui computer Windows Server 2003 Windows XP.

#### Centro distribuzione chiave Kerberos

Il servizio **Centro distribuzione chiave Kerberos** consente agli utenti di accedere alla rete ed essere autenticati mediante il protocollo di autenticazione Kerberos v5.

Analogamente ad altre implementazioni del protocollo Kerberos, la distribuzione della chiave Kerberos è un processo singolo che comprende due servizi:

-   **Servizio di autenticazione**. Questo servizio emette ticket di concessione ticket (TGT, Ticket-Granting Ticket) per la connessione al servizio di concessione dei ticket nel proprio dominio o in altri domini attendibili. Perché un client possa richiedere un ticket a un altro computer deve prima richiedere un TGT al servizio di autenticazione nel dominio dell’account del client. Il servizio di autenticazione restituisce un ticket di concessione ticket per il servizio di concessione interno al dominio del computer. Il ticket di concessione ticket può essere riutilizzato fino alla scadenza ma, al primo accesso al servizio di concessione ticket di un dominio, è sempre necessario che il computer client contatti il servizio di autenticazione del proprio dominio.

-   **Servizio di concessione ticket (TGS, Ticket-Granting Service)**. Questo servizio emette ticket per la connessione ai computer che fanno parte del proprio dominio. Perché un client possa accedere a un altro computer, deve richiedere un TGT e quindi un ticket per il computer. Il ticket può essere riutilizzato fino alla scadenza ma, al primo accesso a un qualunque computer, è sempre necessario contattare il servizio di concessione ticket nel dominio di cui fa parte l’account del computer di destinazione.

Se il servizio **Centro distribuzione chiave Kerberos** viene arrestato, gli utenti non saranno in grado di accedere alla rete e alle risorse. Questo servizio è installato su tutti i computer Windows Server 2003, ma viene eseguito solo nei controller di dominio. Se questo servizio viene disattivato, gli utenti non potranno accedere al dominio.

#### Servizio registrazione licenze

Il **Servizio registrazione licenze** controlla e registra le informazioni relative alle licenze di accesso client a parti del sistema operativo, quali IIS, Servizi terminal, condivisione di file e stampanti, e prodotti che non fanno parte del sistema operativo, quali SQL Server o Microsoft Exchange Server.

Se il **Servizio registrazione licenze** viene arrestato o disattivato, le licenze vengono applicate, ma non saranno controllate. Questo servizio è disabilitato sui computer Windows Server 2003 per impostazione predefinita.

#### Gestione dischi logici

Il servizio di sistema **Gestione dischi logici** rileva e controlla le nuove unità disco rigido e invia informazioni sui volumi dei dischi al **Servizio amministrativo di Gestione dischi logici** per la configurazione. Questo servizio controlla gli eventi Plug and Play per rilevare nuove unità e utilizza un servizio di amministrazione e un servizio watchdog. Non disattivare il servizio se nel computer sono presenti servizi dinamici.

Il servizio **Gestione dischi logici** viene eseguito per impostazione predefinita sui computer Windows Server 2003 e Windows XP. Se viene arrestato, lo stato e le informazioni di configurazione dei dischi dinamici potrebbero non essere aggiornate. Le unità disco rigido, ad esempio, potrebbero non essere rilevate. Il servizio di amministrazione e il servizio watchdog costituiscono essenzialmente un unico componente. Il servizio amministrativo viene avviato esclusivamente quando si configura un’unità o partizione, oppure quando viene rilevata una nuova unità.

#### Servizio amministrativo di Gestione disco logico

Il **Servizio amministrativo di Gestione dischi logici** amministra le richieste di gestione dei dischi e configura le unità disco rigido e i volumi. Viene avviato solo quando si configura un’unità o partizione, oppure quando viene rilevata una nuova unità. Questo servizio non si avvia per impostazione predefinita, ma viene attivato quando la configurazione dei dischi dinamici viene modificata o quando si apre lo snap-in Gestione disco MMC o si avvia lo strumento Diskpart.exe. Le modifiche che danno luogo all’attivazione del servizio sono la conversione di un disco di base in disco dinamico, il ripristino di volumi con tolleranza d’errore, la formattazione di volumi o la modifica di un file di paging.

Il **Servizio amministrativo di Gestione dischi logici** viene eseguito solo per i processi di configurazione e quindi si arresta. Se viene disabilitato, i tentativi di utilizzare lo snap-in Gestione disco di MMC per configurare dischi daranno luogo al messaggio di errore riportato di seguito:

Connessione al servizio Gestione dischi logici non riuscita.

#### Machine Debug Manager

Il servizio **Machine Debug Manager** gestisce il debug locale e remoto di alcune applicazioni, come Microsoft Script Editor, diverse versioni di Office application suite e Microsoft Visual Studio.

Se il servizio **Machine Debug Manager** viene disattivato, i tentativi di debug degli script o dei processi non avranno esito positivo e sarà visualizzato il seguente messaggio di errore:

Impossibile avviare il debug. Il servizio Machine Debug Manager è disattivato.

Inoltre, gli utenti non potranno eseguire il debug degli errori negli script delle pagine Web.

#### Accodamento messaggi

Il servizio **Accodamento messaggi** è un’infrastruttura di messaggistica e uno strumento di sviluppo per la creazione di applicazioni di messaggistica distribuite per Windows. Tali applicazioni possono comunicare attraverso reti eterogenee e inviare messaggi tra computer nel caso in cui questi non siano temporaneamente in grado di connettersi l'uno con l'altro. Questo servizio garantisce il recapito dei messaggi e offre servizi di routing efficienti, protezione e messaggistica basata sulla priorità. Supporta inoltre l'invio di messaggi all'interno delle transazioni e offre sia API Microsoft Win32 sia API COM per tutte le funzionalità di programmazione, incluse amministrazione e gestione.

L'implementazione delle funzionalità di lettura remota nella versione Windows XP del servizio **Accodamento messaggi** consente agli utenti non autenticati di connettersi alle code. Un utente malintenzionato potrebbe rimuovere una coda e creare una condizione di negazione del servizio. Inoltre, i dati della lettura remota di Accodamento messaggi vengono trasmessi sulla rete in testo non crittografato, il che significa che potrebbero venire letti da un utente malintenzionato capace di acquisire dati di rete.

Per queste ragioni, Microsoft consiglia di non installare il servizio **Accodamento messaggi** sui computer Windows XP esposti a reti non attendibili come Internet. In Windows XP, il servizio non è installato per impostazione predefinita, perciò la maggior parte delle organizzazioni dovrebbero già essere protette da questa vulnerabilità.

Se il servizio **Accodamento messaggi** viene arrestato, i messaggi distribuiti non saranno disponibili. Se questo servizio è disabilitato, tutti i servizi che dipendono esplicitamente da esso non vengono avviati. Inoltre, ne saranno influenzate la funzionalità **Componenti in coda COM+**, alcune funzionalità di WMI (Windows Management Instrumentation) e il servizio **Trigger Accodamento messaggi**. Questo servizio non è installato sui computer Windows Server 2003 per impostazione predefinita.

#### Accodamento messaggi per i client di livello inferiore

Il servizio **Accodamento messaggi per i client di livello inferiore** fornisce l'accesso ad Active Directory per i client Windows NT 4.0, Windows 9x e Windows 2000 che utilizzano il servizio **Accodamento messaggi** sui controller di dominio. ll servizio **Accodamento messaggi** utilizza facoltativamente i dati pubblicati in Active Directory per ottenere informazioni di routing per oggetti correlati alla protezione, ad esempio chiavi pubbliche di destinazione e code pubbliche. Installando **Accodamento messaggi** in modalità workgroup, l’accesso ad Active Directory non si verifica mai. Questo servizio è necessario soltanto sui controller di dominio di Windows Server 2003 che utilizzano il servizio **Accodamento messaggi**.

Se il servizio **Accodamento messaggi per i client di livello inferiore** viene arrestato su un controller di dominio, le versioni dei client Microsoft Accodamento messaggi precedenti a 3.0 non saranno in grado di ottenere i servizi di Active Directory nel controller di dominio specificato per la rilevabilità delle code pubbliche, il routing dei messaggi e il riconoscimento di siti. Questo servizio non è installato sui computer Windows Server 2003 per impostazione predefinita.

#### Trigger Accodamento messaggi

Il servizio **Trigger Accodamento messaggi** controlla, basandosi su regole, i messaggi in arrivo in una coda **di Accodamento messaggi** e, se le condizioni di una regola sono soddisfatte, richiama un componente COM o un programma eseguibile autonomo per elaborare il messaggio.

Il servizio **Trigger Accodamento messaggi** viene installato come parte integrante di **Accodamento messaggi**, un componente facoltativo di Windows, ed è disponibile in tutte le versioni di Windows, ad eccezione di Windows XP Home Edition.

Se il servizio **Trigger Accodamento messaggi** viene arrestato, non sarà possibile applicare il monitoraggio basato su regole, né richiamare programmi per elaborare automaticamente i messaggi. Questo servizio non è installato sui computer Windows Server 2003 per impostazione predefinita.

#### Messenger

Il servizio di sistema **Messenger** scambia messaggi in entrata o in uscita con utenti e computer, amministratori e con il servizio **Avvisi.** Questo servizio non è correlato a Windows Messenger, un servizio di messaggistica immediata gratuito disponibile attraverso MSN.

Se il servizio **Messenger** viene disattivato, sarà impossibile per il computer o gli utenti attualmente connessi inviare o ricevere notifiche. I comandi NET SEND e NET NAME smetteranno di funzionare. Questo servizio è installato ma disattivato per impostazione predefinita sui computer Windows Server 2003 Windows XP.

#### Servizio POP3 Microsoft

Il **Servizio POP3 Microsoft** offre servizi di trasferimento e recupero della posta elettronica. Gli amministratori possono utilizzare questo servizio per archiviare e gestire gli account di posta elettronica nel server della posta. Quando si installa il **Servizio POP3 Microsoft** in un server della posta, gli utenti possono connettersi a tale server e recuperare i messaggi e-mail tramite un client di posta elettronica che supporta il protocollo POP3, ad esempio Microsoft Outlook. Il **Servizio POP3 Microsoft** si combina con il **Servizio SMTP**, che consente agli utenti di inviare la posta in uscita.

Il **Servizio POP3 Microsoft** è il meccanismo che consente agli utenti di recuperare i messaggi dal server di posta elettronica. I computer del mittente e del destinatario sono connessi a Internet attraverso i rispettivi provider di servizi Internet (ISP). Quando il mittente utilizza un cliente di posta elettronica per inviare un messaggio, il **Servizio SMTP** trasferisce il messaggio all'ISP del mittente. Il messaggio viene quindi instradato su Internet e inoltrato attraverso vari server intermediari. Quando il messaggio raggiunge l'ISP del destinatario, viene collocato nella casella di posta di quest'ultimo. Quando il computer del destinatario si connette all'ISP, questo trasferisce il messaggio al client di posta elettronica del destinatario sul computer locale conformemente agli standard dei protocolli POP3.

Se il **Servizio POP3 Microsoft** viene arrestato, i servizi di trasferimento e recupero della posta elettronica smetteranno di funzionare. Questo servizio deve essere installato manualmente sui computer Windows Server 2003.

#### Provider di copie replicate software Microsoft

Il servizio **Provider di copie shadow per software MS** gestisce il software per le copie shadow di file create dal servizio **Copia shadow del volume**. Una copia shadow è una copia di un volume di un disco che rappresenta un’immagine congruente, di sola lettura, in un determinato momento, del volume in questione. Questa istantanea momentanea rimane costante e consente a un’applicazione, ad esempio un programma di backup, di copiare i dati dalla copia shadow in un nastro.

Esisto due classi generiche di copie shadow:

-   **Hardware**. Una copia shadow hardware è un mirror di due o più dischi suddivisi in volumi separati. Uno dei due volumi rimane come working set, mentre l’altro può essere montato separatamente.

-   **Software**. Una copia shadow software utilizza come schema la copia in scrittura per copiare in un’area differenziale tutti i settori di un volume che cambiano nel tempo. Quando la copia shadow viene montata, tutti i settori non modificati vengono letti dal volume originale, mentre quelli modificati vengono letti dall’area differenziale.

Le copie shadow risolvono tre problemi classici, associati al backup di dati:

-   La necessità di eseguire il backup di file aperti in modo esclusivo. L’esecuzione del backup di un file aperto rappresenta un problema, in quanto il file può essere modificato. Senza una copia shadow o un modo per sospendere l’applicazione, il risultato è spesso una copia di backup danneggiata.

-   La necessità di conservare la disponibilità del computer durante l'esecuzione della copia shadow.

-   Utilizzo degli stessi canali delle istantanee per facilitare il trasferimento di informazioni fra applicazione e strumenti di backup.

La piattaforma per le copie shadow è costituita da quanto riportato di seguito:

-   Un insieme di API per la copia shadow, che gestisce la sincronizzazione delle applicazioni. Questa sincronizzazione assicura che la copia shadow non sia danneggiata in quanto i dati delle applicazioni si trovano in uno stato la cui validità è nota. Gli API offrono le funzionalità necessarie per i provider di plug-in per le copie shadow e la coordinazione delle copie shadow su più volumi.

-   Un driver della periferica che copia i vecchi settori in un "file delle differenze" la prima volta che vengono sostituiti per la copia shadow di qualsiasi volume montato localmente. Il "file delle differenze" viene sovrapposto al volume corrente per sintetizzare il volume di copia shadow.

-   Supporto per le API di provider e sincronia nelle comunità di sviluppo del software.

Se il servizio **Provider di copie replicate software Microsoft** viene arrestato, sarà impossibile gestire le copie shadow dei volumi basate su software, il che potrebbe provocare un errore nell'utilità di backup di Windows. Questo servizio è installato per impostazione predefinita su Windows Server 2003, ma viene eseguito solo quando l'utente lo richiede.

#### MSSQL$UDDI

Il servizio **MSSQL$UDDI** viene installato insieme alla funzionalità UDDI (Universal Description, Discovery and Integration) della famiglia di sistemi operativi Windows Server 2003, che assicura le funzionalità UDDI all'interno di un'organizzazione. Insieme a questo servizio viene installata anche un'istanza del database SQL Server. Questa istanza gestisce tutti i file che comprendono database utilizzati dal servizio ed elabora le istruzioni Transact-SQL inviate dalle applicazioni client di SQL Server. Il servizio **MSSQL$UDDI** alloca con efficienza le risorse del computer fra vari utenti simultanei. Applica inoltre le regole aziendali definite nelle stored procedure e nei trigger, assicura la coerenza dei dati e impedisce problemi di logica, quali quelli causati da due utenti che tentano contemporaneamente di aggiornare gli stessi dati.

UDDI è una specifica settoriale per la descrizione e la rilevazione di servizi Web. La specifica UDDI si basa sugli standard dei protocolli SOAP (Simple Object Access Protocol), XML (Extensible Markup Language) e HTTP/S, sviluppati dal World Wide Web Consortium (W3C) e da IETF. I servizi UDDI sono servizi Web XML basati su standard, progettati per gli sviluppatori di organizzazioni, che consentono di pubblicare, rilevare, condividere e riutilizzare con efficienza i servizi Web direttamente attraverso i propri strumenti di sviluppo. Costruiti su Microsoft .NET Framework, i servizi UDDI si avvalgono della tecnologia e degli strumenti di provata efficacia di Microsoft SQL Server per fornire un meccanismo di archiviazione scalabile. I responsabili IT possono fare affidamento sul supporto dei servizi UDDI per gli schemi di categorizzazione standard e l’autenticazione Active Directory, ottenendo così un’agevole integrazione nell’ambiente dell’organizzazione.

Il servizio **MSSQL$UDDI** deve essere installato manualmente sui computer Windows Server 2003; una volta eseguita questa operazione, il tipo di avvio è configurato su **Manuale.** Se questo servizio viene arrestato, il database UDDI di SQL Server non sarà più disponibile e i client non saranno più in grado di inviare query o accedere ai dati presenti nei relativi database.

#### MSSQLServerADHelper

Il servizio **MSSQLServerADHelper** consente a Microsoft SQL Server e a SQL Server Analysis Services di pubblicare informazioni in Active Directory quando i servizi non vengono invocati con l’account di sistema locale. In ogni computer può essere eseguita una sola istanza del servizio **MSSQLServerADHelper**. Tutte le istanze di Microsoft SQL Server e Microsoft SQL Server Analysis Services lo utilizzano secondo necessità.

**MSSQLServerADHelper** non è un servizio server e non risponde alle richieste del client. Il servizio non utilizza la porta UDP o TCP.

Non è possibile arrestare il servizio **MSSQLServerADHelper.** Questo servizio viene avviato dinamicamente da una istanza di SQL Server o Analysis Manager, quando è necessario, e si arresta una volta completate le operazioni cui è preposto. Questo servizio deve essere sempre eseguito dall'account di sistema locale; non avviarlo manualmente dalla console. Se questo servizio viene disattivato, ne potrebbe essere influenzata la capacità di aggiungere, aggiornare o eliminare oggetti di Active Directory relativi a SQL Server. Questo servizio deve essere installato manualmente sui computer Windows Server 2003. Quando installato, il tipo di avvio è impostato su **Manuale**.

#### Servizio per il supporto di .NET Framework

Il **servizio per il supporto di .NET Framework** avvisa i client che hanno effettuato la sottoscrizione ogni volta che uno dei processi specificati inizializza il servizio runtime client. Il **servizio per il supporto di .NET Framework** mette a disposizione un ambiente di runtime denominato Common Language Runtime (CLR), che gestisce l’esecuzione di codice e fornisce servizi che semplificano i processi di sviluppo. Compilatori e strumenti espongono le funzionalità del runtime e consentono di scrivere codice che beneficia di questo ambiente con esecuzione gestita. CLR consente di progettare componenti e applicazioni i cui oggetti interagiscono fra i linguaggi. Oggetti scritti in linguaggi diversi possono comunicare gli uni con gli altri e il loro funzionamento può essere integrato strettamente. Questo servizio fa di norma parte dell'ambiente di sviluppo Visual Studio.NET e non sarà presente o attivo a meno che non lo si installi manualmente.

Se il **servizio per il supporto di .NET Framework** viene arrestato o disattivato, l'utente non riceverà una notifica quando un'applicazione .NET avvia CLR.

#### Accesso rete

Il servizio **Accesso rete** mantiene un canale protetto tra il computer e il controller di dominio per l'autenticazione di utenti e servizi. Passa le credenziali dell'utente a un controller di dominio attraverso il canale protetto e restituisce gli identificatori di protezione del dominio e i diritti per l'utente, processo generalmente denominato "autenticazione pass-through". Il servizio è installato su tutti i computer Windows Server 2003 e Windows XP e il tipo di avvio è impostato su Manuale. Dopo che il computer viene aggiunto a un dominio, il servizio si avvia automaticamente.

Nelle famiglie di sistemi operativi Windows 2000 Server e Windows Server 2003, il servizio **Accesso rete** pubblica i record delle risorse dei servizi nel DNS e utilizza il DNS per risolvere i nomi agli indirizzi IP dei controller di dominio. Il servizio implementa inoltre il protocollo di replica su RPC (Remote Procedure Call) per sincronizzare i controller di dominio primari (PDC, Primary Domain Controller) e di backup (BDC, Backup Domain Controller) con Windows NT 4.0.

Se il servizio **Accesso rete** viene arrestato, il computer non potrà autenticare utenti e servizi e il controller di dominio non potrà registrare i record DNS. In particolare, potrebbero venire negate le richieste di autenticazione NTLM e i controller di dominio potrebbero non essere rilevati dai computer client.

#### Condivisione desktop remoto di NetMeeting

Il servizio **Condivisione desktop remoto di NetMeeting** consente agli utenti autorizzati di accedere in modo remoto al computer desktop Windows tramite l'applicazione Microsoft NetMeeting da un altro PC in una rete Intranet. Per impostazione predefinita, questo servizio è installato e disattivato. Deve essere esplicitamente attivato dall'utente tramite NetMeeting e può essere disattivato in NetMeeting o interrotto dall'icona nella barra delle applicazioni di Windows.

Se il servizio **Condivisione desktop remoto di NetMeeting** viene arrestato o disattivato, il driver video di NetMeeting viene scaricato e il computer non sarà in grado di fornire l'accesso remoto al desktop.

#### Connessioni di rete

Il servizio **Connessioni di rete** è installato per impostazione predefinita sui computer Windows Server 2003 Windows XP. Questo servizio gestisce gli oggetti nella cartella **Connessioni di rete**, da cui è possibile visualizzare sia le connessioni di rete sia quelle remote. Questo servizio è responsabile della configurazione della rete client e visualizza lo stato della connessione nell'area di notifica sulla barra delle applicazioni. Attraverso questo servizio è inoltre possibile visualizzare e configurare le impostazioni di interfaccia di rete.

Il servizio **Connessioni di rete** si avvia automaticamente quando il tipo di avvio è Manuale e viene richiamata l’interfaccia Connessioni di rete. Se questo servizio viene arrestato, la configurazione del lato client delle connessioni alla rete LAN, VPN e la connessione remota non saranno disponibili. Se questo servizio viene disattivato, può verificarsi quanto descritto di seguito:

-   Le connessioni non saranno visualizzate nella cartella **Connessioni di rete**, pertanto l’accesso mediante connessione remota è impedito e non sarà possibile configurare le impostazioni della LAN.

-   Gli altri servizi che utilizzano Connessioni di rete per controllare la presenza di criteri di gruppo dipendenti dall’indirizzo di rete non funzioneranno correttamente.

-   Gli eventi riguardanti la connessione e la disconnessione di supporti non verranno ricevuti.

-   La condivisione della connessione Internet non funzionerà correttamente.

-   Non sarà possibile configurare le connessioni in ingresso, le impostazioni delle periferiche senza fili o la rete domestica.

-   Non verranno create nuove connessioni.

-   Qualsiasi servizio che dipende esplicitamente da questo non verrà avviato.

#### DDE di rete

Il servizio **DDE di rete** fornisce il trasporto di rete e la protezione per lo scambio dinamico dei dati (DDE, Dynamic Data Exchange) per i programmi in esecuzione nello stesso computer o in computer diversi. È possibile creare "condivisioni" DDE di rete a livello di programmazione o utilizzando Ddeshare.exe, e renderle visibili ad altre applicazioni e computer. Di solito l’utente che crea la condivisione crea ed esegue un processo server per gestire le richieste in ingresso da processi client e/o applicazioni in esecuzione nello stesso computer o remotamente. Una volta connessi, questi processi possono scambiare qualunque tipo di dati su un trasporto di rete protetto.

Per impostazione predefinita, questo servizio è installato ma disattivato. Per utilizzare la funzionalità DDE di rete, è necessario impostare il tipo di avvio del servizio su Manuale, in modo che questo venga avviato soltanto quando viene richiamato da un'applicazione che utilizza DDE di rete, come Clipbrd.exe o Ddeshare.exe.

Se il servizio **DDE di rete** viene arrestato, il trasporto e la protezione DDE non saranno disponibili. Se il servizio viene disattivato, si verificherà un timeout di tutte le applicazioni che dipendono da esso, quando tentano di avviarlo. Se un’applicazione presente in un computer remoto tenta di avviare il **servizio DDE** di rete in un altro computer, il computer remoto non risulterà visibile nella rete.

#### DDE DSDM di rete

Il servizio **DDE DSDM di rete** gestisce le condivisioni di rete DDE. Questo servizio viene utilizzato esclusivamente dal servizio **DDE di rete** per gestire le conversazioni DDE condivise. È possibile creare e considerare attendibili condivisioni DDE utilizzando Ddeshare.exe per consentire ai computer e alle applicazioni remote di connettersi e condividere dati. Il servizio **DDE DSDM di rete** aggiorna un database delle condivisioni DDE, contenente informazioni sulle condivisioni attendibili. Per ogni richiesta di connessione proveniente o diretta a un’applicazione, il servizio inoltra una query al database e convalida le impostazioni di protezione per determinare se rispondere positivamente alla richiesta.

Il servizio **DDE DSDM di rete** è installato ma disattivato per impostazione predefinita. Per utilizzare la funzionalità DDE di rete, è necessario impostare il tipo di avvio del servizio su Manuale, in modo che questo venga avviato soltanto quando viene richiamato da un'applicazione che utilizza DDE di rete. Se il servizio **DDE DSDM di rete** viene arrestato, le condivisioni di rete DDE non saranno disponibili. Se il servizio viene disattivato, si verificherà un timeout di tutte le applicazioni che dipendono da esso, quando tentano di avviarlo.

#### NLA (Network Location Awareness)

Il servizio **NLA (Network Location Awareness)** è in grado di raccogliere e archiviare informazioni relative alla configurazione di rete, quali le modifiche di indirizzi IP e nomi di domini e informazioni relative alla modifica dei percorsi, quindi notifica immediatamente le modifiche alle applicazioni compatibili perché possano riconfigurarsi per utilizzare la connessione di rete corrente.

Il servizio **NLA (Network Location Awareness)** è predefinito in Windows XP. Anche se si configura questo servizio con un tipo di avvio Manuale, verrà comunque avviato da servizi dipendenti. Se viene arrestato, la funzionalità Network Location Awareness non sarà disponibile.

#### Servizio Provisioning di rete

Il **Servizio Provisioning di rete** consente di scaricare e gestire file di configurazione XML da servizi provisioning di rete come Microsoft Wireless Provisioning Services (WPS), che attiva il provisioning automatico di rete per i provider di servizi Internet e per le reti private. Questo servizio opera unitamente a **Configurazione automatica reti senza fili** per fornire supporto relativamente agli standard della protezione senza fili più recenti.

Se il **Servizio Provisioning di rete** viene arrestato o disattivato, potrebbe non essere possibile configurare e utilizzare l'interfaccia di rete senza fili, anche se l'ambiente di rete non si serve di WPS o di un servizio equivalente.

#### NNTP (Network News Transfer Protocol)

Il sistema di servizio **NNTP** consente ai computer Windows Server 2003 di svolgere la funzione di server delle news. I computer client possono utilizzare un'applicazione client delle news, ad esempio il client di messaggistica Microsoft Outlook Express, per recuperare i newsgroup dal server e leggere le intestazioni o il corpo degli articoli in ogni newsgroup. I client possono quindi rispedirli al server.

NNTP è uno standard Internet; la versione inclusa in Windows Server 2003 non supporta gli inserimenti, in cui due nuovi server si replicano a vicenda i contenuti. Tuttavia, la versione inclusa in Exchange 2000 dispone di questa funzionalità. Per impostazione predefinita, questo servizio non è installato o abilitato. Può essere installato soltanto insieme a IIS.

Se il servizio **NNTP (Network News Transfer Protocol)** viene arrestato, i computer client non saranno in grado di connettersi e leggere o recuperare la posta.

#### NTLM Security Support Provider

Il servizio **NTLM Security Support Provider** fornisce la protezione ai programmi RPC che utilizzano trasporti diversi dalle named pipe e consente agli utenti di accedere alla rete utilizzando il protocollo di autenticazione NTLM, che autentica i client che non si servono del protocollo Kerberos versione 5.

Il protocollo di autenticazione NTLM In attesa/Risposta di Windows NT viene utilizzato in reti che includono sistemi che eseguono versioni del sistema operativo Windows NT e in sistemi autonomi. NTLM è l’acronimo di “Windows NT LAN Manager”, un nome scelto per distinguere questo protocollo basato sullo schema avanzato In attesa/Risposta dal suo più debole predecessore LAN Manager (LM).

Windows 2000 utilizzava il protocollo di autenticazione Kerberos versione 5, che garantisce una protezione migliore alle reti di computer rispetto a NTLM. Sebbene Kerberos sia il protocollo di autenticazione prescelto per le reti Windows 2000 e Windows Server 2003, NTLM è ancora supportato e deve essere utilizzato per l'autenticazione di rete se questa contiene computer che eseguono versioni di Windows NT, Windows 98 o Windows Millennium Edition. NTLM è necessario anche per l'autenticazione di accesso sui computer autonomi.

Le credenziali NTLM si basano su dati ottenuti durante il processo di accesso interattivo e sono costituite da un nome di dominio, un nome utente e un hash unidirezionale della password utente. NTLM utilizza un protocollo In attesa/risposta crittografato per autenticare un utente senza inviarne la password in rete. Il computer che richiede l’autenticazione deve invece eseguire un calcolo che provi di avere accesso alle credenziali NTLM protette.

L’autenticazione NTLM interattiva in una rete di solito coinvolge di solito due computer: un computer client, in cui è l’utente a richiedere l’autenticazione, e un controller di dominio, in cui vengono conservate le informazioni relative alla password dell’utente. Nell’autenticazione non interattiva, che può essere necessaria per consentire a un utente già connesso di accedere a una risorsa quale un’applicazione server, di solito sono coinvolti tre computer: un client, un server e un controller di dominio che autentica i calcoli da parte del server.

Il servizio **NTLM Security Support Provider** è installato ed eseguito per impostazione predefinita su tutti i computer Windows XP e Windows Server 2003. Se questo servizio viene arrestato o disattivato, i client che utilizzano il protocollo di autenticazione NTLM non potranno accedere alle risorse di rete. Microsoft Operations Manager (MOM) si affida a questo servizio.

#### Avvisi e registri di prestazioni

Il servizio **Avvisi e registri di prestazioni** raccoglie i dati relativi alle prestazioni dal computer locale o da computer remoti sulla base di parametri di pianificazione preconfigurati e, successivamente, scrive tali dati in un registro o attiva un avviso. Il servizio consente di avviare e interrompere ciascuna raccolta di dati sulle prestazioni dotata di nome in base alle informazioni contenute nell'impostazione della raccolta denominata dei registri. Questo servizio viene eseguito se viene pianificata almeno una raccolta. Tuttavia, è installato per impostazione predefinita su Windows XP e Windows Server 2003.

Se il servizio **Avvisi e registri di prestazioni** viene arrestato o disattivato, non saranno raccolte informazioni sulle prestazioni. Le raccolte di dati correntemente in esecuzione verranno inoltre terminate e le raccolte pianificate in futuro non verranno eseguite.

#### Plug and Play

Il servizio **Plug and Play** consente a un computer di riconoscere le modifiche apportate all’hardware e di adattarvisi con un intervento minimo, o addirittura nullo, da parte dell'utente. Questo servizio consente di aggiungere e rimuovere periferiche senza essere esperti di hardware e senza dover configurare manualmente l'hardware o il sistema operativo. Collegando ad esempio una tastiera USB, il servizio **Plug and Play** rileverà la nuova periferica, individuerà un driver per essa e la installerà. È in alternativa possibile inserire un computer portatile nell’alloggiamento di espansione e utilizzare la scheda Ethernet di quest’ultimo per connettersi alla rete senza modificare la configurazione. Sarà in seguito possibile estrarre il computer dall’alloggiamento di espansione e utilizzare un modem per connettersi nuovamente alla rete, senza apportare modifiche manuali alla configurazione.

Il servizio **Plug and Play** è installato e configurato per essere eseguito automaticamente su Windows Server 2003 e su Windows XP. Non è possibile disabilitare il servizio attraverso lo snap-in dei servizi, dato l’impatto che la disattivazione avrebbe sulla stabilità del sistema operativo. Se questo servizio viene arrestato mediante lo strumento per la risoluzione dei problemi MSCONFIG, l’interfaccia Gestione periferiche risulta vuota e non viene visualizzata nessuna periferica hardware.

#### Numero di serie per dispositivi multimediali portatili

Il servizio **Numero di serie per dispositivi multimediali portatili** recupera il numero di serie del lettore di musica portatile collegato al computer. Il servizio consente a Gestione periferiche multimediali Windows di acquisire il numero di serie da periferiche musicali portatili, in modo che il contenuto multimediale possa essere copiato in tutta sicurezza in queste periferiche. Senza il numero di serie non è possibile associare il contenuto a una periferica specifica, il che potrebbe impedire che contenuti protetti vengano trasferiti sulla periferica.

Per identificare in modo univoco i supporti portatili, molti produttori di supporti di archiviazione hanno adottato un numero di serie, memorizzato nell’area di archiviazione non volatile. La specifica della revisione 1.3 CompactFlash, di CompactFlash Association (CFA) prevede che queste schede abbiano un numero di serie univoco. Anche altri tipi di supporti di archiviazione rimovibili dispongono di numeri di serie univoci memorizzati al loro interno.

Perché un lettore o adattatore per supporti portatili sia compatibile con Windows Media, deve consentire alle applicazioni di recuperare i numeri di serie dei supporti.

Il servizio **Numero di serie per dispositivi multimediali portatili** è installato per impostazione predefinita su Windows XP e Windows Server 2003. Il suo tipo di avvio è configurato su **Manuale** e viene avviato su richiesta di WMDM. Se il servizio viene arrestato o disattivato, potrebbe non essere possibile trasferire alla periferica contenuti protetti e il numero di serie potrebbe non essere recuperato da periferiche che utilizzano supporti portatili.

#### Server di stampa per Macintosh

Il servizio **Server di stampa per Macintosh** consente ai client Apple Macintosh di inviare le stampe a uno spooler di stampa che si trova in un computer dotato di Windows Server 2003. Questo servizio consente inoltre a Windows Server 2003 Enterprise Edition di comunicare con una periferica di stampa utilizzando il protocollo AppleTalk. Questo servizio non è installato per impostazione predefinita.

Se il servizio **Server di stampa per Macintosh** viene arrestato, i client Macintosh AppleTalk non potranno inviare i processi di stampa a uno spooler di stampa basato su Windows Server 2003.

#### Spooler di stampa

Il servizio **Spooler di stampa** gestisce tutte le code di stampa locali e della rete e controlla tutti i processi di stampa. Lo spooler di stampa è il centro del sottosistema di stampa di Windows e comunica con i driver di stampante e i componenti di input/output (I/O), ad esempio la porta USB e l'insieme di protocolli TCP/IP. Questo servizio è installato e attivato per impostazione predefinita sui computer Windows XP e Windows Server 2003.

Se il servizio **Spooler di stampa** viene arrestato, non sarà possibile stampare o inviare fax dal computer locale. Quando il servizio **Spooler di stampa** viene disattivato su un server che esegue Servizi terminal, l'hive del Registro di sistema crescerà lentamente fino a riempire il volume di sistema causando l'arresto del server. Questo problema è causato dal fatto che quando nuovi client accedono al server attraverso i Servizi terminal, il sistema tenta di eseguire automaticamente il mapping della stampante locale del client a una porta stampante sul server e inserisce tale mapping nel Registro di sistema. Tuttavia, il servizio **Spooler di stampa** dovrebbe eliminare ogni registrazione quando l'utente conclude la sessione, ma se il servizio non è in esecuzione, le registrazioni inutilizzate non verranno mai eliminate.

Inoltre, la funzionalità Printer Pruner di Active Directory fa affidamento sul servizio **Spooler di stampa**. Per utilizzare Printer Pruner all'interno dell'organizzazione ed eseguire lo scavenging delle code orfane su una base non gestita, ogni sito dell'organizzazione deve disporre di almeno un controller di dominio che esegue il servizio **Spooler di stampa**. Se si configura il** **servizio su **Disabilitato** o **Manuale**, questo non si avvierà automaticamente quando vengono inviate le richieste dei processi di stampa.

#### Archiviazione protetta

Il servizio **Archiviazione protetta** protegge l’archivio delle informazioni riservate, ad esempio le chiavi private, impedendo l’accesso da parte di servizi, processi o utenti non autorizzati. Il servizio fornisce un insieme di librerie software che consentono alle applicazioni di recuperare informazioni relative alla protezione e di altro tipo da un percorso di archiviazione personale, nascondendo l’implementazione e i dettagli dell’archivio.

Il percorso di archiviazione fornito in questo servizio è protetto dalle modifiche. Il servizio **Archiviazione protetta** impiega le funzioni di hash crittografico HMAC (Hash-Based Message Authentication Code) e SHA1 (Secure Hash Algorithm 1) per crittografare la chiave principale dell’utente. Per questo componente non è necessaria alcuna configurazione.

Il servizio **Archiviazione Protetta** è stato originariamente introdotto con Windows 2000. In Windows XP e Windows Server 2003, questo servizio  è stato sostituito da DPAPI (Data Protection API), attualmente il servizio preferito per l’archiviazione protetta. A differenza di DPAPI, l’interfaccia del servizio **Archiviazione protetta** non viene esposta pubblicamente.

Se il servizio **Archiviazione protetta** viene disabilitato, non sarà possibile accedere alle chiavi private, il **Servizio certificati di Windows** non funzionerà, S/MIME (Secure Multipurpose Internet Mail Extensions) e SSL non funzioneranno e non sarà supportato l'accesso tramite smart card.

#### Servizio QoS RSVP

Qualità di Servizio (QoS) è uno standard di settore sviluppato per un più efficiente utilizzo delle risorse di rete. Consente ai client e ai server di distinguere tra diversi tipi di dati e di definire le priorità relativamente al traffico di rete end-to-end. IETF (Internet Engineering Task Force) ha giocato un ruolo centrale nell'assicurare che gli standard QoS consentissero a tutte le periferiche di rete interessate di sfruttare la connessione end-to-end abilitata al QoS. Qualità di Servizio mette a disposizione delle applicazioni (o degli amministratori di rete) un metodo per definire e gestire le risorse di rete, come la larghezza di banda disponibile e la latenza, sia sui computer locali sia sulle periferiche all'interno della rete.

Il **Servizio** **QoS RSVP** dispone del supporto QoS di Windows. È installato per impostazione predefinita su Windows XP, ma non sui computer Windows Server 2003. Quando installato, il tipo di avvio è impostato su **Manuale**. Se questo servizio viene disattivato o disinstallato, il computer non potrà servirsi delle connessioni QoS o eseguire richieste RSVP per la larghezza di banda controllata da QoS.

#### Auto Connection Manager di Accesso remoto

Il servizio **Auto Connection Manager di Accesso remoto** rileva i tentativi non riusciti di connessione a una rete remota o a un computer remoto, quindi mette a disposizione metodi di connessione alternativi. Quando un programma non riesce a fare riferimento a un nome o indirizzo DNS o NetBIOS remoto o l’accesso di rete non è disponibile, viene visualizzata una finestra di dialogo per consentire di stabilire una connessione remota o VPN al computer remoto.

A fini di assistenza, il servizio **Auto Connection Manager di Accesso remoto** gestisce un database locale delle connessioni utilizzate in passato per raggiungere computer o condivisioni denominate. Quando il servizio rileva un tentativo non riuscito di raggiungere un computer o condivisione remota, viene offerta la possibilità di comporre il numero utilizzato l’ultima volta per connettersi alla periferica remota. Questo servizio è installato per impostazione predefinita sui computer Windows XP e Windows Server 2003, ma il suo tipo di avvio è configurato su **Manuale**. Viene avviato automaticamente secondo necessità. Se il servizio **Auto Connection Manager di Accesso remoto** viene disattivato, sarà necessario stabilire manualmente le connessioni ai computer remoti quando si desidera accedervi.

#### Connection Manager di Accesso remoto

Il servizio di sistema **Connection Manager di Accesso remoto** gestisce le connessioni remote e VPN del computer a Internet o ad altre reti remote. Facendo doppio clic su una connessione nella cartella **Connessioni di rete** e scegliendo il pulsante **Connetti**, il servizio **Connection Manager di Accesso remoto** compone il numero della connessione o invia una richiesta di connessione VPN e gestisce le successive negoziazioni con il server di Accesso remoto al fine di stabilire la connessione.

Il servizio **Connection manager di Accesso remoto** verrà scaricato automaticamente quando non sono presenti richieste in sospeso. La cartella **Connessioni di rete** richiama questo servizio per enumerare l’insieme di connessioni e visualizzare lo stato di ciascuna. Sebbene il suo stato predefinito di avvio sia configurato su **Manuale**, questo servizio verrà avviato se sono presenti una o più connessioni remote o VPN nella cartella **Connessioni di rete.**

Se il servizio **Connection manager di Accesso remoto** viene arrestato o disattivato, il computer non sarà in grado di stabilire connessioni remote o VPN a una rete remota o di accettare richieste di connessione in ingresso. Inoltre, la cartella **Connessioni di rete** non visualizzerà le connessioni remote o VPN e il pannello di controllo delle opzioni Internet non consentirà agli utenti di configurare le opzioni relative a tali connessioni.

#### Servizio Amministrazione remota

Il **servizio Amministrazione remota** è in grado di eseguire, al riavvio del server, le seguenti attività di amministrazione remota:

-   Aumento del numero di avvii del server.

-   Generazione di un certificato autofirmato.

-   Attivazione di un avviso, nel caso in cui la data e l'ora non siano state impostate sul server.

-   Attivazione di un avviso, nel caso in cui la funzionalità di avviso di posta elettronica non sia stata configurata.

Il **servizio Amministrazione remota** inizia a eseguire le attività corrette quando ne riceve richiesta da **Gestione server remoto** attraverso un’interfaccia COM. Il servizio utilizza l’account di sistema locale e le richieste all’interfaccia COM vengono accettate solo dai client che si servono dell’account di sistema locale o di amministrazione.

Se il **servizio di Amministrazione remota** è configurato su **Manuale**, si avvierà alla chiamata da parte del servizio **Gestione server remoto**. Sarà possibile arrestarlo in seguito senza compromettere la funzionalità del server. Per impostazione predefinita, questo servizio è installato e configurato per avviarsi automaticamente sui computer Windows Server 2003.

Se il **servizio Amministrazione remota** viene arrestato, è possibile che alcune funzioni degli strumenti di amministrazione remota non funzionino correttamente, ad esempio Interfaccia Web per amministrazione remota.

#### Gestione sessione di assistenza mediante desktop remoto

Il servizio **Gestione sessione di assistenza mediante desktop remoto** gestisce e controlla la funzionalità di assistenza remota disponibile nell’applicazione Guida in linea e supporto tecnico (helpctr.exe). È installato per impostazione predefinita su Windows XP e Windows Server 2003, ma viene avviato soltanto quando viene effettuata o ricevuta una richiesta di assistenza remota.

Se il servizio **Gestione sessione di assistenza mediante desktop remoto** viene arrestato, l’assistenza remota non sarà disponibile e non sarà possibile richiedere supporto.

#### Installazione remota

Il servizio **Installazione remota** consente di installare Windows 2000, Windows XP e Windows Server 2003 nei computer client PXE (Pre-Boot Execution Environment) con avvio remoto attivato. Il servizio BINL (Boot Information Negotiation Layer), il componente principale di Servizi di installazione remota (RIS, Remote Installation Services), risponde ai client PXE, controlla la convalida dei client in Active Directory e permette il passaggio delle informazioni tra i client e il server. Il servizio BINL viene installato quando si aggiunge il componente RIS da Installazione componenti di Windows o si seleziona tale servizio durante l'installazione iniziale del sistema operativo.

RIS è una funzione di distribuzione di Windows inclusa nella famiglia di sistemi operativi Windows Server 2003. Con RIS sono supportate le installazioni del sistema operativo su richiesta, basate su immagini o su script, attraverso una connessione di rete fra un server RIS e un computer client. RIS è progettato per semplificare la distribuzione di sistemi operativi e applicazioni e per migliorare la capacità di recupero da errori.

È possibile utilizzare RIS in molti modi, fra cui:

-   Fornire un sistema operativo agli utenti su richiesta. È possibile utilizzare RIS per creare immagini di installazione automatizzate dei sistemi operativi della famiglia Windows Server 2003, Windows XP e Windows 2000. Quando un utente avvia un computer client, anche se tale computer non contiene un sistema operativo, il server RIS potrà rispondere installandone uno attraverso la rete, senza l’ausilio di CD. Perché questa funzionalità sia supportata, i client devono utilizzare PXE attraverso la scheda di rete.

-   Fornire immagini del sistema operativo con impostazioni e applicazioni specifiche, ad esempio un’immagine conforme a uno standard di desktop aziendale. A un determinato gruppo di utenti può essere offerta un’immagine o immagini che l’amministratore ha destinato al gruppo.

Il servizio **Installazione remota** non è installato per impostazione predefinita. Se si installa il servizio e in seguito lo si arresta, i computer client con abilitazione PXE non potranno installare Windows in modalità remota o utilizzare strumenti basati su RIS dal computer.

#### RPC (Remote Procedure Call)

Il servizio Microsoft **RPC (Remote Procedure Call)** è un meccanismo di comunicazione tra processi che consente lo scambio dei dati e la chiamata di funzionalità contenute in processi diversi nello stesso computer, nella rete locale o su Internet. Il servizio **RPC** svolge la funzione di agente di mapping degli endpoint RPC e di Gestione controllo servizi dei componenti COM. L'avvio corretto di più di 50 servizi dipende da RPC.

Non è possibile arrestare o disattivare il servizio **RPC (Remote Procedure Call**. Se questo** **servizio non è disponibile, il sistema operativo non verrà caricato.

#### RPC Locator

Il servizio **RPC Locator** consente ai client RPC che utilizzano la famiglia di API RpcNs\* di rilevare i server RPC e gestire il database del servizio dei nomi RPC. Questo servizio è disattivato per impostazione predefinita, e non è stato utilizzato da molte applicazioni pubblicate dopo il rilascio di Windows 95.

Per ulteriori informazioni sulla famiglia di API RpcNs, vedere il kit SDK in MSDN Library, alla pagina delle [risorse Web](http://www.microsoft.com/windows/reskits/webresources), all’indirizzo www.microsoft.com/windows/reskits/webresources.

Se il servizio **RPC Locator** viene arrestato o disattivato, i client RPC che devono localizzare i servizi RPC su altri computer potrebbero non riuscire a individuare i server o potrebbero non avviarsi. I client RPC che si affidano alle API RpcNs\* dallo stesso computer potrebbero non essere in grado di trovare i server RPC che supportano una determinata interfaccia. Se il servizio viene arrestato o disattivato su un controller di dominio, quest'ultimo e i client RPC che utilizzano le API RpcNs\* potrebbero subire interruzioni del servizio quando tentano di individuare i client. Le API RpcNs\* non vengono utilizzate internamente in Windows; sono necessarie solo per l’avvio del servizio qualora lo richiedano applicazioni di terze parti.

#### Servizio Registro di sistema remoto

Il **Servizio Registro di sistema remoto** consente agli utenti remoti che dispongono delle autorizzazioni necessarie di modificare le impostazioni del Registro di sistema nel controller di dominio Questo servizio è installato ed eseguito automaticamente per impostazione predefinita sui computer Windows XP e Windows Server 2003. Tuttavia, la configurazione predefinita del servizio consente soltanto agli utenti dei gruppi Administrators e Backup Operators di accedere al Registro di sistema in modalità remota. Questo servizio è necessario per l'utilità MBSA (Microsoft Baseline Security Analyzer). MBSA è uno strumento che consente di verificare quali patch sono installate in ciascun server all'interno dell'organizzazione.

Se il **Servizio Registro di sistema remoto** viene arrestato, sarà possibile modificare solo il Registro di sistema sul computer locale. Se questo servizio viene disattivato, tutti i servizi che dipendono esplicitamente da esso non verranno avviati ma ciò non influenzerà le operazioni del Registro di sistema sul computer locale. Tuttavia, gli altri computer o periferiche non saranno più in grado di connettersi al Registro di sistema del computer locale.

#### Gestione server remoto

Il servizio **Gestione server remoto** fornisce le seguenti funzionalità:

-   Contiene le informazioni di avviso di Amministrazione remota.

-   Fornisce un’interfaccia per attivare, cancellare ed enumerare gli avvisi di Amministrazione remota.

-   Fornisce un’interfaccia per eseguire le attività di Amministrazione remota.

Per impostazione predefinita, il servizio **Gestione server remoto** è installato e impostato per avviarsi automaticamente sui computer che eseguono Windows Server 2003. Il servizio agisce da provider di istanze di Strumentazione gestione Windows per gli oggetti avvisi di Amministrazione remota e da provider di metodi per le attività di Amministrazione remota. Il servizio viene eseguito nell’account di sistema locale e le richieste all’interfaccia COM vengono accettate solo dai client in esecuzione con l’account di sistema locale o di amministrazione.

Se il servizio **Gestione server remoto** è configurato su **Manuale**, si avvia alla ricezione della successiva richiesta di attività o avvisi di Amministrazione remota. Se il servizio viene arrestato, si riavvia all’accesso all’interfaccia Web di amministrazione remota. Se questo servizio è disabilitato, tutti i servizi che dipendono esplicitamente da esso non vengono avviati. Inoltre,  le informazioni relative agli avvisi di Amministrazione remota correnti andranno perse.

#### Monitor server remoto

Il servizio **Monitor server remoto** effettua il monitoraggio delle risorse critiche del computer e gestisce l'hardware del watchdog timer facoltativo nei server gestiti in modo remoto.

Se il servizio **Monitor server remoto** viene arrestato, il monitoraggio delle risorse critiche del computer verrà sospeso e il watchdog timer hardware verrà arrestato.

#### Servizio di notifica archiviazione remota

Il **Servizio di notifica archiviazione remota** avvisa l'utente quando un programma tenta di leggere o scrivere su file che sono disponibili solo da supporti di archiviazione secondari. Data la notevole quantità di tempo necessaria per accedere a un file spostato su nastro, Archiviazione remota invia una notifica quando viene effettuato un tentativo di leggere un file spostato. Inoltre, il servizio consente all'utente di annullare la richiesta invece di attendere.

Per impostazione predefinita, il servizio di **notifica archiviazione remota** non è installato su Windows XP o Windows Server 2003. Se questo servizio viene arrestato, non verranno ricevute ulteriori notifiche quando si tenta di aprire file non in linea e non sarà possibile annullare operazioni che riguardano file non in linea.

#### Server di archiviazione remota

Il servizio **Server di archiviazione remota** archivia i file utilizzati con minore frequenza su supporti di archiviazione secondari. Questo servizio consente al sottosistema di Windows Archiviazione remota di avvisare l'utente quando si accede a un file non in linea.

Archiviazione remota è un’applicazione per la gestione dell’archiviazione di tipo gerarchico, che sposta i dati da un archivio di livello superiore a uno di livello inferiore. L’archivio di livello superiore è in genere l’archivio locale: i dati ai quali si accede di frequente vengono archiviati localmente in dischi ad alte prestazioni. L’archivio di livello inferiore è in genere l’archivio remoto: i dati ai quali si accede con minore frequenza vengono archiviati in supporti meno costosi finché non sono di nuovo necessari. La gestione gerarchica dell’archiviazione riduce i costi derivanti dall’archiviazione di grandi quantità di dati, assicurandone nel contempo l’accessibilità.

Il servizio **Server di archiviazione remota** è parte del componente di Windows Archiviazione remota, che deve essere installato manualmente. Una volta installato, il servizio è impostato per essere eseguito automaticamente. Se questo servizio viene arrestato, i file non potranno essere spostati o recuperati da supporti di archiviazione secondari.

#### Archivi rimovibili

Il servizio **Archivi rimovibili** gestisce e cataloga i supporti rimovibili e gestisce il funzionamento delle periferiche rimovibili automatiche. Questo servizio gestisce un catalogo di informazioni di identificazione per i supporti rimovibili utilizzati dal computer, inclusi nastri e CD. Se il computer dispone anche di periferiche automatiche per la gestione di supporti rimovibili, come un autoloader a nastro o un jukebox di CD, il servizio **Archivi rimovibili** automatizza inoltre le funzioni di montaggio, smontaggio ed espulsione dei supporti. In alcune applicazioni, come Backup e Archivio remoto, questo servizio viene utilizzato per gestire la catalogazione e l'automatizzazione dei supporti. In sostanza, questo servizio etichetta e registra i supporti e controlla le unità di librerie, gli slot e le porte. Fornisce inoltre operazioni di pulizia delle unità.

Il servizio **Archivi rimovibili** è installato per impostazione predefinita in Windows Server 2003 e Windows XP. Per impostazione predefinita, questo servizio viene eseguito solo quando viene richiesto l'accesso ad archivi rimovibili da un programma sul computer locale. Se questo servizio viene arrestato, l'esecuzione delle applicazioni dipendenti da Archivi rimovibili, quali Backup e Archiviazione remota, risulterà più lenta. In assenza di elementi da elaborare, il servizio **Archivi rimovibili** smetterà di funzionare. Se al computer non è collegata alcuna periferica automatica, il servizio verrà eseguito solo quando utilizzato dalle applicazioni, pertanto non sussiste la necessità di arrestare il servizio. Se avviato in tali circostanze, in Gestione archivi rimovibili insorge spesso l'esigenza di eseguire un inventario del contenuto completo degli autoloader e dei jukebox collegati, il che implica il montaggio di ciascun supporto in un'unità.

#### Provider Gruppo di criteri risultante

Il servizio **Provider Gruppo di criteri risultante** consente di connettersi a un controller di dominio Windows Server 2003, di accedere al database WMI relativo a tale computer e di simulare lo strumento Gruppo di criteri risultante (RSoP) per le impostazioni dei criteri di gruppo. Le impostazioni dei criteri sono stabilite per un utente o computer contenuto in Active Directory (modalità pianificazione).

Il servizio **Provider Gruppo di criteri risultante** è installato per impostazione predefinita sui computer Windows Server 2003, ma il suo tipo di avvio è configurato su **Manuale.** Se questo servizio viene arrestato su un controller di dominio, la simulazione della modalità di pianificazione del Gruppo di criteri risultante non sarà disponibile. RSoP deve essere eseguito solo sui controller di dominio; per i server membri e le workstation non è necessario eseguire questo servizio per utilizzare la funzionalità.

#### Routing e Accesso remoto

Il servizio **Routing e Accesso remoto** assicura servizi di routing multiprotocollo LAN a LAN, LAN a WAN, VPN e NAT. Questo servizio include inoltre servizi di accesso basati su connessioni remote e VPN.

Il servizio **Routing e Accesso remoto** sostituisce le funzioni del servizio Routing e Accesso remoto (RRAS) e del Servizio di Accesso remoto (RAS) di Windows NT 4.0. **Routing e Accesso remoto** è un servizio unico integrato che termina le connessioni provenienti da client remoti o VPN oppure che fornisce il routing IP, IPX e servizi per Macintosh. Questo servizio consente al server di fungere da server di accesso remoto, server VPN, gateway o router di filiale.

Dal punto di vista del routing, il servizio **Routing e Accesso remoto** supporta i protocolli OSPF (Open Shortest Path First) e RIP (Routing Information Protocol) e controlla le tabelle di routing relative al modulo di inoltro dello stack TCP/IP.

Il servizio **Routing e Accesso remoto** è installato per impostazione predefinita sui computer Windows Server 2003. È disattivato per impostazione predefinita. Se il servizio viene arrestato, le connessioni RAS, VPN e su richiesta non potranno più essere accettate nel computer e i protocolli di routing non potranno essere né ricevuti né trasmessi.

#### Agente SAP

Il servizio **Agente SAP** pubblicizza i servizi di rete in reti IPX utilizzando il protocollo IPX SAP (Service Advertising Protocol). Inoltra anche annunci a un host multihomed. Alcune funzioni, quali Servizi di gestione file e di stampa per NetWare, si basano su questo** **servizio.

Il servizio **Agente SAP** richiede l'installazione del protocollo di trasporto compatibile NWLINK IPX/SPX e non viene installato o attivato per impostazione predefinita. Se il servizio è disattivato, queste funzioni potrebbero non funzionare correttamente.

#### Accesso secondario

Il servizio **Accesso secondario** consente a un utente di creare processi nel contesto di identità di protezione diverse. Viene spesso utilizzato dagli amministratori che accedono come utenti soggetti a restrizioni ma che devono disporre di privilegi amministrativi per poter eseguire una specifica applicazione. Possono utilizzare un accesso secondario per eseguire temporaneamente tali applicazioni.

Un altro componente del servizio **Accesso secondario** è Runas.exe, che consente di eseguire programmi (file \*.exe), console MMC salvate (file \*.msc), collegamenti a programmi e a console MMC salvate ed elementi del Pannello di controllo come amministratore pur avendo eseguito la connessione al computer come membro di un altro gruppo, ad esempio **Users**. In Windows 2000 il servizio è chiamato **servizio RunAs**.

Il servizio **Accesso secondario** è installato ed eseguito automaticamente per impostazione predefinita su Windows XP e Windows Server 2003. Se il servizio viene arrestato o disattivato, questo tipo di accesso non sarà disponibile. Le eventuali chiamate all'API **CreateProcessWithLogonW** non avranno esito positivo. In particolar modo, lo snap-in MMC che avvia le applicazioni con le credenziali di altri utenti e lo strumento RunAs.exe funzioneranno in modo non corretto.

#### Gestione account di protezione

Il servizio **Gestione account di protezione (SAM)** è un sottosistema protetto che gestisce le informazioni di account utente e account di gruppo. In Windows 2000 e nei prodotti della famiglia Windows Server 2003 gli account di protezione delle workstation sono memorizzati dal servizio nel Registro di sistema del computer locale mentre gli account di protezione dei controller di dominio sono memorizzati in Active Directory. In Windows NT 4.0 gli account di protezione, sia locali sia di dominio, sono memorizzati nel Registro di sistema.

All'avvio del servizio **Gestione account di protezione** vengono segnalati gli altri servizi dai quali è pronto ad accettare richieste.

Il servizio **Gestione account di protezione** è presente su tutte le versioni di Windows XP e Windows Server 2003 e non è possibile arrestarlo. Se questo servizio viene disattivato, altri servizi nel computer potrebbero non avviarsi correttamente. Si raccomanda pertanto di non disabilitarlo.

#### Centro sicurezza PC

Il servizio **Centro sicurezza PC** fornisce una posizione centrale per i computer che eseguono Windows XP con SP2 per gestire le impostazioni relative alla protezione. Viene eseguito automaticamente per impostazione predefinita, svolgendo le seguenti attività:

-   Controlla che il servizio **Windows Firewall** sia in esecuzione ed effettua una ricerca presso specifici provider WMI di terze parti per verificare se sono presenti e vengono eseguite applicazioni firewall compatibili.

-   Effettua una ricerca presso specifici provider WMI di terze parti per verificare se è stato installato un software antivirus compatibile, se questo è aggiornato e se la scansione in tempio reale è attivata.

-   Controlla la configurazione del servizio **Aggiornamenti automatici**. Se il servizio **Aggiornamenti automatici** è disattivato o non è stato configurato conformemente alle impostazioni consigliate, il servizio **Centro sicurezza PC** ne informerà l'utente.

Se il servizio **Centro sicurezza PC** determina che un componente protetto è mancante, è stato configurato erroneamente o non è aggiornato, avverte l'utente al riguardo attraverso un messaggio e un'icona di avviso nell'area di notifica sulla barra delle applicazioni quando si effettua l'accesso.

Se il servizio **Centro sicurezza PC** viene disattivato, i componenti protetti continueranno a funzionare conformemente alle impostazioni di configurazione specifiche. Tuttavia, non sarà presente alcun servizio di controllo centralizzato.

#### Server

Il servizio **Server** garantisce il supporto RPC e la condivisione in rete di file, stampa e named pipe. Supporta la condivisione delle risorse locali, quali dischi e stampanti, in modo da consentire ad altri utenti in rete di accedere a queste periferiche. Consente inoltre la comunicazione named pipe tra le applicazioni eseguite nei computer di altri utenti o nel computer in uso, utilizzato per supportare RPC. La comunicazione named pipe rappresenta la quantità di memoria riservata per l'output di un processo da utilizzare come input per un altro processo. Non è necessario che il processo di accettazione degli input venga eseguito localmente nel computer. Questo servizio è installato ed eseguito automaticamente per impostazione predefinita in Windows XP e Windows Server 2003.

Se il servizio **Server** viene arrestato o disattivato, il computer non sarà in grado di condividere i file e le stampanti locali con gli altri computer della rete e di soddisfare richieste RPC remote.

#### Rilevamento hardware shell

Il servizio **Rilevamento hardware shell** effettua il monitoraggio degli eventi hardware AutoPlay e gestisce le relative notifiche. La funzione AutoPlay rileva immagini, musica o file video contenuti in supporti e periferiche rimovibili e avvia automaticamente le applicazioni che riproducono o visualizzano tale contenuto. Ciò semplifica l'utilizzo di periferiche specializzate come i lettori di file MP3 e di foto digitali e consente agli utenti di accedere ai vari tipi di contenuto senza bisogno di sapere quali applicazioni sono necessarie.

AutoPlay supporta vari tipi di contenuto multimediale e applicazioni. I fornitori di hardware indipendenti (IHV, Independent Hardware Vendors) e i fornitori di software indipendenti (ISV, Independent Software Vendors) possono estendere il supporto alle periferiche e le applicazioni di loro produzione. L'utente può configurare una specifica azione di AutoPlay per qualsiasi combinazione di immagini, file musicali e video.

I tipi di supporti e periferiche supportate da AutoPlay sono:

-   Supporti di archiviazione rimovibili

-   Supporti Flash

-   Schede PC

-   USB esterno collegabile a caldo o unità fisse 1394

-   Tipi di contenuto supportati, tra cui:

    -   Immagini (file con estensioni jpg, bmp, gif, tif)

    -   File musicali (con estensioni mp3, wma)

    -   Video (con estensioni mpg, asf)

Il servizio **Rilevamento hardware shell** è installato ed eseguito automaticamente per impostazione predefinita in Windows XP e Windows Server 2003. Se il servizio viene arrestato, non sarà possibile avvalersi della funzione di riproduzione automatica, le icone e le etichette Risorse del computer torneranno a funzionare come in Windows 2000 e anche il funzionamento della shell verrà influenzato.

#### Protocollo SMTP (Simple Mail Transport Protocol)

Il servizio **SMTP (Simple Mail Transfer Protocol)** è un agente di invio e inoltro della posta elettronica. Può accettare e accodare messaggi di posta elettronica per destinazioni remote e stabilire connessioni ad altri computer a intervalli specifici. I controller di dominio Windows utilizzano il servizio **SMTP** per la replica tra siti basata sulla posta elettronica. Anche gli oggetti CDO (Collaboration Data Object) per il componente COM di Windows Server 2003 possono utilizzare questo servizio per l'invio e l'accodamento dei messaggi di posta elettronica in uscita.

Il servizio **SMTP** è installato ed eseguito per impostazione predefinita in Windows Server 2003, Web Edition. In Windows XP e altre versioni di Windows Server 2003, è un componente facoltativo non installato per impostazione predefinita.

#### Servizi TCP/IP semplificati

I **Servizi TCP/IP semplificati** implementano il supporto per i seguenti protocolli e per le seguenti porte:

-   Echo, porta 7, RFC 862

-   Discard, porta 9, RFC 863

-   Character Generator, porta 19, RFC 864

-   Daytime, porta 13, RFC 867

-   Quote of the Day, porta 17, RFC 865

Se i **servizi TCP/IP semplificati** sono abilitati, tutti e cinque i protocolli saranno disponibili per tutte le schede. Non esiste la possibilità di abilitare selettivamente alcuni servizi specifici o di abilitare il servizio scheda per scheda.

Se i **servizi TCP/IP semplificati** vengono arrestati o disattivati, ciò non incide sul funzionamento del sistema operativo. Questo servizio deve essere installato manualmente. Installare questo servizio solo se è necessario che il computer supporti la comunicazione con altri computer che utilizzano questi protocolli.

#### Agente di archiviazione istanza singola

Il servizio **Agente di archiviazione istanza singola (SIS, Single Instance Storage)** è parte integrante dei Servizi di installazione remota (RIS, Remote Installation Services). Questo servizio esegue una ricerca dei file duplicati nel volume RIS per ridurre la quantità di supporti di archiviazione richiesta sul volume. Se vengono trovati file duplicati, il file originale viene copiato nell'Agente di archiviazione istanza singola e al suo posto viene lasciato un file di collegamento in cui sono contenute informazioni relative al file originale, come il percorso corrente, la dimensione e gli attributi. Se in un'immagine sono contenuti file duplicati, questi vengono copiati nell'archivio e di conseguenza è necessario meno spazio nel disco del server RIS.

Il servizio **Agente di archiviazione istanza singola** presenta due limiti.

-   Esso non è in grado di intervenire sui file ai quali viene fatto riferimento mediante punti di giunzione.

-   Può essere utilizzato solo con il file system NTFS, l'unico supportato nei server RIS.

Il servizio **Agente di archiviazione istanza singola** è presente solo se è stato installato il componente Servizi di installazione remota. In tal caso, verrà eseguito automaticamente all'avvio. Se il servizio **Agente di archiviazione istanza singola** viene arrestato, i file non vengono più collegati in questo modo ma quelli collegati esistenti restano accessibili. Le nuove immagini di installazione RIS remota occuperanno tutto lo spazio richiesto dalle rispettive dimensioni e lo spazio residuo sarà limitato. Se il servizio **Agente di archiviazione istanza singola** non è più necessario per il computer, il modo migliore per interromperne l'utilizzo consiste nello scegliere lo strumento Installazione componenti di Windows e nel rimuovere il componente Servizi di installazione remota. Il servizio verrà così disattivato.

#### Smart Card

Il servizio **Smart Card** gestisce e controlla l’accesso a una smart card inserita in un apposito lettore collegato al computer. Il sottosistema della smart card si basa sugli standard del consorzio PC/SC (personal computer/smart card) e comprende il componente Gestione risorse, che gestisce l'accesso ai lettori e alle smart card. A tal fine, Gestione risorse esegue le funzioni seguenti:

-   Identifica e registra le risorse.

-   Alloca lettori e risorse distribuendoli tra varie applicazioni.

-   Supporta le primitive di transazione per l'accesso ai servizi disponibili in una data smart card.

Gestione risorse espone inoltre un sottoinsieme dell'API Win32 per fornire alle applicazioni l'accesso a un'interfaccia utente per la selezione di scheda e lettore. Consente alle applicazioni semplici che riconoscono le smart card di accedere tanto alla smart card quanto al lettore con una quantità minima di codice.

Il servizio **Smart Card** è installato automaticamente per impostazione predefinita sui computer Windows XP e Windows Server 2003. Lo stato di avvio è configurato su **Manuale** e il servizio viene avviato quando un'applicazione richiede l'accesso alla smart card. Se il servizio viene arrestato, non sarà più possibile per il computer leggere le smart card.

#### Servizio SNMP

Il **servizio SNMP** (Simple Network Management Protocol) consente alle richieste SNMP in ingresso di essere servite dal computer locale. Questo servizio include agenti che controllano l'attività nelle periferiche di rete e inviano rapporti alla workstation della console di rete; inoltre, offre un metodo per la gestione degli host di rete, quali workstation o computer server, router, bridge e hub, da un computer a livello centrale in cui è installato il software di gestione della rete. SNMP esegue i servizi di gestione tramite un'architettura distribuita di computer e agenti appositi.

È possibile utilizzare SNMP per eseguire le seguenti attività:

-   **Configurare periferiche remote**: le informazioni di configurazione possono essere inviate a ciascun host in rete dal computer di gestione.

-   **Monitorare le prestazioni della rete**: è possibile registrare la velocità di elaborazione, la velocità effettiva della rete e raccogliere informazioni sull'esito delle trasmissioni di dati.

-   **Rilevare errori di rete o accessi non appropriati**: è possibile configurare allarmi trigger nelle periferiche di rete in cui si verificano alcuni errori. Quando viene generato un allarme, la periferica invia un messaggio di evento al computer di gestione. Alcuni tipi frequenti di allarme sono l'arresto e il successivo riavvio di una periferica, il rilevamento di un errore di collegamento in un router e un accesso non appropriato.

-   **Utilizzo della rete a scopo di controllo**: è possibile monitorare tanto l'utilizzo globale della rete, per identificare l'accesso da parte di un utente o di un gruppo, quanto i tipi di utilizzo delle periferiche e dei servizi di rete.

Nel **servizio SNMP** è incluso un agente SNMP che consente la gestione remota e centralizzata dei computer che eseguono i sistemi operativi riportati di seguito:

-   Windows XP Home Edition

-   Windows XP Professional

-   Windows 2000 Professional

-   Windows 2000 Server

-   Prodotti della famiglia Windows Server 2003

L'agente SNMP consente inoltre di gestire i servizi riportati di seguito:

-   Servizio WINS basato su Windows XP o sui prodotti della famiglia Windows Server 2003 e Windows 2000

-   Servizio DHCP basato su Windows XP o sui prodotti della famiglia Windows Server 2003 e Windows 2000

-   Internet Information Services (IIS) basato su Windows XP o sui prodotti della famiglia Windows Server 2003 e Windows 2000

-   LAN Manager

Il **servizio SNMP** è disponibile solo se si installa manualmente il componente SNMP opzionale attraverso Aggiunta guidata componenti di Windows. Quando installato, il servizio si avvia automaticamente. Se il **servizio SNMP** viene arrestato o disattivato, non sarà più possibile per il computer rispondere alle richieste SNMP. Se il computer è monitorato con strumenti di gestione della rete che si basano su SNMP, essi non saranno più in grado di raccogliere dati dal computer né di controllarne la funzionalità tramite il servizio.

#### Servizio Trap SNMP

Il **Servizio Trap SNMP** riceve messaggi trap contenenti informazioni relative ad eventi specifici e generati da agenti SNMP locali o remoti e li inoltra ai programmi di gestione SNMP in esecuzione nel computer. Se viene configurato per un agente, il **servizio SNMP** genera messaggi trap nel caso in cui si verifichino eventi specifici e li invia a una destinazione trap. Ad esempio, è possibile configurare un agente per iniziare una trap di autenticazione nel caso in cui un computer di gestione sconosciuto invii una richiesta di informazioni. Le destinazioni trap corrispondono al nome e all'indirizzo IP o IPX del computer di gestione. La destinazione trap deve essere un host di rete in cui è installato il software di gestione SNMP. Le destinazioni trap possono essere configurate dall'utente mentre gli eventi che generano un messaggio trap, come il riavvio del computer, sono definiti internamente dall'agente SNMP.

Il **Servizio Trap SNMP** è disponibile solo se si installa manualmente il componente SNMP opzionale attraverso Aggiunta guidata componenti di Windows. Quando installato, il servizio si avvia automaticamente. Se il servizio viene arrestato o disattivato, i programmi basati su SNMP in esecuzione nel computer non potranno ricevere messaggi trap SNMP. Se nel computer il monitoraggio delle periferiche di rete o delle applicazioni server viene eseguito tramite trap SNMP, importanti eventi del computer andranno persi.

#### Helper console di amministrazione speciale

È possibile utilizzare il servizio **Helper console di amministrazione speciale** per eseguire attività di gestione remota su un computer che esegue una versione di Windows Server 2003 se le sue funzioni si sono interrotte a causa di un messaggio di errore di **interruzione**. Il componente dei servizi di gestione emergenze di Windows supporta due interfacce di console fuori banda: la console di amministrazione speciale (SAC, Special Administration Console) e !SAC, che offre un sottoinsieme di comandi SAC da utilizzare quando il server è stato arrestato.

I componenti SAC e !SAC accettano input e inviano output attraverso la porta fuori banda. SAC è un'entità diversa tanto da !SAC quanto dagli ambienti della riga di comando della famiglia Windows Server 2003. Una volta raggiunto uno specifico punto di errore, i componenti dei servizi di gestione emergenze stabiliscono il momento in cui effettuare il passaggio da SAC a !SAC. !SAC diventa disponibile automaticamente se SAC non viene caricato o non funziona. Il servizio **Helper console di amministrazione speciale** consente di creare canali di comunicazione in ingresso attraverso il prompt dei comandi. Questo servizio è installato sui computer Windows Server 2003 soltanto quando si attiva la funzionalità dei servizi di gestione emergenze, come descritto nella documentazione di questo sistema operativo.

Se il servizio **Helper console di amministrazione speciale** viene arrestato, i servizi SAC non saranno più disponibili.

#### SQLAgent$\* (\*UDDI o WebDB)

**SQLAgent$\* (\* UDDI o WebDB)** è un servizio per la pianificazione dei processi e il monitoraggio. Sposta, inoltre, informazioni tra i server SQL e viene molto utilizzato per il backup e la replica. Questi servizi non sono installati o attivati per impostazione predefinita.

Se il servizio **SQLAgent$\* (\* UDDI o WebDB)** viene arrestato, la replica SQL non può aver luogo. Vengono inoltre interrotti tutti i processi pianificati, il monitoraggio degli avvisi/eventi e il riavvio automatico del servizio SQL Server.

#### Servizio di rilevamento SSDP

Il servizio Host Plug and Play universale incluso in Windows XP supporta la funzionalità Plug and Play peer-to-peer per le periferiche di rete. La specifica UPnP ha lo scopo di semplificare l'installazione e la gestione di dispositivi e servizi rete. Il servizio Host Plug and Play universale utilizza il protocollo SSDP (Simple Service Discovery Protocol) per localizzare e identificare le periferiche di rete UPnP.

Il **Servizio di rilevamento SSDP** è installato e configurato su **Manuale** nei computer Windows XP. Il servizio viene avviato solo quando il computer tenta di localizzare e configurare periferiche UPnP. Se questo servizio viene disattivato, il computer non sarà in grado di trovare le periferiche UPnP sulla rete e il servizio Host Plug and Play universale non potrà identificare e interagire con tali periferiche.

#### Notifica eventi di sistema

Il servizio **Notifica eventi di sistema** (SENS) tiene traccia degli eventi del computer come gli eventi di accesso a Windows, gli eventi della rete e gli eventi relativi all’alimentazione e invia notifiche in merito ai sottoscrittori del **Sistema di eventi COM+**. Questo servizio è installato ed eseguito automaticamente per impostazione predefinita in Windows XP e Windows Server 2003.

Se il servizio **Notifica eventi di sistema** viene arrestato, i sottoscrittori del **Sistema di eventi COM+** non ricevono più le notifiche degli eventi e si verificano i seguenti problemi:

-   Le API Win32 IsNetworkAlive() e IsDestinationReachable() non funzionano. Si tratta di API utilizzate soprattutto nelle applicazioni eseguite nei computer portatili.

-   Le interfacce ISens\* non funzionano, soprattutto le notifiche di accesso/disconnessione del servizio SENS.

-   SyncMgr (mobsync.exe) non funziona correttamente. Dipende dalle informazioni di connettività nonché dalle notifiche di connessione/disconnessione dalla rete e accesso/disconnessione ricevute dal servizio SENS.

-   Il Sistema di eventi COM+ genera errori quando tenta di notificare alcuni eventi al servizio SENS.

-   Il servizio **Copia replicata del volume** non viene caricato correttamente, causando il malfunzionamento dell'API dell'utilità di backup di Windows.

#### Servizio Ripristino configurazione di sistema

Il **Servizio Ripristino configurazione di sistema** consente agli utenti di Windows XP di eseguire istantanee della configurazione del computer e di salvarli come una serie di punti di ripristino. Questi punti di ripristino possono essere utilizzati come configurazioni fail-safe dopo un tentativo non riuscito di installazione o aggiornamento di un driver di periferiche o di un'applicazione.

Il **Servizio Ripristino configurazione di sistema** viene attivato per impostazione predefinita e crea automaticamente un nuovo punto di ripristino appena prima che vengano apportate significative modifiche al computer, come l'installazione di nuovi driver di periferiche, aggiornamenti e applicazioni. I punti di ripristino automatici vengono inoltre creati su base giornaliera, tuttavia questa pianificazione può essere modificata.

Se il **Servizio Ripristino configurazione di sistema** viene disattivato, la funzionalità di ripristino automatico del computer non sarà più disponibile e i punti di ripristino non verranno creati né automaticamente né manualmente.

#### Utilità di pianificazione

Il servizio **Utilità di pianificazione** consente di configurare e pianificare l’esecuzione di attività automatiche nel computer. Il servizio effettua il monitoraggio in base ai criteri specificati dall’utente e quando i criteri vengono soddisfatti esegue l'attività pertinente.

È possibile utilizzare la GUI del servizio **Utilità di pianificazione** per eseguire le seguenti attività:

-   Creare elementi di lavoro (attualmente l'unico elemento di lavoro disponibile è rappresentato dalle attività).

-   Pianificare l'esecuzione delle attività a un'ora specifica o in corrispondenza di un evento. È possibile, ad esempio, impostare l'esecuzione di ScanDisk alle 19:00 di ogni domenica.

-   Modificare la pianificazione di un'attività.

-   Personalizzare la modalità di esecuzione delle attività.

-   Interrompere un'attività pianificata.

È possibile avviare il servizio **Utilità di pianificazione** da Gestione computer dello snap-in Servizi di MMC o impostarne l'avvio automatico. Per impostazione predefinita, il servizio **Utilità di pianificazione** è installato sui computer Windows XP e Windows Server 2003. Può essere avviato dalla GUI del programma, dall'API Utilità di pianificazione come descritto nella documentazione del kit SDK o dall'utilità SchTasks.exe.

Se il servizio **Utilità di pianificazione** viene arrestato, le attività pianificate non verranno eseguite all'ora prefissata o all'intervallo impostato. Inoltre, questo servizio è necessario per l'utilità di backup di Windows e per le applicazioni di backup che si affidano all'API dell'utilità stessa. Se nella cartella **%System Root%\\Tasks\\** non sono presenti processi, l'effetto sarà minimo. In caso contrario, i processi la cui esecuzione è necessaria potrebbero non essere avviati. Se il servizio **Utilità di pianificazione** non è disponibile, il feature pack con Systems Management Server e Software Update Services non potrà essere eseguito. Se il servizio **Utilità di pianificazione** viene arrestato, non saranno eseguiti nemmeno i backup pianificati.

#### Servizio guida TCP/IP NetBIOS

Il **Servizio guida TCP/IP NetBIOS** fornisce il supporto per il servizio NetBIOS su TCP/IP (NetBT) e per la risoluzione dei nomi NetBIOS per i client della rete, consentendo agli utenti di condividere file e stampanti e di accedere alla rete. In particolare, per supportare il servizio NetBT, il** **servizio esegue la risoluzione dei nomi DNS e il ping di un insieme di indirizzi IP che restituisce un elenco di indirizzi IP accessibili.

Il **Servizio guida TCP/IP NetBIOS** è installato e avviato automaticamente per impostazione predefinita su Windows Server 2003 e Windows XP. Se questo servizio viene arrestato o disattivato, i client dei servizi NetBT, Redirector (RDR), Server (SRV), **Accesso rete** e **Messenger** potrebbero non essere in grado di condividere file e stampanti e di accedere ai computer. Ad esempio, i Criteri di gruppo basati sui domini non saranno più funzionanti.

#### Server di stampa TCP/IP

Il servizio **Server di stampa TCP/IP** consente la stampa basata su TCP/IP tramite il protocollo Line Printer Daemon. Il servizio Line Printer Daemon (LPDSVC) del server riceve i documenti dalle utilità LPR (Line Printer Remote) native installate nei computer UNIX.

Il servizio **Server di stampa TCP/IP** è un componente opzionale che deve essere installato con uno strumento diverso da Aggiunta guidata componenti di Windows. Se questo servizio viene arrestato, la funzionalità di stampa basata su TCP/IP non sarà disponibile.

#### Telefonia

Il servizio **Telefonia** fornisce il supporto TAPI per programmi che controllano le periferiche per la telefonia e le connessioni vocali basate su IP nel computer locale e, tramite LAN, nei server in cui è in esecuzione il servizio. Il servizio consente alle applicazioni di fungere da client nei confronti di apparecchiature telefoniche come centralini privati, telefoni e modem. Il supporto TAPI di cui si avvale consente al servizio di supportare diversi protocolli per la comunicazione con le apparecchiature telefoniche, protocolli implementati dai provider dei servizi di telefonia.

Il servizio **Telefonia** è installato per impostazione predefinita in Windows XP e Windows Server 2003 e il suo tipo di avvio è configurato su **Manuale**. Le applicazioni che richiedono il TAPI possono avviarlo. Se il servizio **Telefonia** viene arrestato o disattivato, tutti i servizi che dipendono esplicitamente da esso, come il supporto per modem, non verranno avviati. Il servizio non può essere arrestato se un servizio che dipende da esso, come RAS, è correntemente attivo. Se non sono in esecuzione servizi dipendenti quando il servizio viene arrestato, questo verrà riavviato nel caso in cui un'applicazione qualsiasi esegua una chiamata di inizializzazione all'interfaccia TAPI.

#### Telnet

Il servizio **Telnet** per Windows permette sessioni di terminale ASCII ai client Telnet. Supporta due tipi di autenticazione e quattro tipi di terminale: American National Standards Institute (ANSI), VT-100, VT-52 e VTNT.

Il servizio **Telnet** inoltre a un utente remoto di accedere a un computer ed eseguire programmi di console utilizzando la riga di comando. Nel computer che esegue il servizio **Telnet** sono supportate le connessioni provenienti da vari client Telnet TCP/IP, compresi computer basati su UNIX e Windows. Il servizio **Telnet** è installato sui computer Windows XP e Windows Server 2003 per impostazione predefinita, ma è disattivato. Nelle installazioni aggiornate è stato conservato il tipo di avvio del servizio **Telnet** della versione precedente di Windows.

Se il servizio **Telnet** viene arrestato, l'accesso remoto ai programmi potrebbe non essere disponibile mediante il client Telnet, gli utenti remoti non saranno in grado di connettersi utilizzando il protocollo Telnet e gli utenti locali non potranno connettersi al computer o eseguire applicazioni basate su console.

#### Servizi terminal

I **Servizi terminal** costituiscono un ambiente multisessione che consente l'interazione dei client con una sessione virtuale del desktop di Windows e con le applicazioni Windows in esecuzione nel server.

Per impostazione predefinita, i **Servizi terminal** sono installati in modalità di amministrazione remota sui computer Windows Server 2003. Per installare **Servizi terminal** in modalità applicazione, utilizzare Configurazione server o Installazione componenti di Windows per cambiare la modalità di **Servizi terminal**. Questo servizio è necessario nei computer Windows Server 2003 se si desidera utilizzare Desktop remoto. In Windows XP è necessario se si desidera utilizzare Cambio rapido utente, Desktop remoto e Assistenza remota. Su entrambe le versioni di Windows, questo servizio è installato per impostazione predefinita, con un tipo di avvio **Manuale.**

Se il servizio di sistema **Servizi terminal** viene arrestato o disattivato, le prestazioni del computer potrebbero non essere affidabili e Assistenza remota potrebbe non essere più disponibile. Per impedire l’utilizzo remoto del computer, deselezionare le caselle di controllo relative ad **Assistenza remota** e **Desktop remoto** nella scheda **Connessione remota** della finestra **Proprietà del sistema**.

#### Licenze Servizi terminal

Il servizio **Licenze Servizi terminal** installa un server licenze e fornisce licenze client registrate quando ci si connette a un server terminal. **Licenze Servizi terminal** è un servizio a basso impatto che archivia le licenze client rilasciate per un server terminal e registra quindi le licenze rilasciate per computer client o terminali. Questo servizio è presente e necessario solo nei server su cui **Servizi terminal** è installato in modalità applicazione.

Se il servizio **Licenze Servizi terminal** viene disattivato, il server non è disponibile per il rilascio di licenze di Servizi terminal ai client che ne facciano richiesta. Se in un controller di dominio dell'insieme di strutture viene rilevato un altro server licenze, il server terminal richiedente tenterà di utilizzarlo.

#### Directory di sessione di Servizi terminal

Il servizio **Directory di sessione di Servizi terminal** costituisce un ambiente multisessione che consente l'accesso dei client a una sessione virtuale del desktop di Windows e ai programmi Windows in esecuzione in un computer con Windows Server 2003.

Il servizio **Directory di sessione di Servizi terminal** consente ai cluster di server terminal con carico bilanciato di indirizzare adeguatamente una richiesta di connessione di un utente al server in cui l'utente ha già aperto una sessione. Il servizio Bilanciamento carico di rete di Windows raggruppa le risorse di elaborazione di diversi server tramite il protocollo di rete TCP/IP. È possibile utilizzare il servizio Bilanciamento carico di rete di Windows con un cluster di server terminal per fornire agli utenti un singolo punto di accesso server terminal distribuendo le sessioni tra più server.

Il servizio **Directory di sessione di Servizi terminal** tiene traccia delle sessioni disconnesse nel cluster e assicura che gli utenti vengano riconnessi a tali sessioni. Questo servizio è installato ma disattivato per impostazione predefinita sui computer Windows Server 2003 in cui è presente il componente Servizi terminal. Microsoft consiglia di *non* installare il servizio **Directory di sessione di Servizi terminal** su un server terminal.

Se il servizio **Directory di sessione di Servizi terminal** viene arrestato, le richieste di connessione verranno indirizzate al primo server disponibile, indipendentemente dal fatto che abbiano aperto o meno una sessione in un punto qualsiasi del cluster.

#### Temi

Il servizio **Temi** consente di gestire i temi dell’interfaccia utente. Il servizio **Temi** fornisce il supporto per la nuova GUI di Windows XP. Per tema del desktop si intende un insieme predefinito di icone, tipi di carattere, colori, suoni e altri elementi che conferiscono al desktop un aspetto uniforme e distintivo. È possibile cambiare tema, crearne uno personalizzato modificandone uno esistente e salvarlo con un nuovo nome oppure ripristinare il tema di Windows classico. Sui computer Windows XP, il servizio **Temi** è impostato per avviarsi automaticamente. Sui computer Windows Server 2003 è disattivato.

Se il servizio **Temi** viene arrestato o disattivato, il nuovo stile di visualizzazione di Windows XP, ovvero finestre, pulsanti, barre di scorrimento e altri controlli, verrà ripristinato allo stile Windows classico.

#### Trivial FTP Daemon

Il servizio **Trivial FTP (TFTP) Daemon** non richiede un nome utente o una password e costituisce parte integrante dei Servizi di installazione remota (RIS) per Windows Server 2003. Il servizio implementa il supporto per il protocollo TFTP definito nelle seguenti RFC:

-   RFC 1350 – TFTP

-   RFC 2347 – Estensione delle opzioni

-   RFC 2348 – Opzione dimensione blocco

-   RFC 2349 – Opzioni per l'intervallo di timeout e le dimensioni dei trasferimenti

I server di installazione remota utilizzano il servizio **Trivial FTP Daemon** per scaricare i file iniziali necessari per l'avvio del processo di installazione remota. Il file generalmente scaricato nel client con questo servizio è Startrom.com, responsabile dell'avvio del computer client. Quando si preme F12 come richiesto, viene scaricata l'Installazione guidata client che dà inizio al processo di installazione remota.

**Trivial FTP Daemon** non è installato per impostazione predefinita. Se questo servizio viene arrestato o disattivato, i client che richiedono Servizi di installazione remota da questo server non riusciranno ad eseguire installazioni. La procedura corretta per disabilitare il servizio consiste nel disinstallare Servizi di installazione remota.

#### Gruppo di continuità

Il servizio **Gruppo di continuità** gestisce il gruppo di continuità collegato al computer tramite una porta seriale. Questo servizio è installato per impostazione predefinita in Windows XP e Windows Server 2003, ma il suo tipo di avvio è configurato su **Manuale.**

L'arresto o la disabilitazione del servizio **Gruppo di Continuità** comporta l'interruzione della comunicazione con il gruppo di continuità. Se si verifica un'interruzione dell'alimentazione, il gruppo di continuità potrebbe non riuscire ad arrestare il computer in modo sicuro, causando la perdita dei dati.

#### Host di periferiche Plug and Play universali

Il servizio **Host di periferiche Plug and Play universali** supporta la funzionalità Plug and Play universale (UPnP) peer-to-peer per i dispositivi di rete. La specifica UPnP ha lo scopo di semplificare l'installazione e la gestione di dispositivi e servizi rete. UPnP esegue il rilevamento e il controllo del dispositivo e del servizio attraverso meccanismi di protocollo basati su standard e che non richiedono l'installazione di alcun driver.

I dispositivi UPnP possono configurare automaticamente gli indirizzi di rete, annunciare la loro presenza su una subnet di rete e consentire lo scambio delle descrizioni del dispositivo e del servizio. Quando il servizio **Host di periferiche Plug and Play universali** è installato, un computer Windows XP può agire come punto di controllo UPnP per individuare e controllare i dispositivi attraverso l'interfaccia Web o dell'applicazione. Questo servizio è installato per impostazione predefinita sui computer Windows XP ed è configurato su **Manuale.**

#### Upload Manager

Il servizio **Upload Manager** gestisce i trasferimenti di file sincroni e asincroni tra computer client e server della rete. I dati dei driver dei computer dei clienti vengono caricati in modo anonimo da Microsoft e utilizzati per aiutare gli utenti a trovare i driver necessari per i loro computer. Il Server informazioni driver Microsoft richiede l’autorizzazione del client per caricare il profilo hardware del computer, quindi cerca in Internet informazioni su come ottenere il driver necessario o come ricevere assistenza da Microsoft o da terze parti competenti.

I dati caricati dal computer allo scopo di reperire informazioni sui driver includono i numeri di identificazione hardware della periferica, la data in cui è stata terminata la procedura di Installazione guidata hardware e l'ID del sistema operativo Windows in esecuzione. Tali dati non vengono utilizzati per risalire all'utente, al computer, all'azienda, all'indirizzo IP o a qualsivoglia altra fonte di informazioni.

Le informazioni ottenute sono utilizzate per individuare le periferiche i cui driver sono difficili da reperire. Le eventuali informazioni supplementari sui driver saranno disponibili non appena il numero di identificazione della periferica sarà stato caricato. Se non sono disponibili ulteriori informazioni sul driver, Microsoft registra il numero di identificazione della periferica e collabora con i fornitori di hardware per incrementare la disponibilità dei driver di periferiche di Windows o per fornire informazioni sulla disponibilità di driver e sul supporto delle periferiche.

Il servizio **Upload Manager** è installato per impostazione predefinita e configurato su **Manuale** nei computer Windows Server 2003. Se il servizio viene arrestato, i trasferimenti di file sincroni e asincroni tra client e server in rete non saranno possibili.

#### Servizio dischi virtuali

Il **Servizio dischi virtuali** (VDS) offre un’unica interfaccia per la gestione della virtualizzazione dell’archiviazione a blocchi eseguita nel sistema operativo, in sottosistemi hardware di archiviazione RAID (Redundant Array of Independent Disks) o in altri motori di virtualizzazione.

Il **Servizio dischi virtuali** costituisce un'interfaccia, indipendente da fornitori e tecnologie, per la gestione di volumi logici (software) e unità logiche (hardware). È possibile utilizzare questa interfaccia per la gestione delle operazioni di binding, il monitoraggio delle prestazioni, la rilevazione e registrazione della topologia, lo stato dei volumi e la registrazione degli errori.

I dischi virtuali non vanno confusi con le istantanee. Diversamente dal **servizio Copia shadow del volume**, il **Servizio dischi virtuali** non agisce in coordinamento con applicazioni o file system e i dati contenuti in un volume non vengono sincronizzati prima di un'operazione di configurazione di un volume o disco. Per configurare un plex del mirror, è possibile utilizzare il **Servizio dischi virtuali** ma è necessario un provider di istantanee per eseguire il coordinamento durante la rimozione del plex e la replica dell'istantanea. Tale utilizzo esula dall'ambito del presente documento con due eccezioni:

-   Il **Servizio dischi virtuali** agisce in modo coordinato con il file system prima dell'estensione o la compattazione dei volumi.

-   Le istantanee basate sulla copia completa sono interpretate come plex dal **Servizio dischi virtuali**.

Il **Servizio dischi virtuali** è installato e configurato su **Manuale** nei computer Windows Server 2003. Il servizio viene avviato quando un'applicazione tenta di utilizzare i servizi VDS. Se viene arrestato, i servizi VDS non saranno più disponibili.

#### Copia replicata del volume

Il servizio **Copia Shadow del volume** gestisce e implementa le copie shadow dei volumi, utilizzate per il backup e altri scopi. Il servizio gestisce le istantanee del volume. Quando viene eseguito un tentativo di backup utilizzando la nuova infrastruttura di istantanee, l'applicazione preposta ai backup stabilisce il numero di autori in esecuzione nel servizio e invia richieste a ciascuno di essi per reperire i metadati necessari. Vengono così individuati i volumi che richiedono una copia shadow e la sessione di backup viene completata correttamente. Dopo la presentazione dei volumi al coordinatore di copie shadow, viene creata una copia shadow. Questa crea volumi che corrispondono a quelli originali al momento dell'esecuzione della copia shadow.

Il servizio **Copia shadow del volume** è installato sui computer Windows XP e Windows Server 2003 e il suo tipo di avvio è configurato su **Manuale**. Se il servizio viene arrestato, le copie shadow non sono disponibili per il backup e il processo di backup potrebbe non avere esito positivo. Inoltre, il servizio **Copia shadow del volume** è necessario per l'utilità di backup di Windows e per le applicazioni di backup che si affidano all'API dell'utilità stessa.

#### WebClient

Il servizio **WebClient** consente alle applicazioni Win32 di accedere a documenti su Internet. Il servizio estende le funzioni di rete di Windows consentendo alle applicazioni Win32 standard di creare, leggere e scrivere file in file server presenti in Internet utilizzando WebDAV, un protocollo per l'accesso ai file descritto in XML e che utilizza HTTP per comunicare. Mediante il protocollo HTTP standard, WebDAV viene eseguito in infrastrutture Internet esistenti, come i firewall ed i router.

Il servizio **WebClient** è installato sia in Windows XP sia in Windows Server 2003. In Windows XP, il servizio viene avviato automaticamente. In Windows Server 2003 è disattivato. Se il servizio **WebClient** viene arrestato, gli utenti del computer non potranno servirsi della Pubblicazione guidata sul Web per pubblicare dati in Internet relativamente a percorsi in cui è utilizzato il protocollo WebDAV.

#### Gestore elementi Web

Il servizio **Gestore elementi Web** è installato soltanto su Windows Server 2003, Web Edition. Fornisce gli elementi dell’interfaccia utente Web per il sito Web di amministrazione alla porta 8098, determinando le informazioni seguenti:

-   Schede da visualizzare nel sito Web di amministrazione

-   Attività di Amministrazione remota a disposizione dell'amministratore

-   Sommario

-   Argomenti della Guida

-   Avvisi di Amministrazione remota visualizzabili

Gli amministratori possono gestire un server in modalità remota se si connettono al server all'indirizzo https://*&lt;servername&gt;*:8098. Quando questo sito Web riceve una connessione, il codice ASP (Active Server Pages) predefinito richiede al servizio **Gestore elementi Web** le informazioni sopra elencate. Terminata la raccolta delle informazioni, la pagina Web corretta viene visualizzata.

Il servizio **Gestore elementi Web** carica tutte le informazioni all'avvio e il client, ovvero il codice ASP in questo scenario, richiede gli elementi dell'interfaccia utente Web tramite un'interfaccia COM. Il servizio viene eseguito nell’account di sistema locale e le richieste all’interfaccia COM vengono accettate solo dai client in esecuzione con l’account di sistema locale o di amministrazione. Se il servizio viene arrestato o impostato su **Manuale**, si avvierà al ricevimento della successiva richiesta di elementi di interfaccia utente Web.

Il servizio **Gestore elementi Web** viene riavviato automaticamente quando si accede all'interfaccia Web per l'amministrazione remota. Se il servizio viene disabilitato, tutti i servizi che dipendono esplicitamente da esso non verranno avviati e l'interfaccia utente Web Strumenti di amministrazione remota, per l'amministrazione del server, non funzionerà correttamente.

#### Audio Windows

Il servizio **Audio Windows** fornisce il supporto per le funzioni audio e per le funzioni degli eventi correlati all’audio. Il servizio gestisce eventi Plug-and-Play compatibili per periferiche audio, come schede audio ed effetti audio globali (GFX, Global Audio Effects) per interfacce di applicazioni audio per Windows. Esempi di GFX sono l'equalizzazione (EQ), il miglioramento dei bassi e la correzione degli altoparlanti. Il servizio gestisce il caricamento, la rimozione e il salvataggio/ripristino dello stato dei GFX sessione per sessione.

Il pannello di controllo Multimediale consente di eseguire le operazioni seguenti:

-   Abilitare o disabilitare un GFX.

-   Scegliere tra i vari filtri GFX, se sono disponibili più GFX per la periferica audio in questione. Nel file INF del driver GFX viene specificato l'hardware di destinazione.

Il servizio **Audio Windows** è installato sui computer Windows Server 2003 e Windows XP ed è configurato per avviarsi automaticamente sui computer che eseguono Windows XP e Windows Server 2003, Standard Edition. Il servizio è disattivato sulle altre versioni di Windows Server 2003.

Non è possibile arrestare **AudioWindows** una volta che è stato avviato. La disabilitazione del servizio può incidere sulle funzioni audio fino a rendere impossibile l'ascolto di suoni o l'elaborazione di GFX.

#### Windows Firewall /Condivisione connessione Internet

Il servizio **Windows Firewall /Condivisione connessione Internet** (ICS)** **fornisce servizi di conversione degli indirizzi di rete (NAT, Network Address Translation), risoluzione di nomi e indirizzi e servizi di prevenzione delle intrusioni per tutti i computer di una rete domestica o di una piccola rete aziendale tramite una connessione remota o a banda larga.

Quando questo servizio è attivato, il computer diventa un "gateway Internet" di rete, consentendo agli altri computer client di condividere una connessione Internet, condividere file e utilizzare le stesse stampanti. Per questo servizio sono disponibili criteri di gruppo dipendenti dall’indirizzo.

In Windows 2000 e Windows XP Service Pack 1 questo servizio era denominato Condivisione connessione Internet. Non è stato incluso nella versione originale di Windows Server 2003.

**Windows Firewall /Condivisione connessione Internet** è un servizio predefinito che viene installato e avviato automaticamente sui computer Windows XP. Il servizio è installato per impostazione predefinita anche sui computer Windows Server 2003, ma è configurato su **Disabilitato.**

Se il servizio **Windows Firewall /Condivisione connessione Internet** viene arrestato, i servizi di rete come la condivisione Internet, la risoluzione dei nomi e degli indirizzi e la prevenzione delle intrusioni non saranno disponibili. I client della rete potrebbero non essere in grado di accedere a Internet e i loro indirizzi IP scadranno, producendo come effetto l’utilizzo di APIPA (Automatic Private IP Addressing) per la connettività di rete peer-to-peer da parte di alcuni client.

#### Acquisizione di immagini di Windows (WIA)

Il servizio **Acquisizione di immagini di Windows (WIA)** fornisce servizi per l’acquisizione di immagini per scanner, fotocamere e videocamere.

In Windows Server 2003, questo servizio supporta le periferiche di acquisizione immagini utilizzando l'architettura WDM (Windows Driver Model). Con questo servizio la comunicazione tra applicazioni e periferiche di acquisizione immagini è affidabile, consentendo di acquisire immagini in modo efficiente e di trasferirle nel computer per poterle modificare e utilizzare. Il servizio è necessario per acquisire gli eventi generati dalle periferiche di acquisizione immagini.

Il servizio **Acquisizione di immagini di Windows (WIA)** supporta periferiche di acquisizione immagini SCSI (Small Computer System Interface), IEEE 1394, USB e seriali. Il supporto per le periferiche a infrarossi, parallele e seriali proviene dalle interfacce a infrarossi, parallele e seriale esistenti. Esempi di periferiche di acquisizione immagini sono gli scanner di immagini e le foto/videocamere digitali. Il servizio supporta inoltre le videocamere Web basate sull'API Microsoft DirectShow e videocamere digitali per l'acquisizione di immagini da video.

Il servizio **Acquisizione di immagini di Windows (WIA)** è installato e configurato su **Manuale** in Windows XP ed è installato e disattivato per impostazione predefinita nei computer Windows Server 2003. Se il servizio viene arrestato, gli eventi provenienti dalle periferiche di acquisizione immagini non vengono acquisiti né elaborati. Se viene installata una periferica WIA, il servizio viene riavviato automaticamente all'avvio. Il riavvio avviene anche ogni volta che si apre un'applicazione abilitata per WIA.

#### Windows Installer

Il servizio **Windows Installer** gestisce l'installazione e la rimozione delle applicazioni utilizzando una serie di regole di impostazione definite in modo centralizzato durante il processo di installazione che specificano come installare e configurare le applicazioni. Questo servizio, inoltre, consente di modificare, riparare o rimuovere le applicazioni esistenti. La tecnologia di questo servizio è data dalla combinazione del servizio **Windows Installer** per i sistemi operativi Windows e del formato dei file di pacchetto (estensione msi), utilizzato per contenere le informazioni relative all'installazione e alla configurazione delle applicazioni.

**Windows Installer** non solo è un programma di installazione, ma anche un sistema di gestione software estensibile. Consente di gestire l'installazione, l'aggiunta e l'eliminazione dei componenti software, monitorare la capacità di recupero dei file e gestire il ripristino di emergenza di base dei file tramite rollback. Supporta inoltre l'installazione e l'esecuzione delle applicazioni software da più origini e può essere personalizzato dagli sviluppatori che desiderano installare applicazioni personalizzate.

Per impostazione predefinita, il servizio **Windows Installer** è installato e configurato su **Manuale** sia nei computer Windows XP sia nei computer Windows Server 2003. Viene avviato dalle applicazioni che si servono di tale servizio. Se questo servizio viene arrestato, le applicazioni che ne fanno uso non potranno essere installate, rimosse, riparate o modificate. Le applicazioni che si servono di Windows Installer durante l'esecuzione, inoltre, potrebbero non essere eseguite.

#### WINS (Windows Internet Name Service)

Il servizio **WINS (Windows Internet Name Service)** consente la risoluzione dei nomi NetBIOS. La presenza dei server WINS è fondamentale per l'individuazione delle risorse di rete identificabili tramite i nomi NetBIOS. I server WINS sono obbligatori, a meno che tutti i domini non siano stati aggiornati ad Active Directory e sia stato installato Windows 2000 Server o versioni successive del sistema operativo Windows in tutti i computer della rete.

Se questo servizio viene arrestato, verranno apportate le seguenti modifiche di funzionamento:

-   Non sarà possibile localizzare i domini e i relativi controller di Windows NT 4.0.

-   Non sarà possibile localizzare i domini e i relativi controller di Active Directory in Windows 2000 o Windows Server 2003 dai client Windows NT 4.0.

-   I nomi NetBIOS vengono risolti solo se la periferica il cui nome deve essere risolto fa parte della stessa subnet della periferica che tenta di eseguire l'operazione. La periferica deve essere configurata per la risoluzione dei nomi NetBIOS mediante broadcast.

Il servizio **WINS** sarà presente soltanto sui computer Windows Server 2003 che sono stato configurati per operare come server WINS.

#### Strumentazione gestione Windows

Il servizio **Strumentazione gestione Windows** (WMI) offre un’interfaccia e un modello di oggetti comuni per l’accesso alle informazioni di gestione sui sistemi operativi, le periferiche, le applicazioni e i servizi. WMI è un’infrastruttura che consente di creare applicazioni e strumenti di gestione ed è inclusa negli attuali sistemi operativi Microsoft.

L'infrastruttura WMI è un componente dei sistemi operativi Microsoft Windows che cura lo spostamento e la memorizzazione delle informazioni sugli oggetti gestiti. È composta da due elementi: il servizio **Strumentazione gestione Windows** e l'archivio WMI. Il servizio funge da intermediario tra i provider, le applicazioni di gestione e l'archivio WMI, inserendo in quest'ultimo le informazioni dei provider, accede all'archivio WMI per rispondere a query e istruzioni provenienti dalle applicazioni di gestione ed è in grado di trasferire le informazioni direttamente tra un provider e un'applicazione di gestione. Al contrario, l'archivio WMI funge da area di archiviazione per le informazioni fornite dai vari provider.

Il servizio **Strumentazione gestione Windows** consente l'accesso ai dati di gestione mediante una serie di interfacce, tra cui l'API COM, script e interfacce della riga di comando. È compatibile con le interfacce e i protocolli di gestione precedenti, come SNMP (Simple Network Management Protocol). Il servizio è installato ed eseguito automaticamente sui computer Windows XP e Windows Server 2003. Se il servizio viene arrestato, la maggior parte delle applicazioni per Windows non funzionerà correttamente.

#### Estensioni driver Strumentazione gestione Windows

Il servizio **Estensioni driver di Strumentazione gestione Windows** consente di eseguire il monitoraggio di tutti i driver e i provider di analisi eventi configurati per la pubblicazione di informazioni di Strumentazione gestione Windows (WMI) o di analisi eventi. Per impostazione predefinita, questo servizio è installato su Windows XP e Windows Server 2003 e configurato su **Manuale**.

#### Servizi Windows Media

**Servizi Windows Media** fornisce servizi di flussi multimediali tramite reti basate su IP. L'attuale versione di Servizi Windows Media sostituisce i quattro servizi che componevano le versioni 4.0 e 4.1 precedenti:

-   Il servizio Windows Media Monitor

-   Il servizio Windows Media Program

-   Il servizio Stazione di Windows Media

-   Il servizio Unicast di Windows Media

**Servizi Windows Media** è ora un servizio unificato eseguito in Windows Server 2003, Standard Edition, Windows Server 2003, Enterprise Edition, Windows Server 2003, Datacenter Edition e Windows Server 2003, Web Edition. I relativi componenti principali sono stati sviluppati tramite COM, creando un'architettura flessibile facilmente personalizzabile per applicazioni specifiche. Supporta una gamma più ampia di protocolli di controllo, inclusi RTSP (Real Time Streaming Protocol), MMS (Microsoft Media Server) e HTTP.

La piattaforma **Servizi Windows Media** è conforme agli standard di settore seguenti:

-   WMI per la notifica e la messaggistica di eventi server

-   SNMP per i componenti di rete

-   XML, SMIL (Synchronized Multimedia Integration Language) 2.0 e DOM (Document Object Model) per l'implementazione di elenchi di riproduzione

-   MPEG (Moving Picture Experts Group) 1 e 2 per i formati audio e video

Nella maggior parte dei casi i flussi multimediali utilizzano i componenti principali installati con **Servizi Windows Media**. In alcune situazioni più complesse, tuttavia, può essere necessario incorporare una programmazione personalizzata e svolgere attività integrative. Il kit SDK di **Servizi Windows Media** fornisce a sviluppatori e integratori di sistemi l'accesso a tutti gli elementi del server tramite una combinazione di plug-in, un modello di oggetti ampiamente documentato e una nutrita serie di notifiche di eventi esterni, tutti elementi facilmente personalizzabili.

**Servizi Windows Media** è un servizio opzionale che deve essere installato separatamente sui computer Windows Server 2003. Se questo servizio viene arrestato o disattivato, i servizi dei flussi multimediali potrebbero non essere più disponibili.

#### Gestione risorse di sistema Windows

Il servizio **Gestione risorse di sistema Windows** (WSRM) è uno strumento facoltativo che consente di distribuire applicazioni in scenari consolidati. Esegue una gestione basata su criteri del consumo di CPU e di memoria da parte di processi in esecuzione in una singola istanza del sistema operativo. Negli scenari progettati sono incluse numerose applicazioni server eterogenee, vari utenti di Servizi terminal, numerose istanze di SQL Server, più pool di applicazioni di IIS V6 oppure Exchange e IIS V6 eseguiti insieme nello stesso computer.

L'opzione principale per la gestione della CPU è costituita dagli obiettivi della larghezza di banda, espressi in percentuale dell'utilizzo della CPU. Gli obiettivi sono rispettati monitorando e rettificando dinamicamente le priorità dei processi. Il servizio **WSRM** fornisce inoltre la gestione dell'affinità, tramite l'utilizzo di API specifiche per processo per l'affinità marcata.

Le opzioni per la gestione della memoria comprendono i limiti del working set e il massimo della memoria vincolata, applicato in funzione del processo. I limiti del working set sono impostati nei criteri e applicati da WSRM mediante una API del kernel. Ne consegue che il sistema per la gestione della memoria del kernel applica e gestisce i limiti relativi alle dimensioni del working set eseguendo il paging del processo in base alle esigenze del momento. La memoria vincolata viene semplicemente monitorata a fronte di un limite superiore. Quando tale limite viene superato, il processo viene interrotto oppure viene registrato un evento, a scelta dell'utente.

Altre funzioni sono le seguenti: funzioni di calendario complete per la pianificazione dei criteri desiderati, criteri di ricerca sofisticati per l'identificazione dei processi in fase di esecuzione, contatori specifici di WRM e un sistema semplice per l'accounting dei processi.

Il servizio **WSRM** è implementato come un'opzione e viene eseguito sulle versioni del sistema operativo di Windows che sono state rilasciate dopo Windows 2000 Service Pack 3. I componenti server possono essere installati su Windows Server 2003, Datacenter Edition e Windows Server 2003, Enterprise Edition (oltre alle versioni x64 di queste ultime). Il client WSRM deve essere installato su ogni computer gestito. Per l'amministrazione del servizio sono disponibili uno snap-in MMC e programmi della riga di comando che possono essere installati ed eseguiti indifferentemente sui computer Windows 2000 e Windows XP Professional o nel sistema Windows .NET. Il servizio può essere installato ed eseguito esclusivamente in .NET Datacenter e .NET Enterprise. Queste SKU sono applicate in fase di installazione ed esecuzione.

#### Ora di Windows

Il servizio **Ora di Windows** gestisce la sincronizzazione della data e dell’ora in tutti i computer in esecuzione in una rete Microsoft Windows. Utilizza il protocollo NTP per sincronizzare gli orologi dei computer, in modo che sia possibile assegnare un valore dell’orologio, o timestamp, preciso alle richieste di convalida e di accesso alle risorse della rete. Grazie all'implementazione di NTP e all'integrazione dei provider di servizi orari, **Ora di Windows** rappresenta un servizio orario affidabile e scalabile per gli amministratori. Per i computer non associati a un dominio, è possibile configurare **Ora di Windows** per sincronizzare l'ora con un'origine esterna. Se questo servizio è disattivato, l'impostazione dell'ora per i computer locali non verrà sincronizzata con un servizio orario all'interno del dominio di Windows o con un servizio orario esterno.

Se il servizio **Ora di Windows** viene arrestato o disattivato, la sincronizzazione della data e dell'ora non è disponibile nell'insieme di strutture o in un server NTP esterno. Esistono due possibili scenari:

-   Se il servizio **Ora di Windows** viene arrestato su una workstation, questa non sarà in grado di sincronizzare l'ora con un'altra origine, ma i server esterni non ne saranno influenzati.

-   Se il servizio **Ora di Windows** viene arrestato su un controller di dominio, si verificherà la situazione precedente, con la differenza che neanche i membri del dominio saranno in grado di sincronizzare l'ora. Ciò potrebbe ripercuotersi negativamente sulla sincronizzazione dell'ora dell'organizzazione.

Per impostazione predefinita, il servizio **Ora di Windows** è installato ed eseguito automaticamente sia nei computer Windows XP sia nei computer Windows Server 2003.

**Nota**: per ulteriori informazioni sul servizio **Ora di Windows** in Windows Server 2003, vedere "[How Windows Time Service Works](http://technet.microsoft.com/en-us/library/cc773013.aspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/
TechRef/71e76587-28f4-4272-a3d7-7f44ca50c018.mspx e "[Windows Time Service Tools and Settings](http://technet.microsoft.com/en-us/library/cc773263.aspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/TechRef/
b43a025f-cce2-4c82-b3ea-3b95d482db3a.mspx.

#### Servizio rilevamento automatico proxy WinHTTP

Il **Servizio rilevamento automatico proxy Web WinHTTP** implementa il protocollo WPAD (Web Proxy Auto-Discovery) per i servizi HTTP Windows (WinHTTP). WPAD è un protocollo che consente a un client HTTP di rilevare automaticamente una configurazione proxy.

Se il **Servizio rilevamento automatico proxy Web WinHTTP** viene arrestato o disabilitato, il protocollo WPAD viene eseguito all'interno del processo del client HTTP, anziché in un processo esterno parte del servizio; di conseguenza, non si verifica alcuna perdita di funzionalità. Questo servizio è installato sui computer Windows Server 2003 per impostazione predefinita ed il suo tipo di avvio è configurato su **Manuale.**

#### Configurazione automatica reti senza fili

Il servizio **Configurazione automatica reti senza fili** consente la configurazione automatica delle schede IEEE 802.11 per le comunicazioni senza fili. Microsoft ha collaborato con i fornitori di schede di interfaccia di rete 802.11 per migliorare le prestazioni in roaming senza fili di Windows automatizzando il processo di configurazione della scheda di interfaccia di rete da associare a una rete disponibile.

**Nota**: il servizio **Configurazione automatica reti senza fili** è denominato **Zero Configuration reti senza fili** in Windows XP.

La scheda di interfaccia di rete senza fili e il relativo driver NDIS (Network Driver Interface Specification) possono limitarsi a supportare pochi nuovi identificatori di oggetto (OID, Object Identifiers) NDIS utilizzati per inviare query e impostare la periferica e il funzionamento del driver. La scheda eseguirà una ricerca delle reti disponibili e invierà le informazioni a Windows. Il servizio **Configurazione automatica reti senza fili** esegue la configurazione della scheda per una rete disponibile. Nei casi in cui due reti coprano la stessa area, è possibile configurare un ordine preferito in modo che venga verificata la disponibilità di ogni rete in successione fino all'individuazione di quella attiva. È inoltre possibile limitare l'associazione alle reti preferite e configurate.

Il servizio **Configurazione automatica reti senza fili** viene installato e avviato automaticamente sui computer Windows Server 2003 e Windows XP (ad eccezione di Windows Server 2003, Web Edition, in cui è configurato su **Manuale).** Se questo servizio viene arrestato, la configurazione automatica non è disponibile.

#### Scheda WMI Performance

Il servizio **Scheda WMI Performance** fornisce informazioni relative alla libreria delle prestazioni dai provider di alte prestazioni WMI. Le applicazioni e i servizi possono fornire i contatori delle prestazioni in due modi: scrivendo un provider di alte prestazioni WMI o scrivendo una libreria di prestazioni. Gli utenti di dati relativi alle prestazioni elevate possono richiederli in due modi: mediante il servizio WMI o tramite le API dell'helper Dati di prestazione (PHD, Performance Data Helper). Alcuni meccanismi esistenti comportano l'interazione dei due modelli consentendo ai client che accedono ai contatori di un modello di vedere anche quelli forniti dall'altro. Uno di tali meccanismi è la scheda di inversione.

Il servizio **Scheda WMI Performance** consente di trasformare i contatori delle prestazioni, forniti dai provider di alte prestazioni WMI, in contatori che possono essere utilizzati dall'helper Dati di prestazione mediante la libreria delle prestazioni della scheda di inversione. Questo approccio consente ai client PDH, ad esempio Sysmon, di utilizzare i contatori delle prestazioni forniti da qualsiasi provider di alte prestazioni WMI esistente nel computer.

Sebbene sia installato per impostazione predefinita su Windows XP e Windows Server 2003, **Scheda WMI Performance** è un servizio manuale, cioè non viene eseguito automaticamente. Viene eseguito a richiesta quando un client delle prestazioni, ad esempio Sysmon, utilizza l'helper Dati di prestazione per richiedere informazioni. Quando il client si disconnette, il servizio si interrompe.

Se il servizio **Scheda WMI Performance** viene arrestato, i contatori delle prestazioni WMI non saranno disponibili.

#### Workstation

Il servizio **Workstation** è installato ed eseguito automaticamente su Windows XP e Windows Server 2003. Il servizio crea e gestisce connessioni e comunicazioni di rete per i client. Il servizio **Workstation** è un contenuto aggiuntivo in modalità utente per il redirector di reti Microsoft. Carica ed esegue funzioni di configurazione per il redirector, fornisce supporto nello stabilire connessioni di rete con server remoti, supporta le API WNet e fornisce dati statistici sul redirector.

Se il servizio **Workstation** viene arrestato, non è possibile stabilire connessioni con server remoti né accedere a file mediante named pipe. I client e i programmi non potranno accedere ai file e alle stampanti su altri computer remoti, ma la connettività TCP/HTTP non subirà conseguenze. L'esplorazione di Internet e l'accesso al client Web rimarranno funzionanti.

#### Servizio Pubblicazione sul Web

Il **servizio Pubblicazione sul Web** fornisce la connettività Web e funzionalità di amministrazione dei siti Web attraverso lo snap-in MMC IIS. Il servizio offre servizi HTTP per applicazioni su piattaforma Windows e contiene una funzionalità di gestione dei processi e una funzionalità di gestione della configurazione. La gestione dei processi controlla i processi in cui risiedono applicazioni personalizzate e siti Web semplici. La gestione della configurazione legge la configurazione del computer archiviata e assicura che Windows sia configurato per indirizzare le richieste HTTP ai pool di applicazioni o ai processi del sistema operativo appropriati.

Il servizio esegue un monitoraggio dei processi in cui risiedono applicazioni personalizzate e fornisce loro servizi di riciclo. Il riciclo è una proprietà di configurazione di un pool di applicazioni e può essere eseguito in base ai limiti di memoria, ai limiti di richiesta, all'ora di elaborazione o all'ora del giorno. Se le applicazioni personalizzate si bloccano, il servizio accoda le richieste HTTP e tenta di riavviare le applicazioni.

Questo servizio è un componente facoltativo che può essere installato in Windows Server 2003 o Windows XP come parte del pacchetto IIS. Se il **servizio Pubblicazione sul Web** viene arrestato, nel sistema operativo Windows Server 2003 non sarà possibile soddisfare alcuna richiesta Web.

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

I seguenti collegamenti forniscono ulteriori informazioni su alcune delle impostazioni trattate in questo capitolo:

-   Una descrizione dettagliata della configurazione e del blocco dei cluster dei server Windows esula dagli argomenti trattati in questa guida. Tuttavia, una guida approfondita è disponibile sull'articolo della Microsoft Knowledge Base n. 891597, "[Come applicare le impostazioni di protezione più restrittive su un server basato su Windows Server 2003 di cluster](http://support.microsoft.com/kb/891597/it)", all'indirizzo http://support.microsoft.com/kb/891597/it.

-   La Configurazione guidata impostazioni di sicurezza (SCW) di Windows Server 2003 contiene un database di configurazione con descrizioni e informazioni sui servizi disponibili in Windows Server 2003 e su molti altri prodotti server Microsoft. Per consultare questo database, è possibile installare il componente SCW su un computer Windows Server 2003 e avviarlo.

-   Un elenco di numerosi servizi Windows Server 2003 e delle relative informazioni sulle porte di rete è disponibile nell'articolo della Microsoft Knowledge Base "[Requisiti delle porte per il sistema di server Microsoft Windows](http://support.microsoft.com/kb/832017/it/it)" all'indirizzo http: //support.microsoft.com/kb/832017.

-   Il linguaggio SDDL è descritto dettagliatamente nell'articolo "[Security Descriptor Definition Language](http://msdn.microsoft.com/en-us/library/aa379567.aspx)" (in inglese) su MSDN all'indirizzo http://msdn.microsoft.com/library/en-us/secauthz/
    security/security\_descriptor\_definition\_language.asp.

-   Per ulteriori informazioni sulle impostazioni predefinite per i servizi di Windows Server 2003, vedere la pagina [Default settings for services](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/2b1dc6cf-2e34-4681-9aa6-8d0ffba2d3e3.mspx) su Microsoft Technet all'indirizzo www.microsoft.com/resources/documentation/windowsserv/2003/standard/proddocs/en-us/sys\_srv\_default\_settings.asp.

-   Per ulteriori informazioni su come ripristinare le impostazioni di protezione predefinite a livello locale, consultare l'articolo della Microsoft Knowledge Base “[How to: Reimpostare le opzioni di protezione predefinite](http://support.microsoft.com/kb/313222/it)” all'indirizzo http://support.microsoft.com/kb/313222/it.

-   Per ulteriori informazioni su come ripristinare le impostazioni di protezione predefinite negli oggetti dei criteri di gruppo integrati del dominio, consultare l'articolo della Microsoft Knowledge Base “[Reimpostazione dei diritti utente nei criteri di gruppo di dominio predefiniti in Windows Server 2003](http://support.microsoft.com/kb/324800/it)” a http://support.microsoft.com/kb/324800/it.

**Download**

[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)

[](#mainsection)[Inizio pagina](#mainsection)
