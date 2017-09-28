---
TOCTitle: Come configurare le tecnologie di protezione della rete di Windows XP SP2 in un ambiente Active Directory
Title: Come configurare le tecnologie di protezione della rete di Windows XP SP2 in un ambiente Active Directory
ms:assetid: 'b95d0f4a-e3a6-450b-b6b8-58514a8969eb'
ms:contentKeyID: 20213176
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700817(v=TechNet.10)'
---

Come configurare le tecnologie di protezione della rete di Windows XP SP2 in un ambiente Active Directory
=========================================================================================================

##### In questa pagina

[](#ekaa)[Introduzione](#ekaa)
[](#ejaa)[Operazioni preliminari](#ejaa)
[](#eiaa)[Aggiunta degli aggiornamenti rapidi alle workstation di gestione e a Windows Small Business Server 2003](#eiaa)
[](#ehaa)[Aggiornamento degli oggetti Criteri di gruppo esistenti](#ehaa)
[](#egaa)[Configurazione delle impostazioni del Centro sicurezza PC](#egaa)
[](#efaa)[Configurazione delle impostazioni di Windows Firewall](#efaa)
[](#eeaa)[Configurazione delle impostazioni di protezione di Internet Explorer](#eeaa)
[](#edaa)[Configurazione delle impostazioni di Gestione comunicazioni Internet](#edaa)
[](#ecaa)[Configurazione delle impostazioni di accesso DCOM](#ecaa)
[](#ebaa)[Configurazione delle impostazioni di RPC](#ebaa)
[](#eaaa)[Informazioni correlate](#eaaa)

### Introduzione

Le impostazioni di Criteri di gruppo vengono applicate in base all'implementazione di Microsoft Active Directory decisa dall'azienda e aiutano a proteggere l'ambiente informatico con impostazioni di configurazione standard per le varie categorie di utenti e di computer. Le nuove impostazioni di Criteri di gruppo di Microsoft Windows XP Service Pack 2 (SP2) per la protezione della rete includono:

-   **Windows Firewall**. Configurare queste impostazioni di criterio per attivare e disattivare il firewall, gestire le eccezioni relative a porte e programmi e definire le eccezioni per scenari specifici, ad esempio per consentire l'amministrazione remota dei computer di destinazione.

-   **Internet Explorer**. Grazie alle nuove impostazioni di criterio, è possibile configurare la protezione di Microsoft Internet Explorer. Inoltre, è possibile attivare o disattivare le funzionalità di protezione di Internet Explorer per diversi processi.

-   **Gestione comunicazioni Internet**. È possibile configurare queste impostazioni per controllare la modalità di comunicazione su Internet dei vari componenti di Windows XP SP2, relativamente alle attività che comportano lo scambio di informazioni tra i computer aziendali e Internet.

-   **Protezione DCOM**. È possibile configurare queste impostazioni per controllare le impostazioni di protezione per DCOM (Distributed Component Object Model). L'infrastruttura DCOM include nuove restrizioni per il controllo di accesso. Queste restrizioni contribuiscono a minimizzare i rischi di protezione derivanti dagli attacchi provenienti dalla rete.

-   **Centro sicurezza PC**. È possibile configurare queste impostazioni per amministrare in modo centralizzato il Centro sicurezza PC Windows. Il Centro sicurezza PC è una nuova funzionalità di Windows XP SP2 che consente di monitorare i computer dell'azienda per assicurarsi che siano conformi agli ultimi aggiornamenti del sistema di protezione e per avvisare gli utenti nel caso che un computer rappresenti un rischio per la protezione.

-   **RPC** **(Remote Procedure Call)**. È possibile configurare le impostazioni di criterio RPC per bloccare l'accesso remoto anonimo alle interfacce RPC del sistema e per impedire l'accesso anonimo all'interfaccia di mapping degli endpoint RPC.

In questo documento viene illustrato come distribuire le impostazioni di Criteri di gruppo per la protezione della rete, al fine di rendere sicuri i computer client di Windows XP SP2.

Per un elenco completo delle impostazioni consigliate, fare riferimento alle seguenti risorse:

-   "[Windows XP Security Guide Appendix A: Additional Guidance for Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35465)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35465

Le attività relative agli oggetti Criteri di gruppo (GPO) vengono eseguite in un dominio Active Directory. Alcune di queste attività possono essere eseguite da un controller di dominio ma, solitamente, vengono effettuate su un computer client Windows XP SP2 che contiene gli strumenti di gestione Active Directory.

**Nota:** per ulteriori informazioni su come distribuire i GPO, fare riferimento alle seguenti risorse:

-   "[Designing a Managed Environment: Staging Group Policy Deployments](http://technet.microsoft.com/en-us/library/cc757934.aspx)" sul sito Web Microsoft Windows Server System all'indirizzo http://go.microsoft.com/fwlink/?linkid=35498

Per configurare la protezione della rete in un ambiente Active Directory, è necessario effettuare le seguenti attività:

-   Aggiungere gli aggiornamenti rapidi alle workstation di gestione

-   Aggiornare i GPO esistenti

-   Configurare le impostazioni del Centro sicurezza PC

-   Configurare le impostazioni di Windows Firewall

-   Configurare le impostazioni di Internet Explorer

-   Configurare le impostazioni di Gestione comunicazioni Internet

-   Configurare le impostazioni di Protezione DCOM

-   Configurare le impostazioni di RPC

**IMPORTANTE:** le istruzioni contenute in questo documento sono state sviluppate a partire dal menu Start che viene visualizzato per impostazione predefinita quando si installa il sistema operativo. Se il menu Start è stato modificato, la procedura potrebbe essere leggermente diversa.

Per le definizioni dei termini relativi alla protezione, fare riferimento alle seguenti risorse:

-   "[Microsoft Security Glossary](http://go.microsoft.com/fwlink/?linkid=35468)" sul sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=35468

[](#mainsection)[Inizio pagina](#mainsection)

### Operazioni preliminari

Windows XP SP2 può essere utilizzato come client del dominio Windows in un dominio Active Directory con controller di dominio che eseguano qualsiasi edizione di:

-   Microsoft Windows Server 2003

-   Microsoft Windows Small Business Server 2003

-   Microsoft Windows 2000 Server SP3 o versione successiva    

Prima di installare gli aggiornamenti rapidi, è necessario avere effettuato il backup del computer, incluso il Registro di sistema.

Per ulteriori informazioni su come eseguire il backup del Registro di sistema, fare riferimento alle seguenti risorse:

-   [Microsoft Knowledge Base, articolo 322756](http://go.microsoft.com/fwlink/?linkid=36365) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=36365

[](#mainsection)[Inizio pagina](#mainsection)

### Aggiunta degli aggiornamenti rapidi alle workstation di gestione e a Windows Small Business Server 2003

Se si gestiscono le impostazioni degli oggetti Criteri di gruppo su computer con versioni precedenti del sistema operativo o del service pack (ad esempio, Windows XP con SP1 o Windows Server 2003), è necessario installare l'aggiornamento rapido KB842933 per far sì che le impostazioni di criterio vengano visualizzate correttamente nell'Editor oggetti Criteri di gruppo.

Se si sta utilizzando Small Business Server 2003 (SBS 2003), è necessario applicare anche l'aggiornamento rapido KB872769 poiché SBS 2003 disattiva Windows Firewall per impostazione predefinita. L'aggiornamento rapido risolve questo problema.

**Nota:** gli aggiornamenti rapidi elencati non sono inclusi in Windows Update e devono essere installati a parte. Gli aggiornamenti rapidi devono essere applicati su ogni singolo sistema interessato.

L'aggiornamento KB842933 riguarda:

-   Microsoft Windows Server 2003, Web Edition

-   Microsoft Windows Server 2003, Standard Edition

-   Microsoft Windows Server 2003, Enterprise Edition

-   Microsoft Windows Server 2003, 64-Bit Enterprise Edition

-   Microsoft Windows XP Professional SP1

-   Microsoft Windows Small Business Server 2003, Premium Edition

-   Microsoft Windows Small Business Server 2003, Standard Edition

-   Microsoft Windows 2000 Advanced Server

-   Microsoft Windows 2000 Server

-   Microsoft Windows 2000 Professional

L'aggiornamento KB872769 riguarda:

-   Microsoft Windows Small Business Server 2003, Standard Edition

-   Microsoft Windows Small Business Server 2003, Premium Edition

    **Nota:** per avere questi aggiornamenti rapidi e per ulteriori informazioni, fare riferimento alle seguenti risorse:

    -   [Microsoft Knowledge Base, articolo 842933](http://go.microsoft.com/fwlink/?linkid=35474) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35474

    -   [Microsoft Knowledge Base, articolo 872769](http://go.microsoft.com/fwlink/?linkid=35477) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35477

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere al computer client come membro del gruppo di protezione Amministratori di dominio o del gruppo di protezione Amministratori locali.

-   Strumenti: l'aggiornamento rapido scaricato, indicato per il sistema operativo in uso dalla Knowledge Base, articoli 842933 e 872769.

##### Aggiunta dell'aggiornamento rapido 842933 a Windows Small Business Server 2003, Windows 2000 Server SP3 o versione successiva, Windows XP SP1 o Windows Server 2003

**Per aggiungere l'aggiornamento rapido**

1.  Dal desktop di Windows, fare clic su **Start**, scegliere **Esegui**, digitare il percorso e il nome file dell'aggiornamento rapido scaricato, quindi fare clic su **OK**.

2.  Nella pagina **Installazione guidata di KB842933**, fare clic su **Avanti**.

3.  Nella pagina **Licenza**, fare clic su **Accetto**, quindi scegliere **Avanti**.

4.  Nella pagina **Completamento installazione guidata di KB842933**, per terminare l'installazione dell'aggiornamento rapido e riavviare il computer, fare clic su **Fine**.

5.  Ripetere i passaggi sopra illustrati per tutti i sistemi per i quali l'aggiornamento è indicato (server e workstation di gestione).

##### Aggiunta dell'aggiornamento rapido 872769 a Windows Small Business Server 2003

**Per aggiungere l'aggiornamento rapido**

1.  Dal desktop di Windows, fare clic su **Start**, scegliere **Esegui**, digitare il percorso e il nome file dell'aggiornamento rapido 872769 scaricato, quindi fare clic su **OK**.

2.  Nella pagina **Installazione guidata di KB872769**, fare clic su **Avanti**.

3.  Nella pagina **Licenza**, fare clic su **Accetto**, quindi scegliere **Avanti**.

4.  Nella pagina **Completamento installazione guidata di KB872769**, per terminare l'installazione dell'aggiornamento rapido e riavviare il computer, fare clic su **Fine**.

[](#mainsection)[Inizio pagina](#mainsection)

### Aggiornamento degli oggetti Criteri di gruppo esistenti

I modelli amministrativi di Windows XP SP2 presentano nuove impostazioni. Per configurare queste nuove impostazioni, è necessario aggiornare ogni GPO con i nuovi modelli amministrativi di Windows XP SP2. Se i GPO non sono aggiornati, le impostazioni relative a Windows Firewall non saranno disponibili.

È possibile aggiornare i GPO con Microsoft Management Console (MMC) con lo snap-in Editor oggetti Criteri di gruppo installato, su un computer con Windows XP SP2.

Una volta che un GPO è stato aggiornato, è possibile configurare le impostazioni per la protezione della rete più adatte ai computer Windows XP SP2 in uso.

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio o del gruppo di protezione Proprietari autori criteri di gruppo.

-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.

##### Aggiornamento degli oggetti Criteri di gruppo

**Per aggiornare gli oggetti Criteri di gruppo**

1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.

2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.

3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.

4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.

5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.

    ![](images/Cc700817.adprte01(it-it,TechNet.10).gif)

    **Figura 1   Ricerca oggetto Criteri di gruppo**

6.  Nella finestra di dialogo **Ricerca oggetto Criteri di gruppo**, selezionare l'oggetto Criteri di gruppo da aggiornare con le nuove impostazioni di Windows Firewall.

7.  Fare clic su **OK**, quindi scegliere **Fine** per chiudere la Procedura guidata Criteri di gruppo.

    In questo modo il nuovo modello amministrativo viene applicato al GPO selezionato.

8.  Nella finestra di dialogo **Aggiungi snap-in autonomo**, fare clic su **Chiudi**.

9.  Nella finestra di dialogo **Aggiungi/Rimuovi snap-in,** fare clic su **OK**.

10. Chiudere MMC. Se si fa clic su **File**, quindi si esce, non si salvano le modifiche alle impostazioni della console.

    **Nota:** sebbene non salvi le modifiche nella console, la procedura sopra illustrata importa nel GPO i nuovi modelli amministrativi di Windows XP SP2. I modelli devono essere importati in ogni GPO definito.

11. Ripetere i passaggi per ogni GPO utilizzato per applicare i Criteri di gruppo ai computer su cui è installato Windows XP SP2.

    **Nota: **per aggiornare i GPO per gli ambienti di rete che utilizzano Active Directory e Windows XP SP1, Microsoft consiglia la console Gestione criteri di gruppo, un download gratuito. Per ulteriori informazioni, fare riferimento alle seguenti risorse:

    -   "[Enterprise Management with the Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=35479)" sul sito Web Microsoft Windows Server System all'indirizzo http://go.microsoft.com/fwlink/?linkID=35479

[](#mainsection)[Inizio pagina](#mainsection)

### Configurazione delle impostazioni del Centro sicurezza PC

Il Centro sicurezza PC è un nuovo servizio di Windows XP SP2 che offre una posizione centrale da cui modificare le impostazioni di protezione, ottenere informazioni sulla protezione e assicurare che i computer degli utenti siano aggiornati con le impostazioni di protezione consigliate da Microsoft.

Nei domini Windows, è possibile utilizzare i Criteri di gruppo per attivare il Centro sicurezza PC e monitorare i computer degli utenti per assicurare che dispongano degli ultimi aggiornamenti del sistema di protezione e per avvisare gli utenti se i loro computer sono esposti a un potenziale rischio.

Il servizio Centro sicurezza PC viene eseguito come processo in background e controlla, sui computer degli utenti, lo stato dei componenti riportati di seguito:

-   **Firewall**. Il Centro sicurezza PC controlla se Windows Firewall è attivo o meno e, inoltre, verifica se sono presenti altri firewall software. Per controllare la presenza di altri firewall, il Centro sicurezza PC ricerca specifici provider di Strumentazione gestione Windows (WMI), resi disponibili dai produttori partecipanti.

-   **Protezione** **da virus**. Il Centro sicurezza PC controlla la presenza di software antivirus. Per controllare la presenza di software antivirus, il Centro sicurezza PC ricerca specifici provider di WMI, resi disponibili dai produttori partecipanti. Se sono disponibili le informazioni necessarie, il servizio Centro sicurezza PC determina anche se il software è aggiornato e se è attiva la scansione in tempo reale.

-   **Aggiornamenti** **automatici**. Il Centro sicurezza PC assicura che l'impostazione per Aggiornamenti automatici sia quella consigliata, che prevede il download e l'installazione automatici degli aggiornamenti critici sui computer degli utenti. Se la funzione Aggiornamenti automatici non è attiva o se la sua impostazione non è quella consigliata, il Centro sicurezza PC fornisce le raccomandazioni appropriate.

Se un componente risulta mancante o non conforme ai Criteri di protezione, il Centro sicurezza PC visualizza un'icona rossa nell'area di notifica della barra delle applicazioni e visualizza un messaggio di avviso al momento dell'accesso. Questo messaggio contiene i collegamenti per aprire l'interfaccia utente del Centro sicurezza PC, che fornisce tutte le informazioni sul problema e le raccomandazioni per risolverlo.

Per eseguire un firewall o software antivirus che non deve essere rilevato dal Centro sicurezza PC, è possibile impostare il Centro sicurezza PC in modo che eviti di generare avvisi relativi a tale componente.

È possibile utilizzare un'impostazione di Criteri di gruppo per gestire in modo centralizzato la funzionalità Centro sicurezza PC per i computer di un dominio Windows.

Se si attiva l'impostazione di criterio Attiva Centro sicurezza PC (solo computer in un dominio), il Centro sicurezza PC monitora le principali impostazioni di protezione (firewall, antivirus e aggiornamenti automatici) e avvisa gli utenti se il loro computer può essere a rischio. Per impostazione predefinita, l'impostazione di criterio Attiva Centro sicurezza PC (solo computer in un dominio) non è attivata, il che significa che viene disattivata quando viene disattivato il Centro sicurezza PC e che non sono visualizzate né le notifiche né la sezione dedicata allo stato del Centro sicurezza PC.

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo**.

-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.

##### Configurazione delle impostazioni del Centro sicurezza PC

Questa impostazione permette agli utenti dei computer con Windows XP SP2 di utilizzare il Centro sicurezza PC per gli avvisi relativi a firewall, software antivirus e aggiornamenti automatici.

**Per configurare le impostazioni del Centro sicurezza PC**

1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.

2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.

3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.

4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.

5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.

6.  Selezionare dall'elenco l'oggetto Criteri di gruppo da configurare. Fare clic su **OK**, quindi scegliere **Fine** per chiudere la Procedura guidata Criteri di gruppo.

7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo **Aggiungi snap-in autonomo**, quindi scegliere **OK** per uscire dalla finestra di dialogo **Aggiungi/Rimuovi snap-in** e tornare alla console di gestione.

8.  Nella struttura della console, aprire **Configurazione computer**, **Modelli amministrativi**, **Componenti di Windows** e, infine, **Centro sicurezza PC**.

    [![](images/Cc700817.adprte02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte02_big(it-it,technet.10).gif)

    **Figura 2   Impostazioni del Centro sicurezza PC**

9.  Fare doppio clic su **Attiva Centro sicurezza PC (solo computer in un dominio)**, scegliere **Attivato**, quindi fare clic su **OK**.

#### Applicazione della configurazione con GPUpdate

L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.

L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.

##### Esecuzione di GPUpdate

**Per eseguire GPUpdate**

1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.

    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:

    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504

3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.

    [![](images/Cc700817.adprte03(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte03_big(it-it,technet.10).gif)

    **Figura 3   GPUpdate dalla riga di comando**

4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.

#### Verifica dell'applicazione delle impostazioni del Centro sicurezza PC

**Per verificare che le impostazioni del Centro sicurezza PC siano applicate**

1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Pannello di controllo**.

2.  Sotto **Scegliere una categoria**, fare clic su **Centro sicurezza PC**.

3.  Verificare che il Centro sicurezza PC venga avviato.

    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:

    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481

[](#mainsection)[Inizio pagina](#mainsection)

### Configurazione delle impostazioni di Windows Firewall

Le impostazioni di Windows Firewall da configurare sono suddivise in tre insiemi:

-   **Consenti messaggi da computer con autenticazione IPSec**. Questa impostazione viene utilizzata quando un'azienda si avvale dell'IPSec (Internet Protocol Security) per proteggere il traffico e deve attivare Windows Firewall.

-   **Profilo di dominio**. Queste impostazioni vengono utilizzate dai computer quando questi sono connessi a una rete in cui si trovano i controller di dominio per il dominio di cui tali computer sono membri.

-   **Profilo standard**. Queste impostazioni vengono utilizzate dai computer quando questi non sono connessi a una rete, come nel caso dei computer laptop di cui si avvalgono gli utenti in viaggio.

Se le impostazioni del profilo standard non vengono configurate, i valori predefiniti rimangono invariati. Microsoft consiglia di configurare sia le impostazioni del profilo di dominio sia le impostazioni del profilo standard e di attivare Windows Firewall per entrambi i profili. L'unica eccezione è costituita dall'uso di un firewall host di un altro produttore.

Se è già in uso un firewall host di un altro produttore, Microsoft consiglia di disattivare Windows Firewall.

Se si decide di disattivare Windows Firewall sull'intera rete aziendale, costituita da un insieme di computer con Windows XP SP2, Windows XP SP1 e Windows XP senza service pack installati, è necessario configurare le seguenti impostazioni di Criteri di gruppo:

-   **Proibisci l'uso della Condivisione connessione Internet nella rete del dominio** impostata su **Attivata**

-   **Profilo di dominio – Windows Firewall: proteggi tutte le connessioni di rete** impostata su **Disattivata**

-   **Profilo standard – Windows Firewall: proteggi tutte le connessioni di rete** impostata su **Disattivata**

    **Nota:** questa impostazione del profilo standard assicura che Windows Firewall non venga utilizzato, indipendentemente dal fatto che i computer siano collegati o meno alla rete aziendale. Per assicurare che Windows Firewall non venga utilizzato nella rete aziendale, ma venga utilizzato quando i computer non sono collegati alla rete, cambiare l'impostazione in **Attivata**.

Le impostazioni del profilo standard sono generalmente più restrittive di quelle del profilo di dominio, poiché non includono le applicazioni e i servizi che vengono utilizzati solo in un ambiente di dominio gestito.

In un GPO, sia il profilo di dominio che il profilo standard contengono lo stesso insieme di impostazioni di Windows Firewall. Per applicare il profilo corretto, Windows XP SP2 si avvale del riconoscimento della rete.

**Nota:** per ulteriori informazioni sul riconoscimento della rete, fare riferimento alle seguenti risorse:

-   "[Network Determination Behavior for Network-Related Group Policy Settings](http://go.microsoft.com/fwlink/?linkid=35480)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35480

In questa sezione vengono descritte le possibili impostazioni di Windows Firewall in un GPO e le impostazioni consigliate per un ambiente Enterprise. Inoltre viene mostrato come attivare quattro tipi di impostazioni.

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo** modificato nel corso dell'attività precedente.

-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.

    **Nota:** per aprire un GPO si utilizza MMC con lo snap-in Editor oggetti Criteri di gruppo incluso o la console Utenti e computer di Active Directory. Per utilizzare la console Utenti e computer di Active Directory su un computer client Windows XP, è necessario eseguire adminpak.msi dal CD di Windows Server 2003.

##### Configurazione delle impostazioni di Windows Firewall con Criteri di gruppo

Per modificare le impostazioni di Windows Firewall nei GPO appropriati si utilizza lo snap-in Editor oggetti Criteri di gruppo o Utenti e computer di Active Directory.

Una volta che sono state configurate le impostazioni di Windows Firewall, il successivo aggiornamento del Criterio di gruppo Configurazione computer scarica le nuove impostazioni di Windows Firewall e le applica ai computer con Windows XP SP2.

**Per configurare le impostazioni di Windows Firewall**

1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.

2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.

3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.

4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.

5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.

6.  Selezionare l'oggetto Criteri di gruppo da configurare e fare clic su **OK**, quindi scegliere **Fine** per** **uscire dalla Procedura guidata Criteri di gruppo.

7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo Aggiungi snap-in autonomo, quindi scegliere **OK** per uscire dalla finestra di dialogo Aggiungi/Rimuovi snap-in e tornare alla console di gestione.

8.  Nella struttura della console, aprire **Configurazione computer**, **Modelli amministrativi**, **Rete**, **Connessioni di rete** e, infine, **Windows Firewall**.

    [![](images/Cc700817.adprte04(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte04_big(it-it,technet.10).gif)

    **Figura 4   Opzioni di Windows Firewall in un Criterio di gruppo**

9.  Fare doppio clic su **Windows Firewall: consenti messaggi da computer con autenticazione IPSec**.

    ![](images/Cc700817.adprte05(it-it,TechNet.10).gif)

    **Figura 5   Consenti messaggi da computer con autenticazione IPSec**

    Nella Tabella 1 sono riepilogate le opzioni di Consenti messaggi da computer con autenticazione IPSec.

    **Tabella 1   Impostazioni di Consenti messaggi da computer con autenticazione IPSec per un ambiente Enterprise**

<p> </p>
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Impostazione</p></th>
    <th><p>Descrizione</p></th>
    <th><p>Note</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Non configurata</strong></p></td>
    <td style="border:1px solid black;"><p>Il GPO non cambia la configurazione corrente di Windows Firewall</p></td>
    <td style="border:1px solid black;"><p> </p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Attivata</strong></p></td>
    <td style="border:1px solid black;"><p>Windows Firewall non elabora il traffico protetto da IPSec salvo quello proveniente dagli utenti o dai gruppi elencati nel criterio.</p></td>
    <td style="border:1px solid black;"><p>La sintassi per elencare gli utenti e i gruppi segue il linguaggio SDDL standard. Per ulteriori informazioni, fare riferimento alle seguenti risorse:</p>
    <p>&quot;<a href="http://go.microsoft.com/fwlink/?linkid=35503">Security Descriptor Definition Language</a>&quot; sul sito Web MSDN all'indirizzo http://go.microsoft.com/fwlink/?linkid=35503</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Disattivata</strong></p></td>
    <td style="border:1px solid black;"><p>Windows Firewall elabora il traffico protetto da IPSec.</p></td>
    <td style="border:1px solid black;"><p> </p></td>
    </tr>
    </tbody>
    </table>
  
10. In base alle informazioni riportate nella Tabella 1, fare clic su **Attivata** o **Disattivata**.
  
    **Nota:** se si fa clic su Attivata, è possibile creare l'elenco degli utenti o dei gruppi autorizzati a inviare traffico protetto da IPSec al computer in uso.
  
11. Fare clic su **OK**.    
  
12. Selezionare **Profilo di dominio** o **Profilo standard**.
  
    [![](images/Cc700817.adprte06(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte06_big(it-it,technet.10).gif)
  
    **Figura 6   Impostazioni di Windows Firewall in un Criterio di gruppo**
  
    Nella Tabella 2 sono riepilogate le impostazioni del Criterio di gruppo Windows Firewall consigliate per il profilo di dominio e per il profilo standard.
  
    **Tabella 2   Impostazioni di Windows Firewall consigliate per un ambiente Enterprise**

<p> </p>
    <table style="border:1px solid black;">
    <colgroup>
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Impostazione</p></th>
    <th><p>Descrizione</p></th>
    <th><p>Profilo di dominio</p></th>
    <th><p>Profilo standard</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Proteggi tutte le connessioni di rete</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica che in tutte le connessioni di rete deve essere attivato Windows Firewall</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Non consentire eccezioni</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica che tutto il traffico non richiesto deve essere ignorato, incluso il traffico elencato nelle eccezioni</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata, a meno che non sia necessario configurare eccezioni relative ai programmi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Definisci eccezioni programmi</strong></p></td>
    <td style="border:1px solid black;"><p>Definisce il traffico incluso nelle eccezioni in termini di nome file di programma</p></td>
    <td style="border:1px solid black;"><p>Attivata e configurata per i programmi (applicazioni e servizi) utilizzati dai computer che eseguono Windows XP SP2 sulla rete</p></td>
    <td style="border:1px solid black;"><p>Attivata e configurata per i programmi (applicazioni e servizi) utilizzati dai computer che eseguono Windows XP SP2 sulla rete</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Consenti eccezioni programmi locali</strong></p></td>
    <td style="border:1px solid black;"><p>Consente la configurazione locale delle eccezioni relative ai programmi</p></td>
    <td style="border:1px solid black;"><p>Disattivata, a meno che non sia necessario che gli amministratori locali configurino localmente le eccezioni relative ai programmi</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Consenti eccezione per amministrazione remota</strong></p></td>
    <td style="border:1px solid black;"><p>Consente la configurazione remota per mezzo degli appositi strumenti</p></td>
    <td style="border:1px solid black;"><p>Disattivata, a meno che non si desideri attivare l'amministrazione remota dei computer con gli snap-in di MMC</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Consenti eccezione per condivisione file e stampanti</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se è consentito il traffico di condivisione di file e stampanti</p></td>
    <td style="border:1px solid black;"><p>Disattivata, a meno che i computer con Windows XP SP2 non condividano risorse locali</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Consenti eccezioni ICMP</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica i tipi di messaggi ICMP consentiti</p></td>
    <td style="border:1px solid black;"><p>Disattivata, a meno che non si desideri utilizzare il comando ping per la risoluzione dei problemi</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Consenti eccezione per Desktop remoto</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se il computer può accettare una richiesta di connessione basata su Desktop remoto</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Consenti eccezione per framework UPnP</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se il computer può ricevere messaggi UPnP non richiesti</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Proibisci notifiche</strong></p></td>
    <td style="border:1px solid black;"><p>Disattiva le notifiche</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Consenti registrazione</strong></p></td>
    <td style="border:1px solid black;"><p>Consente di registrare il traffico e configurare le impostazioni del file registro</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Impedisci risposte unicast a richieste multicast o broadcast</strong></p></td>
    <td style="border:1px solid black;"><p>Elimina i pacchetti unicast ricevuti in risposta a messaggi di richieste multicast o broadcast</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Definisci eccezioni porte</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica il traffico incluso nelle eccezioni in termini di TCP e UDP</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Consenti eccezioni porte locali</strong></p></td>
    <td style="border:1px solid black;"><p>Consente la configurazione locale delle eccezioni relative alle porte</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    </tbody>
    </table>
  
##### Attivazione delle eccezioni per le porte
  
**Per attivare le eccezioni per le porte**
  
1.  Nell'area delle impostazioni di **Profilo di dominio** o **Profilo** **standard**, fare doppio clic su **Windows Firewall: definisci eccezioni porte**.
  
    ![](images/Cc700817.adprte07(it-it,TechNet.10).gif)
  
    **Figura 7   Proprietà di Windows Firewall: definisci eccezioni porte**
  
2.  Fare clic su **Attivata**, quindi scegliere **Mostra**.    
  
    [![](images/Cc700817.adprte08(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte08_big(it-it,technet.10).gif)
  
    **Figura 8   Mostra contenuti**
  
3.  Fare clic su **Aggiungi**.
  
    ![](images/Cc700817.adprte09(it-it,TechNet.10).gif)
  
    **Figura 9   Aggiungi elemento**
  
4.  Digitare le informazioni sulle porte da bloccare o attivare utilizzando la seguente sintassi:
  
    **porta:trasporto:ambito:stato:nome**
  
    Dove porta è il numero di porta, trasporto è TCP o UDP, ambito è \* (per tutti i sistemi) o un elenco dei computer autorizzati ad accedere alla porta, stato è enabled o disabled e nome è la stringa di testo utilizzata come etichetta per questa voce.
  
    Per l'ambito non sono supportati nomi host, nomi DNS (Domain Name System) o suffissi DNS. Per gli intervalli di indirizzi IPv4 è possibile specificare l'intervallo utilizzando una subnet mask decimale con punti o una lunghezza di prefisso. Se si utilizza una subnet mask decimale con punti, è possibile specificare l'intervallo come ID di rete IPv4 (ad esempio, 10.47.81.0/255.255.255.0) oppure utilizzare un indirizzo IPv4 compreso nell'intervallo (ad esempio, 10.47.81.231/255.255.255.0). Se si utilizza una lunghezza di prefisso di rete, è possibile specificare l'intervallo come ID di rete IPv4 (ad esempio, 10.47.81.0/24) oppure utilizzare un indirizzo IPv4 compreso nell'intervallo (ad esempio, 10.47.81.231/24).
  
    Per ulteriori informazioni sulle subnet e sugli indirizzi TCP/IP, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 164015](http://go.microsoft.com/fwlink/?linkid=36370) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=36370
  
    **Nota:** se sono presenti spazi tra le voci dell'elenco delle origini o altri caratteri non validi, l'ambito viene ignorato e l'impostazione si comporta come se fosse disattivata. Controllare con cura la sintassi dell'ambito prima di salvare le modifiche.
  
    In questo esempio viene utilizzata un'eccezione chiamata WebTest che attiva la porta TCP 80 per tutte le connessioni.
  
5.  Fare clic su **OK** per chiudere **Aggiungi elemento**.
  
    [![](images/Cc700817.adprte10(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte10_big(it-it,technet.10).gif)
  
    **Figura 10   Mostra contenuti**
  
6.  Fare clic su **OK** per chiudere **Mostra contenuti**.
  
7.  Fare clic su **Chiudi** per chiudere **Proprietà di Windows Firewall: definisci eccezioni porte**.
  
    **Nota:** se è selezionato **Non consentire eccezioni**, tutte le eccezioni relative alle porte vengono ignorate.
  
##### Attivazione delle eccezioni per i programmi
  
**Per attivare le eccezioni per i programmi**
  
1.  Nell'area delle impostazioni di **Profilo di dominio** o **Profilo** **standard**, fare doppio clic su **Windows Firewall: definisci eccezioni programmi**.
  
    ![](images/Cc700817.adprte11(it-it,TechNet.10).gif)
  
    **Figura 11   Proprietà di Windows Firewall: definisci eccezioni programmi**
  
2.  Fare clic su **Attivata**, quindi scegliere **Mostra**.
  
    [![](images/Cc700817.adprte12(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte12_big(it-it,technet.10).gif)
  
    **Figura 12   Mostra contenuti**
  
3.  Fare clic su **Aggiungi**.
  
    ![](images/Cc700817.adprte13(it-it,TechNet.10).gif)
  
    **Figura 13   Aggiungi elemento**
  
4.  Digitare le informazioni sui programmi da bloccare o attivare utilizzando la seguente sintassi:
  
    **percorso:ambito:stato:nome**
  
    Dove percorso è il percorso e nome file del programma, ambito è \* (per tutti i sistemi) o un elenco dei computer autorizzati ad accedere al programma, stato è enabled o disabled e nome è la stringa di testo utilizzata come etichetta per questa voce.
  
    In questo esempio si attiva Windows Messenger per tutte le connessioni.
  
    Per ulteriori informazioni sulle subnet e sugli indirizzi TCP/IP, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 164015](http://go.microsoft.com/fwlink/?linkid=36370) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=36370
  
5.  Fare clic su **OK** per chiudere **Aggiungi elemento**.
  
    [![](images/Cc700817.adprte14(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte14_big(it-it,technet.10).gif)
  
    **Figura 14   Mostra contenuti**
  
6.  Fare clic su **OK** per chiudere **Mostra contenuti**.
  
7.  Fare clic su **Chiudi** per chiudere **Proprietà di Windows Firewall: definisci eccezioni programmi**.
  
##### Configurazione delle opzioni ICMP di base
  
Per informazioni su ICMP, fare riferimento alle seguenti risorse:
  
-   "[Internet Control Message Protocol (ICMP)](http://technet.microsoft.com/en-us/library/cc758065.aspx)" sul sito Web Microsoft Windows XP all'indirizzo http://go.microsoft.com/fwlink/?linkid=35499
  
**Per configurare le opzioni ICMP di base**
  
1.  Nell'area delle impostazioni di **Profilo di dominio** o **Profilo standard**, fare doppio clic su **Windows Firewall: consenti eccezioni ICMP**.
  
2.  Fare clic su **Attivata**.
  
    ![](images/Cc700817.adprte15(it-it,TechNet.10).gif)
  
    **Figura 15   Proprietà di Windows Firewall: consenti eccezioni ICMP**
  
3.  Selezionare le eccezioni ICMP da attivare. In questo esempio viene selezionata Consenti richiesta echo in ingresso.
  
4.  Fare clic su **OK** per chiudere **Proprietà di Windows Firewall: consenti eccezioni ICMP**.
  
##### Registrazione dei pacchetti ignorati e delle connessioni riuscite
  
**Per registrare i pacchetti ignorati e le connessioni riuscite**
  
1.  Nell'area delle impostazioni di **Profilo di dominio** o **Profilo standard**, fare doppio clic su **Windows Firewall: consenti registrazione**.
  
    ![](images/Cc700817.adprte16(it-it,TechNet.10).gif)
  
    **Figura 16   Proprietà di Windows Firewall: consenti registrazione**
  
2.  Fare clic su **Attivata**, selezionare **Registra pacchetti ignorati** e **Registra connessioni riuscite**, digitare un percorso e un nome per il file registro, quindi scegliere **OK**.
  
    **Nota:** il percorso in cui viene salvato il file registro deve essere protetto al fine di impedire l'eliminazione o la manomissione del file.
  
3.  Chiudere l'Editor criteri di gruppo.
  
4.  Alla richiesta di salvataggio delle impostazioni della console, fare clic su **No**.
  
#### Applicazione della configurazione con GPUpdate
  
L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.
  
L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.
  
##### Esecuzione di GPUpdate
  
**Per eseguire GPUpdate**
  
1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.
  
2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.
  
    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504
  
3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.
  
    [![](images/Cc700817.adprte17(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte17_big(it-it,technet.10).gif)
  
    **Figura 17   GPUpdate dalla riga di comando**
  
4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.
  
#### Verifica dell'applicazione delle impostazioni di Windows Firewall
  
**Nota:** se si utilizza Criteri di gruppo per configurare Windows Firewall, è possibile che le impostazioni non consentano agli amministratori locali di modificare alcuni elementi della configurazione. Alcune schede e alcune opzioni della finestra di dialogo Windows Firewall non sono disponibili sui computer locali degli utenti.
  
**Per verificare che le impostazioni di Windows Firewall siano applicate**
  
1.  Dal **Centro sicurezza PC**, sotto **Gestione impostazioni di protezione per**, fare clic su **Windows Firewall**.
  
2.  Fare clic sulle schede **Generale**, **Eccezioni** e **Avanzate** e verificare che la configurazione desiderata sia applicata a Windows Firewall sul computer, quindi scegliere **OK** per chiudere Windows Firewall.
  
    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:
  
    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione delle impostazioni di protezione di Internet Explorer
  
Per Windows XP SP2, è possibile gestire tutte le impostazioni di protezione di Internet Explorer sia per la configurazione computer che per la configurazione utente con le nuove impostazioni di Criteri di gruppo.
  
Windows XP SP2 utilizza due aree principali di impostazioni di criterio:
  
-   Funzionalità di protezione
  
-   Azioni URL
  
Le impostazioni di criterio Funzionalità di protezione consentono di gestire scenari specifici che potrebbero influire sulla protezione di Internet Explorer. Nella maggior parte dei casi, è importante impedire un comportamento specifico; per questo motivo, è necessario assicurare che la funzionalità di protezione sia attivata. Ad esempio, è possibile che un codice dannoso in esecuzione nell'area Computer locale anziché nell'area Internet tenti di aumentare il livello delle proprie autorizzazioni. Per cercare di impedire un attacco di questo tipo, è possibile utilizzare l'impostazione di criterio Protezione da promozione di area.
  
Per ognuna delle impostazioni di criterio Funzionalità di protezione, è possibile specificare le impostazioni per controllare il comportamento delle funzionalità di protezione, in base a quanto segue:
  
-   Processi di Internet Explorer
  
-   Un elenco di processi definiti
  
-   Tutti i processi, indipendentemente dalla loro origine
  
Per azione URL (Uniform Resource Locator) si intende un'azione che il browser può intraprendere e che può comportare rischi di protezione per il computer locale, ad esempio il tentativo di eseguire un applet Java o un controllo ActiveX. Le azioni URL corrispondono a quelle impostazioni di protezione del Registro di sistema che identificano l'azione da intraprendere per tale funzionalità nell'area di protezione in cui risiede l'URL. Le impostazioni delle azioni URL includono attivazione, disattivazione, richiesta e così via, a seconda dei casi.
  
Per la gestione della protezione delle azioni URL in Internet Explorer, è necessario utilizzare le nuove impostazioni del Criterio di gruppo Pagina protezione sotto **Pannello di controllo Internet**. Utilizzando Criteri di gruppo per controllare la protezione per le azioni URL, è possibile creare configurazioni standard di Internet Explorer per tutti gli utenti e i computer dell'azienda.
  
Per garantire la protezione, è possibile attivare criteri per tutte le aree URL con le impostazioni di criterio del modello dell'area di protezione. Per ognuna delle impostazioni di criterio delle azioni URL, è possibile specificare uno dei seguenti livelli di protezione:
  
-   **Bassa**. Generalmente utilizzato per le aree di protezione URL che contengono siti Web considerati assolutamente attendibili dagli utenti. È il livello di protezione predefinito per l'area Siti attendibili.
  
-   **Medio-bassa**. Può essere utilizzato per le aree di protezione URL che contengono siti Web che difficilmente potrebbero danneggiare computer o dati. È il livello di protezione predefinito per l'area Intranet.
  
-   **Media**. Può essere utilizzato per le aree di protezione URL che contengono siti Web che non sono né attendibili ne inattendibili. È il livello di protezione predefinito per l'area Internet.
  
-   **Alta**. Utilizzato per le aree di protezione URL che contengono siti Web che potrebbero potenzialmente danneggiare computer o dati. È il livello di protezione predefinito per l'area Siti con restrizioni.
  
Per ulteriori informazioni sui controlli di Funzionalità di protezione, fare riferimento alle seguenti risorse:
  
-   "[Changes in Functionality in Microsoft Windows XP Service Pack 2](http://technet.microsoft.com/en-us/library/bb878160.aspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35487
  
#### Requisiti per l'esecuzione di questa attività
  
-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo**.
  
-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.
  
##### Configurazione delle impostazioni di protezione di Internet Explorer
  
**Per configurare le impostazioni di Internet Explorer**
  
1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.
  
3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.
  
4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.
  
5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.
  
6.  Selezionare l'oggetto Criteri di gruppo da configurare e fare clic su **OK**, quindi scegliere **Fine** per** **uscire dalla Procedura guidata Criteri di gruppo.
  
7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo **Aggiungi snap-in autonomo**, quindi scegliere OK per uscire dalla finestra di dialogo Aggiungi/Rimuovi snap-in e tornare alla console di gestione.
  
8.  Nella struttura della console, aprire **Configurazione computer**, **Modelli amministrativi**, **Componenti di Windows**, **Internet Explorer** e, infine, **Funzionalità di protezione**.
  
    [![](images/Cc700817.adprte18(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte18_big(it-it,technet.10).gif)
  
    **Figura 18   Impostazioni di protezione del Criterio di gruppo Internet Explorer**
  
9.  In base alle informazioni riportate nella Tabella 3, configurare le impostazioni di protezione di Internet Explorer.
  
    **Tabella 3   Impostazioni delle funzionalità di protezione di Internet Explorer**

<p> </p>
    <table style="border:1px solid black;">
    <colgroup>
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Impostazione</p></th>
    <th><p>Descrizione</p></th>
    <th><p>Configurazione predefinita</p></th>
    <th><p>Configurazione consigliata per un ambiente Enterprise</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Restrizione di protezione comportamenti binari</strong></p></td>
    <td style="border:1px solid black;"><p>Controlla se l'impostazione Restrizione di protezione comportamenti binari è negata o consentita</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Aggiungere i comportamenti approvati dall'azienda all'elenco Comportamenti approvati da amministratori nella notazione #pacchetto#comportamento</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Limitazione protocollo di protezione MK</strong></p></td>
    <td style="border:1px solid black;"><p>Riduce i rischi di sicurezza non consentendo il protocollo MK</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Blocco protezione area computer locale</strong></p></td>
    <td style="border:1px solid black;"><p>Aiuta a limitare gli attacchi che utilizzano l'area Computer locale per caricare codice HTML dannoso</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Gestione MIME coerente</strong></p></td>
    <td style="border:1px solid black;"><p>Determina se Internet Explorer richiede che tutte le informazioni sul tipo file fornite dai server Web siano coerenti</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Funzionalità di protezione analisi MIME</strong></p></td>
    <td style="border:1px solid black;"><p>Determina se l'analisi MIME di Internet Explorer deve impedire che un file di un certo tipo sia promosso a un tipo di file più pericoloso</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Protezione cache oggetti</strong></p></td>
    <td style="border:1px solid black;"><p>Definisce se un riferimento a un oggetto è accessibile quando l'esplorazione dell'utente si limita all'interno di un dominio o raggiunge un nuovo dominio</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Restrizioni di protezione finestre impostate da script</strong></p></td>
    <td style="border:1px solid black;"><p>Limita le finestre popup e impedisce agli script di visualizzare finestre in cui la barra del titolo e la barra di stato non sono visibili o coprono la barra del titolo o la barra di stato di altre finestre</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Protezione da promozione di area</strong></p></td>
    <td style="border:1px solid black;"><p>Aiuta a proteggere l'area di protezione Computer locale</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Barra informazioni</strong></p></td>
    <td style="border:1px solid black;"><p>Indica se deve essere visualizzata la barra informazioni per i processi di Internet Explorer quando le installazioni di file o di codice sono sottoposte a restrizioni</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Limita installazione ActiveX</strong></p></td>
    <td style="border:1px solid black;"><p>Consente di bloccare la richiesta di conferma dell'installazione di controlli ActiveX® per i processi di Internet Explorer</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Limita download file</strong></p></td>
    <td style="border:1px solid black;"><p>Consente di bloccare le richieste di conferma di download di file non originate dall'utente</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i processi</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Gestione componenti aggiuntivi</strong></p></td>
    <td style="border:1px solid black;"><p>Consente di assicurare che i componenti aggiuntivi di Internet Explorer non presenti nell'Elenco componenti aggiuntivi non siano consentiti</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attivata per tutti i componenti aggiuntivi a meno che non sia specificato diversamente nell'Elenco componenti aggiuntivi</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Blocco protocollo di rete</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica un elenco di protocolli con restrizioni per le seguenti aree di protezione: Internet, intranet, siti attendibili, siti con restrizioni e computer locale</p></td>
    <td style="border:1px solid black;"><p>Non configurata</p></td>
    <td style="border:1px solid black;"><p>Attiva protocolli specifici per ogni area di protezione</p></td>
    </tr>
    </tbody>
    </table>
  
10. Espandere il **Pannello di controllo Internet**
  
    [![](images/Cc700817.adprte19(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte19_big(it-it,technet.10).gif)
  
    **Figura 19   Impostazioni del Pannello di controllo Internet**
  
11. Attivare ogni impostazione per impedire che gli utenti possano accedere alle pagine di configurazione di Internet Explorer elencate. A tale scopo, fare doppio clic su ogni impostazione, fare clic su **Attivata**, quindi scegliere **OK**.
  
12. Espandere la **Pagina protezione**.
  
    [![](images/Cc700817.adprte20(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte20_big(it-it,technet.10).gif)
  
    **Figura 20   Impostazioni della Pagina protezione del Pannello di controllo Internet**
  
13. Esistono due modi per configurare le aree di protezione: utilizzare i modelli o scegliere ogni singola impostazione per le varie aree.  
    Effettuare una delle seguenti operazioni:
  
    -   In base alle informazioni riportate nella Tabella 4, utilizzare i modelli di area per configurare ogni area di protezione. Fare doppio clic su ogni opzione di modello, quindi selezionare **Attivata**.
  
        Oppure
  
    -   In base alle informazioni riportate nella Tabella 5, configurare ogni area di protezione separatamente.
  
        **Tabella 4   Impostazioni del Pannello di controllo Internet per area di protezione**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Impostazione</p></th>
        <th><p>Configurazione consigliata</p></th>
        <th><p>Livello consigliato</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Modello area Internet</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Media</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Modello area Intranet</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Medio-bassa</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Modello area siti attendibili</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Bassa</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Modello area siti con restrizioni</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Alta</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Modello area computer locale</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Bassa</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Modello Area computer locale bloccata</strong></p></td>
        <td style="border:1px solid black;"><p>Attivata</p></td>
        <td style="border:1px solid black;"><p>Alta</p></td>
        </tr>
        </tbody>
        </table>
  
        **Tabella 5   Impostazioni del Pannello di controllo Internet per area di protezione**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Impostazione</p></th>
        <th><p>Descrizione</p></th>
        <th><p>Configurazione predefinita</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Scarica controlli ActiveX con firma elettronica</strong></p></td>
        <td style="border:1px solid black;"><p>Gestisce il download dei controlli ActiveX con firma elettronica dall'area URL della pagina HTML che contiene il controllo.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Scarica controlli ActiveX senza firma elettronica</strong></p></td>
        <td style="border:1px solid black;"><p>Gestisce il download dei controlli ActiveX senza firma elettronica dall'area URL della pagina HTML che contiene il controllo.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Inizializza e esegui script controlli ActiveX non contrassegnati come sicuri</strong></p></td>
        <td style="border:1px solid black;"><p>Gestisce l'esecuzione dei controlli e dei plug-in ActiveX dalle pagine HTML dell'area.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Esegui controlli e plug-in ActiveX</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se la protezione dell'oggetto controllo ActiveX viene ignorata o applicata per le pagine dell'area di protezione dell'URL. La protezione dell'oggetto dovrebbe essere ignorata solo se si è sicuri che tutti i controlli ActiveX e gli script che potrebbero interagire con essi nelle pagine dell'area non costituiscono un pericolo per la protezione. Aggregato dei flag URLACTION_ACTIVEX_OVERRIDE_DATA_SAFETY e URLACTION_ACTIVEX_OVERRIDE_SCRIPT_SAFETY.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Consenti esecuzione script attivo</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se eseguire o meno il codice script nelle pagine dell'area di protezione URL.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Esecuzione script delle applet Java</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se il codice script nelle pagine HTML dell'area di protezione URL può utilizzare le applet Java se le proprietà, i metodi e gli eventi delle applet sono accessibili da parte degli script.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Esegui script controllo ActiveX contrassegnati come sicuri</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se è possibile utilizzare gli script per i controlli ActiveX sicuri.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Accesso all'origine dati a livello di dominio</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se la risorsa è autorizzata ad accedere alle origini dati dei vari domini.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Consenti operazioni di copia tramite script</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se gli script possono eseguire operazioni di copia e incolla.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Invia dati modulo non crittografati</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se sono consentiti i moduli HTML contenuti nelle pagine dell'area di protezione URL o inviati ai server dell'area. Aggregato dei flag URLACTION_HTML_SUBMIT_FORMS_FROM e URLACTION_HTML_SUBMIT_FORMS_TO.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Consenti download dei caratteri</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se sono consentiti i download dei caratteri HTML.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Persistenza dati utente</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se la persistenza dei dati dell'utente è attivata.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>Esplora sottoframe in domini diversi</strong></p></td>
        <td style="border:1px solid black;"><p>Determina se i sottoframe sono autorizzati a navigare nei vari domini.</p></td>
        <td style="border:1px solid black;"><p>Non configurata</p></td>
        </tr>
        </tbody>
        </table>
  
#### Applicazione della configurazione con GPUpdate
  
L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.
  
L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.
  
##### Esecuzione di GPUpdate
  
**Per eseguire GPUpdate**
  
1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.
  
2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.
  
    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504
  
3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.
  
    [![](images/Cc700817.adprte21(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte21_big(it-it,technet.10).gif)
  
    **Figura 21   GPUpdate dalla riga di comando**
  
4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.
  
#### Verifica dell'applicazione delle impostazioni di protezione di Internet Explorer
  
**Nota:** se si utilizza Criteri di gruppo per configurare Internet Explorer, è possibile che le impostazioni non consentano agli amministratori locali di modificare alcuni elementi della configurazione. Alcune schede e alcune opzioni delle finestre di dialogo non sono disponibili sui computer locali degli utenti.
  
##### Verifica dell'applicazione delle impostazioni di protezione di Internet Explorer
  
**Per verificare che le impostazioni di Internet Explorer siano applicate**
  
1.  Dal **Centro sicurezza PC**, sotto **Gestione impostazioni di protezione per**, fare clic su **Opzioni Internet**.
  
2.  Fare clic sulle schede **Protezione**, **Privacy** e **Avanzate** e verificare che la configurazione desiderata sia applicata a Internet Explorer sul computer, quindi scegliere **OK** per chiudere Proprietà Internet.
  
    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:
  
    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione delle impostazioni di Gestione comunicazioni Internet
  
Windows XP SP2 fornisce nuove impostazioni per Criteri di gruppo, progettate principalmente per controllare il modo in cui i componenti di Windows XP SP2 comunicano con Internet. Le impostazioni di Criteri di gruppo consentono di:
  
-   Ordinare stampe fotografiche su Internet
  
-   Utilizzare spazio di archiviazione su Internet
  
-   Pubblicare sul Web
  
In Windows XP SP2, gli utenti possono selezionare le attività di Windows Explorer per ordinare stampe fotografiche in linea (**Ordinazione guidata di stampe via Internet**), iscriversi a un servizio che offre spazio di archiviazione in linea (**Aggiunta guidata risorse di rete)** o pubblicare file che possono essere visualizzati in un browser (**Pubblicazione guidata sul Web**), nonché selezionare altre attività. L'attività o la procedura guidata selezionata richiama i nomi e gli URL di questi provider di servizi da due origini diverse: un elenco locale (archiviato nel Registro di sistema) e un elenco archiviato in un sito Web Microsoft. Per impostazione predefinita, Windows visualizza i provider dell'elenco del sito Web Microsoft in aggiunta a quelli elencati nel Registro di sistema.
  
È possibile utilizzare le seguenti impostazioni di Criteri di gruppo per controllare la modalità di funzionamento di queste procedure guidate e di queste attività e per controllare la modalità di comunicazione di questi componenti con Internet:
  
-   **Disattiva l'operazione per file e cartelle Pubblica sul Web**. Questa impostazione di criterio specifica se le attività necessarie per pubblicare gli elementi sul Web sono disponibili da Operazioni file e cartella nelle cartelle di Windows. Le attività sono: Pubblica file sul Web, Pubblica cartella sul Web e Pubblica elementi selezionati sul Web.
  
-   **Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet**. Questa impostazione di criterio specifica se Windows deve scaricare un elenco di provider da **Pubblicazione guidata sul Web**, **Aggiunta guidata risorse di rete** e **Ordinazione guidata di stampe via Internet**. Per impostazione predefinita, Windows visualizza i provider scaricati dal sito Web Microsoft in aggiunta a quelli elencati nel Registro di sistema.
  
-   **Disattiva l'operazione immagine Ordina stampe**. Questa impostazione di criterio specifica se l'attività Ordina stampe via Internet è disponibile da Operazioni immagine nelle cartelle di Windows. Questa impostazione disattiva l'Ordinazione guidata di stampe via Internet.
  
Queste impostazioni di criterio sono disponibili sia per Configurazione utente che per Configurazione computer.
  
Per ulteriori informazioni su come controllare l'uso dell'Aggiunta guidata risorse di rete e della Pubblicazione guidata sul Web, fare riferimento alle seguenti risorse:
  
-   "[Using Windows XP Professional with Service Pack 2 in a Managed Environment: Controlling Communication with the Internet](http://technet.microsoft.com/en-us/library/cc507837.aspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?LinkId=35489
  
#### Requisiti per l'esecuzione di questa attività
  
-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo**.
  
-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.
  
##### Configurazione delle impostazioni di Gestione comunicazioni Internet
  
**Per configurare le impostazioni di Gestione comunicazioni Internet**
  
1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.
  
3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.
  
4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.
  
5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.
  
6.  Selezionare l'oggetto Criteri di gruppo da configurare e fare clic su **OK**, quindi scegliere **Fine** per** **uscire dalla Procedura guidata Criteri di gruppo.
  
7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo **Aggiungi snap-in autonomo**, quindi scegliere OK per uscire dalla finestra di dialogo Aggiungi/Rimuovi snap-in e tornare alla console di gestione.
  
8.  Nella struttura della console, aprire **Configurazione computer**, **Modelli amministrativi**, **Sistema** e, infine, **Gestione comunicazioni Internet**.
  
    [![](images/Cc700817.adprte22(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte22_big(it-it,technet.10).gif)
  
    **Figura 22   Impostazioni di Gestione comunicazioni Internet**
  
9.  Configurare l'impostazione **Limita comunicazioni Internet** come **Disattivata** per disattivare tutte le impostazioni sotto Impostazioni di comunicazione Internet, oppure come **Attivata** per attivarle.
  
10. Per configurare ogni singola impostazione, espandere **Impostazioni di comunicazione Internet**, quindi basarsi sulle informazioni contenute nella Tabella 6 per configurare le impostazioni.
  
    **Tabella 6   Impostazioni di comunicazione Internet consigliate**

<p> </p>
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Impostazione</p></th>
    <th><p>Descrizione</p></th>
    <th><p>Impostazione consigliata</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Disattiva l'operazione per file e cartelle Pubblica sul Web</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se le attività Pubblica file sul Web, Pubblica cartella sul Web e Pubblica elementi selezionati sul Web sono disponibili da Operazioni file e cartella nelle cartelle di Windows</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet</strong></p></td>
    <td style="border:1px solid black;"><p>Controlla se Windows scarica un elenco di provider nelle procedure guidate di pubblicazione sul Web e ordinazione via Internet</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Disattiva Analisi utilizzo software Windows Messenger</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se Windows Messenger raccoglie informazioni anonime sull'uso del software e del servizio Windows Messenger</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Disattiva aggiornamenti file contenuto Ricerca guidata</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se Ricerca guidata deve scaricare automaticamente gli aggiornamenti del contenuto durante le ricerche locali e in Internet</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Disattiva stampa su HTTP</strong></p></td>
    <td style="border:1px solid black;"><p>Consente di disattivare la stampa su HTTP dal client</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;"><p><strong>Disattiva download driver di stampa su HTTP</strong></p></td>
    <td style="border:1px solid black;"><p>Controlla se il computer può scaricare i pacchetti dei driver di stampa su HTTP</p></td>
    <td style="border:1px solid black;"><p>Attivata</p></td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;"><p><strong>Disattiva ricerca driver periferiche in Windows Update</strong></p></td>
    <td style="border:1px solid black;"><p>Specifica se Windows ricerca in Windows Update i driver di periferica se non sono presenti driver locali per una periferica</p></td>
    <td style="border:1px solid black;"><p>Disattivata</p></td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** nella Tabella 6 sono riportate tutte le Impostazioni di comunicazione Internet consigliate.
  
#### Applicazione della configurazione con GPUpdate
  
L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.
  
L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.
  
##### Esecuzione di GPUpdate
  
**Per eseguire GPUpdate**
  
1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.
  
2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.
  
    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504
  
3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.
  
    [![](images/Cc700817.adprte23(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte23_big(it-it,technet.10).gif)
  
    **Figura 23   GPUpdate dalla riga di comando**
  
4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.
  
#### Verifica dell'applicazione delle impostazioni di Gestione comunicazioni Internet
  
**Per verificare che le impostazioni di Gestione comunicazioni Internet siano applicate**
  
1.  Fare clic sul pulsante **Start**, quindi scegliere **Immagini**.
  
2.  Verificare che sotto **Operazioni immagine** non sia visualizzato **Ordina stampe via Internet**.
  
3.  Verificare che sotto **Operazioni file e cartella** non sia visualizzato **Pubblica cartella sul Web**.
  
4.  Chiudere **Immagini**.
  
    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:
  
    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione delle impostazioni di accesso DCOM
  
Microsoft Component Object Model (COM) è un sistema per la creazione di applicazioni software in grado di interagire tra loro. DCOM consente la distribuzione di queste applicazioni. Il protocollo wire DCOM fornisce in modo trasparente il supporto per le comunicazioni tra i componenti COM.
  
**Nota:** per ulteriori informazioni sulla protezione DCOM, fare riferimento alle seguenti risorse:
  
-   "[Best Practices for Mitigating RPC and DCOM Vulnerabilities"](http://www.microsoft.com/technet/security/alerts/info/bpdcom.mspx) sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=36371
  
Molte applicazioni COM includono codice specifico per la protezione ma utilizzano impostazioni deboli che spesso consentono l'accesso non autenticato ai componenti. In Windows XP SP2, è stata apportata una modifica a COM per fornire controlli di accesso a livello di intero computer, al fine di regolare l'accesso a tutte le richieste di richiamo, attivazione o avvio di quest'ultimo. Windows XP SP2 offre uno standard di autorizzazione minimo che deve essere superato per accedere a qualsiasi server COM sul computer.
  
**Nota:** per ulteriori informazioni sulle correzioni a COM in Windows XP SP2, fare riferimento alle seguenti risorse:
  
-   **"**[Com+ fixes in Windows XP Service Pack 2](http://support.microsoft.com/default.aspx?scid=kb;en-us;838211)" all'indirizzo http://support.microsoft.com/default.aspx?scid=kb;en-us;838211
  
Gli elenchi di controllo di accesso (ACL) vengono controllati per ogni richiesta DCOM. Se il controllo non viene superato, la richiesta viene negata. Esiste un ACL a livello di intero computer per:
  
-   **Autorizzazioni di esecuzione e attivazione**. Queste autorizzazioni controllano il permesso di avviare un server COM durante l'attivazione COM se il server non è già in esecuzione e prevedono quattro diritti di accesso:
  
    -   Avvio locale
  
    -   Avvio remoto
  
    -   Attivazione locale
  
    -   Attivazione remota
  
-   **Autorizzazioni di accesso**. Queste autorizzazioni controllano il permesso di richiamare un server COM in esecuzione e prevedono due diritti di accesso:
  
    -   Chiamate locali
  
    -   Chiamate remote
  
        **Nota: **un messaggio COM locale arriva tramite una chiamata locale, mentre un messaggio COM remoto arriva tramite una chiamata remota.
  
Le autorizzazioni possono essere configurate tramite Servizi componenti di Microsoft Management Console (MMC) e offrono uno standard di protezione minimo che deve essere superato, indipendentemente dalle impostazioni della specifica applicazione server COM.
  
**Nota:** per impostazione predefinita, Windows Firewall blocca questo snap-in di MMC su un computer con Windows XP SP2; se si riceve un avviso di protezione relativo a questa situazione, è necessario fare clic su **Sblocca**.
  
Le impostazioni di restrizione predefinite di Windows XP SP2 sono riportate nella Tabella 7.
  
**Tabella 7   Restrizioni predefinite del controllo di accesso DCOM**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Autorizzazione</p></th>
<th><p>Amministratore</p></th>
<th><p>Tutti</p></th>
<th><p>Anonimo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Avvio e attivazione</p></td>
<td style="border:1px solid black;"><p>Avvio locale</p>
<p>Attivazione locale</p>
<p>Avvio remoto</p>
<p>Attivazione remota</p></td>
<td style="border:1px solid black;"><p>Avvio locale</p>
<p>Attivazione locale</p></td>
<td style="border:1px solid black;"><p>Nessuna autorizzazione impostata</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Accesso</p></td>
<td style="border:1px solid black;"><p>Nessuna autorizzazione impostata</p></td>
<td style="border:1px solid black;"><p>Chiamate locali</p>
<p>Chiamate remote</p></td>
<td style="border:1px solid black;"><p>Chiamate locali</p></td>
</tr>
</tbody>
</table>
  
Le impostazioni predefinite permettono il funzionamento di tutti gli scenari locali senza dover modificare il software o il sistema operativo. Le impostazioni predefinite attivano anche la maggior parte degli scenari client COM e disattivano le attivazioni remote da parte di utenti diversi dagli amministratori per i server COM installati.
  
Se si implementa un server COM e si intende supportare l'attivazione remota da parte di un client COM non amministrativo o le chiamate remote non autenticate, è necessario modificare la configurazione predefinita per questa funzionalità.
  
**Nota: **sebbene questo documento spieghi come modificare le impostazioni predefinite, occorre tenere presente che tale modifica comporta sempre un aumento della vulnerabilità del computer agli attacchi.
  
#### Requisiti per l'esecuzione di questa attività
  
-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo**.
  
-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.
  
##### Configurazione delle impostazioni DCOM
  
**Per configurare le impostazioni DCOM**
  
1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.
  
3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.
  
4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.
  
5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.
  
6.  Selezionare l'oggetto Criteri di gruppo da configurare e fare clic su **OK**, quindi scegliere **Fine** per** **uscire dalla Procedura guidata Criteri di gruppo.
  
7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo **Aggiungi snap-in autonomo**, quindi scegliere OK per uscire dalla finestra di dialogo Aggiungi/Rimuovi snap-in e tornare alla console di gestione.
  
8.  Nella struttura della console, aprire **Configurazione computer**, **Impostazioni di Windows, Impostazioni protezione**, **Criteri locali** e, infine, **Opzioni di protezione**.
  
    [![](images/Cc700817.adprte24(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte24_big(it-it,technet.10).gif)
  
    **Figura 24   Opzioni di protezione**
  
9.  Fare doppio clic su **DCOM: restrizioni accesso computer nella sintassi Security Descriptor Definition Language (SDDL)**.
  
    **Nota:** per ulteriori informazioni sul linguaggio SDDL, fare riferimento alle seguenti risorse:
  
    -   "[Security Descriptor Definition Language](http://go.microsoft.com/fwlink/?linkid=35503)" sul sito Web MSDN all'indirizzo http://go.microsoft.com/fwlink/?linkid=35503
  
    ![](images/Cc700817.adprte25(it-it,TechNet.10).gif)
  
    **Figura 25   DCOM: restrizioni accesso computer**
  
10. Fare clic su **Modifica protezione**.
  
    ![](images/Cc700817.adprte26(it-it,TechNet.10).gif)
  
    **Figura 26   Autorizzazioni di accesso**
  
11. Per concedere l'accesso a tutti i computer a utenti particolari delle applicazioni DCOM all'interno dell'azienda, fare clic su **Aggiungi**.
  
    ![](images/Cc700817.adprte27(it-it,TechNet.10).gif)
  
    **Figura 27   Seleziona utenti, computer o gruppi**
  
12. Digitare i nomi degli utenti e fare clic su **OK**.
  
13. Fare clic su **OK** per chiudere la finestra di dialogo **Autorizzazione di accesso**, quindi scegliere **OK** per chiudere la casella **DCOM: restrizioni accesso computer nella sintassi Security Descriptor Definition Language (SDDL)**.
  
14. Fare doppio clic su **DCOM: restrizioni avvio computer nella sintassi Security Descriptor Definition Language (SDDL)**, quindi scegliere **Modifica protezione**. Per concedere le autorizzazioni di avvio o attivazione di tutti i computer a utenti particolari delle applicazioni DCOM all'interno dell'azienda, fare clic su **Aggiungi**.
  
15. Digitare i nomi degli utenti e fare clic su **OK**.
  
16. Fare clic su **OK** per chiudere la finestra di dialogo **Autorizzazione di accesso**, quindi scegliere **OK** per chiudere la casella **DCOM: restrizioni avvio computer nella sintassi Security Descriptor Definition Language (SDDL)**.
  
17. Chiudere la console.
  
#### Applicazione della configurazione con GPUpdate
  
L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.
  
L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.
  
##### Esecuzione di GPUpdate
  
**Per eseguire GPUpdate**
  
1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.
  
2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.
  
    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504
  
3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.
  
    [![](images/Cc700817.adprte28(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte28_big(it-it,technet.10).gif)
  
    **Figura 28   GPUpdate dalla riga di comando**
  
4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.
  
#### Verifica dell'applicazione delle impostazioni di Protezione DCOM
  
**Per verificare che le impostazioni DCOM siano applicate**
  
1.  Fare clic su **Start** e scegliere **Pannello di controllo**.
  
2.  Fare clic su **Prestazioni e manutenzione**.
  
3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Strumenti di amministrazione**.  
  
4.  In **Strumenti di amministrazione**, fare doppio clic su **Servizi componenti**.
  
5.  Nella console **Servizi componenti**, fare doppio clic su **Servizi componenti**, quindi su **Computer**, fare clic con il pulsante destro del mouse su **Computer locale** e, infine, scegliere **Proprietà**.  
  
6.  Fare clic su **Protezione COM**, quindi scegliere entrambi i pulsanti **Modifica predefinite** per verificare che la configurazione desiderata per DCOM sia applicata e, infine, fare clic su **OK** per chiudere Protezione COM.
  
7.  Chiudere Servizi componenti, quindi chiudere Strumenti di amministrazione.
  
8.  Chiudere il Pannello di controllo.
  
    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:
  
    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione delle impostazioni di RPC
  
Windows XP SP2 include alcune modifiche al servizio RPC, progettate per proteggere per impostazione predefinita le interfacce RPC e ridurre i rischi di sicurezza su Windows XP. Sono state aggiunti due nuove impostazioni di criterio:
  
-   **Restrizioni per client RPC non autenticati**. Questa impostazione di criterio consente di modificare il comportamento di tutte le interfacce RPC del sistema e, per impostazione predefinita, elimina l'accesso anonimo remoto a tali interfacce, salvo alcune eccezioni.
  
-   **Autenticazione client mapping degli endpoint RPC**. Questa impostazione di criterio consente di indicare ai client RPC che devono comunicare con il servizio di mapping degli endpoint di autenticarsi, sempre che la chiamata RPC per cui deve essere risolto l'endpoint disponga di informazioni per l'autenticazione.  
  
Se si richiede che le chiamate RPC eseguano l'autenticazione, si può proteggere un'interfaccia dagli attacchi anche utilizzando un livello di autenticazione relativamente basso. Questa prassi è particolarmente utile per difendersi dai worm che sfruttano la vulnerabilità dei sovraccarichi dei buffer che possono essere richiamati in remoto utilizzando connessioni anonime.
  
Per ulteriori informazioni sulla protezione RPC, fare riferimento alle seguenti risorse:
  
-   "[Best Practices for Mitigating RPC and DCOM Vulnerabilities](http://www.microsoft.com/technet/security/alerts/info/bpdcom.mspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=36371
  
#### Requisiti per l'esecuzione di questa attività
  
-   Credenziali: è necessario accedere a un computer Windows XP SP2 che sia un client di dominio Active Directory come membro del gruppo di protezione Amministratori di dominio e aprire un **oggetto Criteri di gruppo**.
  
-   Strumenti: Microsoft Management Console (MMC) con installato lo snap-in Editor oggetti Criteri di gruppo.
  
##### Configurazione delle impostazioni di RPC
  
Quando si attiva l'impostazione di criterio Restrizioni per client RPC non autenticati, è possibile configurare Restrizioni runtime RPC client non autenticati da applicare con una delle seguenti opzioni:
  
-   **Autenticato** (impostazione predefinita). Questa opzione consente *solo* ai client RPC autenticati di connettersi ai server RPC in esecuzione sul computer in cui è applicata l'impostazione di criterio. Alle interfacce che hanno richiesto di essere esentate da questa restrizione viene concessa l'esenzione. Questa opzione rappresenta il valore RPC\_RESTRICT\_REMOTE\_CLIENT\_DEFAULT (1).
  
-   **Autenticato senza eccezioni**. Questa opzione consente *solo* ai client RPC autenticati di connettersi ai server RPC in esecuzione sul computer in cui è applicata l'impostazione di criterio. *Non* consente eccezioni. Se questa opzione è selezionata, un sistema *non può* ricevere chiamate remote anonime tramite RPC. Questa impostazione offre il massimo livello di protezione. Questa opzione rappresenta il valore RPC\_RESTRICT\_REMOTE\_CLIENT\_HIGH (2).
  
-   **Nessuno**. Questa opzione consente a tutti i client RPC di connettersi ai server in esecuzione sul computer in cui è applicato il criterio. Se questa opzione è selezionata, il sistema elude la restrizione per l'interfaccia RPC. L'opzione equivale al comportamento RPC delle precedenti versioni di Windows. Questa opzione rappresenta il valore RPC\_RESTRICT\_REMOTE\_CLIENT\_NONE (0).
  
Quando si attiva l'impostazione di criterio Autenticazione client mapping degli endpoint RPC, i client RPC che devono comunicare con il servizio di mapping degli endpoint devono autenticarsi, sempre che la chiamata RPC per cui deve essere risolto l'endpoint disponga di informazioni per l'autenticazione.
  
Quando si disattiva l'impostazione di criterio Autenticazione client mapping degli endpoint RPC, i client RPC che devono comunicare con il servizio di mapping degli endpoint *non* devono autenticarsi. Il servizio di mapping degli endpoint sui computer con sistema operativo Microsoft Windows NT® 4.0 non è in grado di elaborare le informazioni per l'autenticazione fornite con questa modalità. Ciò significa che, se si attiva questa impostazione su un computer client, tale client non può comunicare con un server Windows NT 4.0 che utilizza l'RPC se è richiesta la risoluzione degli endpoint.
  
**Per configurare le impostazioni di RPC**
  
1.  Dal desktop di Windows XP SP2, fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi snap-in**.
  
3.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.
  
4.  Nell'elenco **Snap-in autonomi disponibili**, fare clic su **Editor oggetti Criteri di gruppo**, quindi scegliere **Aggiungi**.
  
5.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo**, fare clic su **Sfoglia**.
  
6.  Selezionare dall'elenco l'oggetto Criteri di gruppo da configurare. Fare clic su **OK**, quindi scegliere **Fine** per chiudere la Procedura guidata Criteri di gruppo.
  
7.  Fare clic su **Chiudi** per uscire dalla finestra di dialogo **Aggiungi snap-in autonomo**, quindi scegliere **OK** per uscire dalla finestra di dialogo **Aggiungi/Rimuovi snap-in** e tornare alla console di gestione.
  
8.  Nella struttura della console, aprire **Configurazione computer**, **Modelli amministrativi**, **Sistema** e, infine, **RPC (Remote Procedure Call)**.
  
    [![](images/Cc700817.adprte29(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte29_big(it-it,technet.10).gif)
  
    **Figura 29   Impostazioni di RPC**
  
9.  Utilizzare le informazioni di configurazione sopra illustrate e fare doppio clic su **Restrizioni per client RPC non autenticati**, fare clic su **Attivata**, scegliere **Autenticato senza eccezioni** e, infine, fare clic su **OK**.
  
10. Utilizzare le informazioni di configurazione sopra illustrate e fare doppio clic su **Autenticazione client mapping degli endpoint RPC**, fare clic su **Attivata** e, infine, scegliere **OK**.
  
11. Chiudere l'oggetto Criteri di gruppo.
  
#### Applicazione della configurazione con GPUpdate
  
L'utilità GPUpdate aggiorna le impostazioni di Criteri di gruppo basate su Active Directory, che includono le impostazioni di protezione. Dopo avere configurato Criteri di gruppo, è possibile attendere che le impostazioni vengano applicate al computer client dai cicli di aggiornamento standard. Per impostazione predefinita, questi cicli hanno luogo ogni 90 minuti, con un offset casuale di più o meno 30 minuti.
  
L'utilità GPUpdate consente di aggiornare Criteri di gruppo tra un ciclo standard e l'altro.
  
##### Esecuzione di GPUpdate
  
**Per eseguire GPUpdate**
  
1.  Dal desktop di Windows XP, fare clic su **Start**, quindi scegliere **Esegui**.
  
2.  Nella casella **Apri**, digitare **cmd**, quindi fare clic su **OK**.
  
    **Nota:** per una descrizione completa delle opzioni disponibili per GPUpdate, fare riferimento alle seguenti risorse:
  
    -   [Microsoft Knowledge Base, articolo 298444](http://go.microsoft.com/fwlink/?linkid=35504) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35504
  
3.  Dal prompt dei comandi, digitare **GPUpdate** e premere INVIO.
  
    [![](images/Cc700817.adprte30(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700817.adprte30_big(it-it,technet.10).gif)
  
    **Figura 30   GPUpdate dalla riga di comando**
  
4.  Per chiudere il prompt dei comandi, digitare **Exit** e premere INVIO.
  
#### Verifica dell'applicazione delle impostazioni di RPC
  
Questa procedura contiene le informazioni su come modificare il Registro di sistema. Prima di modificare il Registro di sistema, eseguire il backup del registro e assicurarsi di sapere come ripristinarlo in caso di problemi. Per ulteriori informazioni su come eseguire il backup del Registro di sistema e su come ripristinare e modificare tale registro, fare riferimento alle seguenti risorse:
  
-   [Microsoft Knowledge Base, articolo 256986](http://go.microsoft.com/fwlink/?linkid=35500) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35500
  
##### Verifica dell'applicazione delle impostazioni di RPC
  
**Per verificare che le impostazioni di RPC siano applicate**
  
1.  Fare clic su **Start** e quindi su **Esegui**.
  
2.  Digitare **Regedit** e fare clic su **OK**.
  
3.  Nell'Editor del Registro di sistema, fare doppio clic su **HKEY\_LOCAL\_MACHINE**, quindi su **SOFTWARE**\\**Policies**\\**Microsoft**\\**Windows NT**\\**Rpc**.  
  
4.  Verificare che nel Registro di sistema siano presenti le seguenti voci:
  
    **EnableAuthEPResolution REG\_DWORD 0x000000001**
  
    **RestrictRemoteClientsIn REG\_DWORD 0x000000002**
  
5.  Chiudere l'Editor del Registro di sistema.
  
    **Nota:** se le impostazioni di configurazione non sono applicate, è necessario cercare di risolvere gli eventuali problemi relativi all'applicazione Criteri di gruppo. Per risolvere i problemi relativi all'applicazione Criteri di gruppo, fare riferimento alle seguenti risorse:
  
    -   "[Troubleshooting Group Policy in Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=35481)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Informazioni correlate
  
Per ulteriori informazioni sulla protezione di rete di Windows XP SP2, fare riferimento alle seguenti risorse:
  
-   "[Changes to Functionality in Microsoft Windows XP Service Pack 2, Part 2: Network Protection Technologies](http://technet.microsoft.com/en-us/library/bb457156.aspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35486
  
-   "[Managing Windows XP Service Pack 2 Features Using Group Policy](http://technet.microsoft.com/en-us/library/bb878159.aspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35485
  
-   "[Recommendations for managing Group Policy administrative template (.adm) files](http://go.microsoft.com/fwlink/?linkid=35502)" sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35502
  
Per ulteriori informazioni sulla protezione di Windows XP SP2, fare riferimento alle seguenti risorse:
  
-   "[Windows XP Security Guide, Updated for Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35309)" sul sito Web dell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35309
  
-   "[Windows XP Security Guide Appendix A: Additional Guidance for Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35465)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35465
  
-   "[Using Group Policy to Deploy Windows XP Service Pack 2 (SP2)](http://go.microsoft.com/fwlink/?linkid=35501)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35501
  
Per le definizioni dei termini relativi alla protezione, fare riferimento alle seguenti risorse:
  
-   "[Microsoft Security Glossary](http://go.microsoft.com/fwlink/?linkid=35468)" sul sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35468
  
[](#mainsection)[Inizio pagina](#mainsection)
