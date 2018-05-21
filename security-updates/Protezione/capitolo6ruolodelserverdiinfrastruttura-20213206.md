---
TOCTitle: 'Capitolo 6: Ruolo del server di infrastruttura'
Title: 'Capitolo 6: Ruolo del server di infrastruttura'
ms:assetid: 'ed0c9484-c1e8-4399-8da1-488342ca6503'
ms:contentKeyID: 20213206
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163125(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 6: Ruolo del server di infrastruttura

##### In questa pagina

[](#ehaa)[Panoramica](#ehaa)  
[](#egaa)[Impostazioni del Criterio Controllo](#egaa)  
[](#efaa)[Impostazioni di Assegnazione diritti utente](#efaa)  
[](#eeaa)[Opzioni di protezione](#eeaa)  
[](#edaa)[Impostazioni del Registro eventi](#edaa)  
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)  
[](#ebaa)[Creazione del criterio utilizzando SCW](#ebaa)  
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Il presente capitolo descrive le impostazioni di criterio per aumentare la sicurezza dei server infrastruttura con Microsoft Windows Server 2003 Service Pack 1 (SP1) nei tre ambienti definiti in questa guida. Nell'ambito della presente guida, un server infrastruttura fornisce servizi DHCP o funzionalità Microsoft WINS.

La maggior parte delle impostazioni in questo capitolo sono configurate e applicate tramite il criterio di gruppo. È possibile collegare un oggetto Criteri di Gruppo (Group Policy object, GPO) che integri i Criteri di base dei server membro (Member Server Baseline Policy, MSBP) alle unità organizzative appropriate (Organizational Unit, OU) che contengono i server infrastruttura al fine di offrire ulteriore protezione ai server. Questo capitolo tratta solo le impostazioni dei criteri che differiscono da quelle dei criteri MSBP.

Dove possibile, queste impostazioni di criterio sono raccolte in un oggetto Criteri di Gruppo incrementale che sarà applicato all'OU dei server infrastruttura. Alcune delle impostazioni in questo capitolo non possono essere applicate tramite il criterio di gruppo. Vengono fornite informazioni dettagliate su come configurare manualmente queste impostazioni.

La tabella seguente mostra i nomi dei modelli di protezione dei server infrastruttura per i tre ambienti definiti in questa guida. Questi modelli forniscono le impostazioni di criterio per il modello di server infrastruttura incrementale, che a sua volta è utilizzato per creare un nuovo GPO collegato all'OU dei server infrastruttura nell'ambiente relativo. Le istruzioni dettagliate sono contenute nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003" per facilitare la creazione di OU e di criteri di gruppo e quindi di importare il modello di protezione idoneo in ciascun GPO.

**Tabella 6.1 Criteri e modelli di sicurezza dei server infrastruttura**
 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Client precedente</th>
<th style="border:1px solid black;" >Client di organizzazione</th>
<th style="border:1px solid black;" >Protezione specializzata/funzionalità limitata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">LC-Infrastructure Server.inf</td>
<td style="border:1px solid black;">EC-Infrastructure Server.inf</td>
<td style="border:1px solid black;">SSLF-Infrastructure Server.inf</td>
</tr>
</tbody>
</table>
  
Per le informazioni sulle impostazioni di criterio nell'MSBP, consultare il Capitolo 4, “Criterio di base per un server membro". Per informazioni su tutte le impostazioni di criteri predefinite, consultare la guida correlata, [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Le impostazioni di Criteri di controllo per i server infrastruttura nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro". Le impostazioni del criterio MSBP attivano la registrazione delle informazioni di controllo della protezione pertinenti su tutti i server infrastruttura.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Assegnazione diritti utente
  
Le impostazioni per l'assegnazione dei diritti utente per i server infrastruttura nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, vedere il Capitolo 4, "Criterio di base per un server membro." Le impostazioni MSBP configurano uniformemente tutti i diritti utente su tutti i server infrastruttura.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
Le impostazioni delle opzioni di protezione per i server infrastruttura nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, vedere il Capitolo 4, "Criterio di base per un server membro." Le impostazioni MSBP configurano uniformemente le impostazioni delle opzioni di sicurezza rilevanti su tutti i server infrastruttura.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni del registro eventi per i server infrastruttura nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
Le impostazioni di protezione applicate dal criterio MSBP migliorano significativamente la protezione dei server infrastruttura. Questa sezione descrive alcune impostazioni aggiuntive. Non è possibile configurare le impostazioni in questa sezione attraverso i Criteri di gruppo; è necessario configurarle manualmente su tutti i server infrastruttura.
  
#### Configurare la registrazione DHCP
  
Per impostazione predefinita, il servizio DHCP registra nel registro di evento soltanto gli eventi di avvio ed arresto. Effettuare le seguenti operazioni per ottenere un registro più dettagliato sul server di DHCP:
  
1.  Fare clic con il pulsante destro del mouse sul server DHCP nello strumento di amministrazione DHCP.
  
2.  Selezionare **Proprietà**.
  
3.  Nella scheda **Generale** della finestra di dialogo **Proprietà**, scegliere **Attiva registrazione controlli DHCP**.
  
Una volta terminata l'operazione, il server DHCP crea un file di registro nella posizione seguente:
  
**%systemroot%\\system32\\dhcp\\**
  
Poiché le uniche informazioni memorizzate nei registri evento sono i nomi dei computer e non gli indirizzi IP, è spesso difficile individuare informazioni sui client DHCP tra i dati di registro. I registri di controllo DHCP forniscono un ulteriore strumento per individuare le fonti di attacchi interni o le attività involontarie.
  
Le informazioni contenute in tali registri, tuttavia, non sono sicure, dal momento che sia i nomi host che gli indirizzi di controllo dell'accesso ai supporti (MAC, Media Access Control) possono essere contraffatti o oggetto di spoof. (Lo Spoofing fa in modo che una trasmissione di dati sembri provenire da un utente diverso rispetto all'utente che ha realmente eseguito l'azione.) Tuttavia, i vantaggi forniti da queste informazioni superano i costi sostenuti in seguito all'abilitazione della registrazione su un server DHCP. Avere più di un indirizzo IP e un nome computer può essere molto utile quando è necessario determinare come un particolare indirizzo IP è stato utilizzato sulla rete.
  
Per impostazione predefinita, i gruppi **Server Operators** e **Authenticated Users** dispongono dei diritti di lettura dei file di registro DHCP. Per preservare l’integrità dei dati registrati da un server DHCP, è consigliabile che l’accesso ai registri sia limitato agli amministratori dei server. I gruppi **Server Operators** e **Authenticated Users** devono essere rimossi dagli elenchi di controllo all’accesso (ACL) della cartella **%systemroot%\\system32\\dhcp\\**.
  
In teoria, i registri di controllo DHCP potrebbero riempire il disco su cui sono memorizzati. Tuttavia, la configurazione predefinita dell’impostazione per la registrazione del controllo DHCP blocca la registrazione se la disponibilità di spazio nel server scende sotto i 20 MB. Si tratta di un’impostazione predefinita adeguata per i server della maggior parte di ambienti ma è possibile modificarla per fare in modo che altre applicazioni in esecuzione in un server possano disporre di spazio sufficiente. Per informazioni su come modificare questa configurazione, consultare la pagina [DhcpLogMinSpaceOnDisk](http://technet.microsoft.com/en-us/library/cc740115.aspx) del Tech Center di Windows Server 2003 all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/  
DepKit/f7802dce-3ff9-406a-b3e6-c0c6b3ed4941.mspx.
  
#### Proteggere da attacchi di tipo Denial of Service
  
Poiché i server DHCP sono risorse di importanza cruciale in quanto consentono ai client di accedere alla rete, potrebbero essere i primi obiettivi di un attacco di tipo Denial of Service (DoS). Se un server DHCP viene aggredito e non è in grado di soddisfare le richieste DHCP, i client DHCP perdono la capacità di acquisire lease, finendo con il perdere il lease IP esistente e la possibilità di accedere alle risorse di rete.
  
La scrittura dello script di uno strumento di attacco che richieda tutti gli indirizzi disponibili in un server DHCP non è un’operazione particolarmente difficile. Tale strumento esaurirebbe il pool di indirizzi IP disponibili per le richieste successive, questa volta legittime, provenienti dai client DHCP. È inoltre possibile per un utente malintenzionato configurare tutti gli indirizzi IP DHCP contenuti nella scheda di rete di uno dei computer amministrati: in tal modo il server DHCP rileverebbe conflitti di indirizzi IP per tutti gli indirizzi nel proprio ambito e rifiuterebbe di assegnare i lease DHCP.
  
Inoltre, come per tutti gli altri servizi di rete, un attacco di tipo DoS (ad esempio l’esaurimento della CPU o il riempimento del buffer delle richieste del listener) che esaurisse la capacità del server DHCP di gestire il traffico legittimo renderebbe difficile da parte dei client richiedere lease e aggiornamenti. Questo tipo di problema può essere evitato con una corretta progettazione dei servizi DHCP.
  
Per diminuire questi tipi di attacco è possibile configurare i server DHCP a coppie e seguire la regola della procedura 80/20 (vale a dire la suddivisione degli ambiti dei server DHCP tra vari server in modo che l’80% degli indirizzi sia distribuito da un server e il rimanente 20% da un altro. Queste configurazioni consigliate consentono ai client di continuare a ricevere la configurazione di indirizzi IP anche in caso di mancato funzionamento del server. Per ulteriori informazioni sulla regola 80/20 ed il protocollo DHCP, vedere la pagina [DHCP](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/cnet/cncb_dhc_ogjw.mspx?mfr=true) nel Windows 2000 Server Resource Kit all'indirizzo www.microsoft.com/resources/documentation/Windows/2000/server/  
reskit/en-us/cnet/cncb\_dhc\_klom.asp.
  
**Nota**: la regola 80/20 descritta nel Windows 2000 Server Resource Kit è valida anche per i servizi DHCP in Windows Server 2003 SP1.
  
#### Protezione di account noti
  
In Windows Server 2003 sono disponibili alcuni account utente predefiniti, che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membro e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account predefinito. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
**Per proteggere gli account noti nei server infrastruttura:**
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico che riuscisse ad accedere a un server membro potrebbe avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Salvare qualsiasi modifica effettuata in un luogo sicuro.
  
    **Nota**: per rinominare l'account Amministratore incorporato è possibile utilizzare Criteri di gruppo. Questa impostazione di criterio non è stata implementata in nessuno dei modelli di protezione forniti con questa guida, in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare le impostazioni di **Account: Rinomina l'impostazione di account amministratore** per rinominare gli account amministratore in tutti e tre gli ambienti che sono definiti in questa guida. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
#### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche la guida [Guida alla pianificazione della protezione degli account dei servizi](http://technet.microsoft.com/it-it/library/cc170953) (in inglese) all'indirizzo www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie è necessario utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di server.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Le impostazioni di questi criteri sono definite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, installare il sistema operativo su un computer simile a quello usato durante lo sviluppo. L'installazione nuova è chiamata *computer di riferimento.*
  
È possibile che durante le fasi di creazione del criterio di server venga eliminato il ruolo di File server dall'elenco di ruoli rilevati. Questo ruolo è comunemente configurato sui server che non lo richiedono e potrebbe essere considerato un rischio di protezione. Per abilitare il ruolo di File server per i server che lo richiedono, è possibile applicare successivamente un secondo criterio nel corso di questo processo.
  
**Per creare i criteri del server infrastruttura**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un nuovo computer di riferimento.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio, che applicherà tutte le impostazioni di protezione dalle unità operative genitore.
  
4.  Installare e configurare soltanto le applicazioni obbligatorie che saranno presenti su ogni server che condivide questo ruolo. Gli esempi comprendono servizi specifici, agenti di software e di gestione, agenti di backup su nastro e utilità antivirus o antispyware.
  
5.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
6.  Verificare che i ruoli dei server rilevati siano appropriati per l'ambiente in uso, ad esempio, i ruoli server DHCP e server WINS.
  
7.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
10. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di utilizzarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
11. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
12. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
13. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
14. Allegare il modello di protezione idoneo (ad esempio, EC-Infrastructure Server.inf).
  
15. Salvare il criterio con un nome idoneo (ad esempio, Infrastructure Server.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o usare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo consente di rieseguire facilmente i criteri utilizzati da SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), verificare che i client possano richiedere e ottenere certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la guida [Deployment Guide for the Security Configuration Wizard](http://technet.microsoft.com/en-us/library/cc776871.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx e la guida [Security Configuration Wizard Documentation](http://go.microsoft.com/fwlink/?linkid=43450)(in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:

    ```  
    scwcmd transform /p:<PathToPolicy.xml> /g:<GPODisplayName>
    ```  
    e premere INVIO. Ad esempio:

    ```  
    scwcmd transform /p:"C:\Windows\Security\msscw\Policies\Infrastructure.xml"
    /g:"Infrastructure Policy" 
    ```  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni di criterio desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni di criterio appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Il presente capitolo ha descritto le impostazioni di criterio che possono essere utilizzate per i server DHCP e WINS con Windows Server 2003 SP1 nei tre ambienti definiti in questa guida. La maggior parte delle impostazioni di questi ruoli sono applicate tramite i criteri di base dei server membro. Lo scopo principale della creazione di un oggetto dei criteri dell'infrastruttura dei server DHCP e WINS consiste nell’abilitare i servizi necessari al funzionamento corretto di questi ruoli pur mantenendoli protetti.
  
Sebbene il criterio MSBP fornisca un notevole livello di protezione, questo capitolo ha trattato anche altre considerazioni sui ruoli dei server infrastruttura. Principalmente, tali considerazioni riguardano la generazione di file di registro.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server infrastruttura che eseguono Windows Server 2003 con SP1.
  
-   Per informazioni su come la registrazione DHCP è cambiata in Windows Server 2003, consultare l'articolo della Knowledge Base Microsoft “[Modifiche nella registrazione DHCP in Windows Server 2003](http://support.microsoft.com/?kbid=328891)” all'indirizzo http://support.microsoft.com/default.aspx?scid=kb%3Bit%3B328891.
  
-   Per ulteriori informazioni su DHCP, vedere la pagina [DHCP Technical Reference](http://technet.microsoft.com/en-us/library/cc781223.aspx) (in inglese) all'indirizzo www.microsoft.com/resources/documentation/Windows/2000/server/reskit/  
    en-us/cnet/cncb\_dhc\_klom.asp.
  
-   Per ulteriori informazioni su WINS, consultare “[WINS Technical Reference](http://technet.microsoft.com/en-us/library/cc736411.aspx)” (in inglese) all'indirizzo WINS Technical Reference.
  
-   Per informazioni sull'installazione di WINS in Windows Server 2003, consultare la pagina “[Install and Manage WINS Servers](http://technet.microsoft.com/en-us/library/cc781979.aspx)” (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/  
    ServerHelp/a29d0a59-8bdd-4a82-a980-b53bd72fcb0e.mspx.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)