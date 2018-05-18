---
TOCTitle: 'Capitolo 8: Ruolo del server di stampa'
Title: 'Capitolo 8: Ruolo del server di stampa'
ms:assetid: '897b32c2-f09c-4b08-b10c-37f73aa516df'
ms:contentKeyID: 20213208
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163129(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 8: Ruolo del server di stampa

##### In questa pagina

[](#ehaa)[Panoramica](#ehaa)  
[](#egaa)[Impostazioni del Criterio Controllo](#egaa)  
[](#efaa)[Assegnazione dei diritti utente](#efaa)  
[](#eeaa)[Opzioni di protezione](#eeaa)  
[](#edaa)[Impostazioni del Registro eventi](#edaa)  
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)  
[](#ebaa)[Creazione del criterio utilizzando SCW](#ebaa)  
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo si concentra su come garantire una protezione avanzata ai server di stampa che eseguono Microsoft Windows Server 2003 con SP1, operazione che può risultare impegnativa. I servizi essenziali forniti da questi server richiedono i protocolli Server Message Block (SMB) e Common Internet File System (CIFS), che possono entrambi fornire molte informazioni a utenti non autenticati. Tali protocolli sono spesso disattivati sui server di stampa in ambienti Windows con un livello di protezione alto. Tuttavia, se questi protocolli sono disattivati nell'ambiente in uso, accedere ai server di stampa può essere difficile sia per gli amministratori che per gli utenti.

La maggior parte delle impostazioni in questo capitolo sono configurate e applicate tramite il criterio di gruppo. È possibile collegare un oggetto Criteri di Gruppo (Group Policy object, GPO) che complementi i Criteri di base dei server membro (Member Server Baseline Policy, MSBP) alle unità organizzative appropriate (Organizational Unit, OU) che contengono i server di stampa, al fine di offrire le impostazioni di sicurezza necessarie per tale ruolo server. Questo capitolo tratta solo le impostazioni dei criteri che differiscono da quelle dei criteri MSBP.

Dove possibile, queste impostazioni sono raccolte in un oggetto Criteri di Gruppo incrementale che sarà applicato all'OU dei server di stampa. Alcune delle impostazioni in questo capitolo non possono essere applicate tramite il criterio di gruppo. Vengono fornite informazioni dettagliate su come configurare manualmente queste impostazioni.

La tabella seguente mostra i nomi dei modelli di protezione del server di stampa per i tre ambienti definiti in questa guida. Questi modelli forniscono le impostazioni di criterio per il modello di server di stampa incrementale, che a sua volta è utilizzato per creare un nuovo GPO collegato all'OU dei server di stampa nell'ambiente relativo. Le istruzioni dettagliate sono contenute nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003" per facilitare la creazione di OU e di criteri di gruppo e quindi di importare il modello di protezione idoneo in ciascun GPO.

**Tabella 8.1 Modelli di protezione dei server di stampa per tutti e tre gli ambienti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">LC-Print Server.inf</td>
<td style="border:1px solid black;">EC-Print Server.inf</td>
<td style="border:1px solid black;">SSLF-Print Server.inf</td>
</tr>
</tbody>
</table>
  
Per le informazioni sulle impostazioni nel criterio MSBP, consultare il Capitolo 4, “Criterio di base per un server membro". Per informazioni su tutte le impostazioni di criteri predefinite, consultare la guida correlata, [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP,*](http://technet.microsoft.com/it-it/library/dd162275)disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.
  
**Nota:** ai server di stampa protetti mediante il modello di protezione SSLF-Print Server.inf possono accedere in modo affidabile solo i computer client protetti con impostazioni compatibili. Per informazioni su come proteggere i computer client con impostazioni compatibili con SSLF, consultare la *Guida per la protezione di Windows XP*.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Le impostazioni dei criteri di controllo per i server di stampa nei tre ambienti qui definiti sono configurate tramite i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Il Criterio di base del server membro". Le impostazioni del criterio MSBP attivano la registrazione delle informazioni per il controllo della protezione su tutti i server di stampa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Assegnazione dei diritti utente
  
Le impostazioni per l'assegnazione dei diritti utente per i server di stampa nei tre ambienti definiti in questa guida sono configurate tramite i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Il Criterio di base del server membro." Le impostazioni MSBP configurano uniformemente le assegnazioni dei diritti utente su tutti i server di stampa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
La maggior parte delle impostazioni delle opzioni di protezione per i server di stampa nei tre ambienti qui definiti sono configurate tramite i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro". Le differenze tra i criteri MSBP e i Criteri di gruppo del server di stampa sono descritti nella sezione seguente.
  
#### Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)
  
**Tabella 8.2 Impostazioni consigliate per l'aggiunta della firma digitale alle comunicazioni (sempre)**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
Questa impostazione di criterio determina se il componente server SMB deve richiedere la firma del pacchetto. Il protocollo SMB fornisce le basi per la condivisione di stampanti e file Microsoft e molte altre operazioni di rete, ad esempio l’amministrazione remota di Windows. Per evitare attacchi di tipo "man-in-the-middle" che modificano i pacchetti SMB in transito, il protocollo SMB supporta la firma digitale dei pacchetti SMB. Questa impostazione di criterio determina se debba essere negoziata la firma dei pacchetti SMB perché siano consentite ulteriori comunicazioni con un client SMB.
  
Sebbene l'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** sia disattivata per impostazione predefinita, viene attivata in base ai criteri MSBP per i server nell'ambiente SSLF, consentendo agli utenti di stampare, ma non di visualizzare, la coda di stampa. Agli utenti che tentano di visualizzare la coda di stampa viene visualizzato un messaggio di accesso negato.
  
L'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** è configurata su **Disabilitato** per i server di stampa in tutti e tre gli ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni del registro eventi per i server di stampa nei tre ambienti qui definiti sono configurate tramite i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
Sebbene le impostazioni di protezione applicate mediante i criteri MSBP migliorino significativamente la protezione dei server di stampa, esistono alcune impostazioni aggiuntive che è necessario considerare. Le impostazioni in questa sezione non possono essere applicate tramite i Criteri di gruppo e devono essere quindi eseguite manualmente su tutti i server di stampa.
  
#### Protezione di account noti
  
In Microsoft Windows Server 2003 con SP1 sono disponibili alcuni account utente predefiniti che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membri e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account incorporato. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
**Per proteggere gli account noti sui server di stampa**
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico in grado di accedere a un server membro potrà avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Salvare qualsiasi modifica effettuata in un luogo sicuro.
  
    **Nota**: per rinominare l’account Amministratore incorporato è possibile utilizzare Criteri di gruppo. Questa impostazione di criterio non è stata implementata in nessuno dei modelli di protezione forniti con questa guida, in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare l' impostazione **Account: rinomina l'impostazione di account amministratore** per rinominare gli account amministratore in tutti e tre gli ambienti definiti in questa guida. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
#### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche la guida [Guida alla pianificazione della protezione degli account dei servizi](http://technet.microsoft.com/it-it/library/cc170953) (in inglese) all'indirizzo www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie è necessario utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di server.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Queste impostazioni sono fornite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, utilizzare un hardware simile a quello usato durante la distribuzione. L'installazione nuova è chiamata *computer di riferimento.*
  
**Per creare i criteri dei server di stampa**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio, che applicherà tutte le impostazioni di protezione dalle unità operative genitore.
  
4.  Installare e configurare soltanto le applicazioni obbligatorie che saranno presenti su ogni server che condivide questo ruolo. Gli esempi comprendono servizi specifici, agenti di software e di gestione, agenti di backup su nastro e utilità antivirus o antispyware.
  
5.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
6.  Verificare che i ruoli dei server rilevati siano appropriati per l'ambiente in uso, ad esempio, il ruolo server di stampa.
  
7.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
10. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
11. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
12. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
13. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
14. Allegare il modello di protezione idoneo (ad esempio, EC-Print Server.inf).
  
15. Salvare il criterio con un nome idoneo (ad esempio, Print Server.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o implementare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo offre la possibilità di rieseguire facilmente i criteri utilizzati dallo SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), accertarsi che i client possano richiedere e ottenere dei certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la guida [Deployment Guide for the Security Configuration Wizard](http://technet.microsoft.com/en-us/library/cc776871.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx* * e la guida [Security Configuration Wizard Documentation](http://go.microsoft.com/fwlink/?linkid=43450)(in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:

    ```
  
    scwcmd transform /p:<PathToPolicy.xml> /g:<GPODisplayName>

    ```
  
    e premere INVIO. Ad esempio:

    ```
  
    scwcmd transform /p:"C:\Windows\Security\msscw\Policies\Print 
    Server.xml" /g:"Print Server Policy"

    ```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Il presente capitolo ha descritto le impostazioni di criterio che possono essere utilizzate per i server di stampa che eseguono Windows Server 2003 SP1 nei tre ambienti definiti in questa guida. La maggior parte delle impostazioni sono applicate tramite un oggetto Criteri di gruppo (GPO) che era stato progettato per completare il criterio MSBP. Per fornire maggiore sicurezza, è possibile collegare i GPO alle unità organizzative (OU) appropriate che contengono i server di stampa.
  
Alcune delle impostazioni di criterio trattate non possono essere applicate mediante i Criteri di gruppo. Per queste impostazioni sono stati forniti i dettagli per la configurazione manuale.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server di stampa che eseguono Windows Server 2003 con SP1.
  
-   Per una panoramica su server di stampa, vedere l’articolo "[Technical Overview of Windows Server 2003 Print Services](http://www.microsoft.com/windowsserver2003/techinfo/overview/print.mspx)", scaricabile all'indirizzo: www.microsoft.com/windowsserver2003/techinfo/overview/print.mspx (informazioni in lingua inglese).
  
-   Per ulteriori informazioni sui server di stampa, vedere l'articolo "[What's New in File and Print Services](http://www.microsoft.com/windowsserver2003/evaluation/overview/technologies/fileandprint.mspx)" all’indirizzo: www.microsoft.com/windowsserver2003/evaluation/overview/technologies/  
    fileandprint.mspx (informazioni in lingua inglese).
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
