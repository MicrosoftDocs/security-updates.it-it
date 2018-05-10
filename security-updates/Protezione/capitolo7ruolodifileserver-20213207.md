---
TOCTitle: 'Capitolo 7: Ruolo di File server'
Title: 'Capitolo 7: Ruolo di File server'
ms:assetid: 'e4da3b65-69ce-44a2-8c77-dcd42da508b8'
ms:contentKeyID: 20213207
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163127(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 7: Ruolo di File server

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

Può essere impegnativo migliorare la sicurezza dei file server con Microsoft Windows Server 2003 Service Pack 1 (SP1), perché i servizi più importanti offerti da tali server richiedono i protocolli SMB (Server Message Block) e CIFS (Common Internet File System). Questi protocolli possono fornire molte informazioni a utenti non autenticati e sono spesso disattivati negli ambienti Windows ad elevata protezione. Tuttavia, se questi protocolli sono disattivati, accedere questo tipo di file server può essere difficile sia per gli amministratori sia per gli utenti.

La maggior parte delle impostazioni di criterio in questo capitolo sono configurate e applicate tramite il criterio di gruppo. È possibile collegare un oggetto Criteri di Gruppo (Group Policy object, GPO) che complementi i Criteri di base dei server membro (Member Server Baseline Policy, MSBP) alle unità organizzative appropriate (Organizational Unit, OU) che contengono i file server al fine di offrire le impostazioni di sicurezza necessarie per tale ruolo server. Questo capitolo tratta solo le impostazioni dei criteri che differiscono da quelle dei criteri MSBP.

Dove possibile, queste impostazioni di criterio sono raccolte in un oggetto Criteri di Gruppo incrementale che sarà applicato alla OU del file server. Alcune delle impostazioni di criterio in questo capitolo non possono essere applicate tramite il criterio di gruppo. Vengono fornite informazioni dettagliate su come configurare manualmente queste impostazioni di criterio.

La tabella seguente mostra i nomi dei modelli di protezione del file server per i tre ambienti definiti in questa guida. Questi modelli forniscono le impostazioni per il modello di file server incrementale, che a sua volta è utilizzato per creare un nuovo GPO collegato alla OU dei file server nell'ambiente relativo. Le istruzioni dettagliate sono contenute nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003" per facilitare la creazione di OU e di criteri di gruppo e quindi di importare il modello di protezione idoneo in ciascun GPO.

**Tabella 7.1 Modelli di protezione dei file server**

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
<td style="border:1px solid black;">LC-File Server.inf</td>
<td style="border:1px solid black;">EC-File Server.inf</td>
<td style="border:1px solid black;">SSLF-File Server.inf</td>
</tr>
</tbody>
</table>
  
Per le informazioni sulle impostazioni di criterio nell'MSBP, consultare il Capitolo 4, “Criterio di base per un server membro". Per informazioni su tutte le impostazioni di criteri predefinite, consultare la guida correlata, [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275)*, *disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Le impostazioni di Criteri di controllo per i file server nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro". Le impostazioni del criterio MSBP attivano la registrazione di tutte le informazioni di controllo della protezione pertinenti su tutti i server IIS.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Assegnazione dei diritti utente
  
Le impostazioni per l'assegnazione dei diritti utente per i file server nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, vedere il Capitolo 4, "Criterio di base per un server membro". Le impostazioni MSBP configurano uniformemente tutti i diritti utente appropriati su tutti i file server.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
Le impostazioni delle opzioni di protezione per i file server nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, vedere il Capitolo 4, "Criterio di base per un server membro". Le impostazioni MSBP configurano uniformemente tutte le relative opzioni di sicurezza su tutti i file server.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni del registro eventi per i file server nei tre ambienti qui definiti sono configurate tramite i criteri di base dei server membro (MSBP). Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
Sebbene le impostazioni di protezione che il criterio MSBP applica migliorino significativamente la protezione dei file server, questa sezione tratta alcune considerazioni aggiuntive. Tuttavia, le impostazioni in questa sezione non possono essere implementate attraverso i Criteri di gruppo e devono essere quindi eseguite manualmente su tutti i file server.
  
#### Protezione di account noti
  
In Windows Server 2003 sono disponibili alcuni account utente predefiniti, che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membro e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account predefinito. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
**Per proteggere gli account noti nei file server**
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico in grado di accedere a un server membro potrà avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Salvare qualsiasi modifica effettuata in un luogo sicuro.
  
    **Nota**: per rinominare l’account Amministratore incorporato è possibile utilizzare Criteri di gruppo. Questa impostazione di criterio non è stata implementata in nessuno dei modelli di protezione forniti con questa guida, in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare le impostazioni di **Account: Rinomina l'impostazione di account amministratore** per rinominare gli account amministratore in tutti e tre gli ambienti che sono definiti in questa guida. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
#### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche [la Guida alla pianificazione della protezione degli account dei servizi](http://technet.microsoft.com/it-it/library/cc170953) all'indirizzo www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie è necessario utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di server.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Queste impostazioni sono fornite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, installare il sistema operativo su un computer simile a quello usato durante lo sviluppo. L'installazione nuova è chiamata *computer di riferimento*.
  
**Per creare i criteri del file server**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio, che applicherà tutte le impostazioni di protezione dalle unità operative genitore.
  
4.  Installare e configurare soltanto le applicazioni obbligatorie che saranno presenti su ogni server che condivide questo ruolo. Gli esempi comprendono servizi specifici, agenti di software e di gestione, agenti di backup su nastro e utilità antivirus o antispyware.
  
5.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
6.  Verificare che i ruoli dei server rilevati siano appropriati per l'ambiente in uso, ad esempio, il ruolo file server.
  
7.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
10. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di utilizzarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
11. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
12. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
13. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
14. Allegare il modello di protezione idoneo (ad esempio, EC-File Server.inf).
  
15. Salvare il criterio con un nome idoneo (ad esempio, File Server.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o usare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare l'interfaccia grafica SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo consente di rieseguire facilmente i criteri utilizzati da SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), verificare che i client possano richiedere e ottenere certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la [Deployment Guide for the Security Configuration Wizard](http://technet.microsoft.com/en-us/library/cc776871.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx e la [Security Configuration Wizard Documentation](http://go.microsoft.com/fwlink/?linkid=43450) (in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:
  
    ```
       scwcmd transform /p:<PathToPolicy.xml> /g:<GPODisplayName>
    ```
  
    e premere INVIO. Ad esempio:
  
    ```
       scwcmd transform /p:"C:\Windows\Security\msscw\Policies\File 
       Server.xml" /g:"File Server Policy"
    ```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Il presente capitolo ha descritto le impostazioni di criterio che possono essere utilizzate per configurare i file server con Windows Server 2003 SP1 nei tre ambienti definiti in questa guida. La maggior parte delle impostazioni sono applicate tramite un oggetto Criteri di gruppo (GPO) che era stato progettato per completare il criterio MSBP. Per fornire maggiore sicurezza, è possibile collegare i GPO alle unità organizzative (OU) appropriate che contengono i file server.
  
Alcune impostazioni di criterio non possono essere applicate attraverso i Criteri di gruppo. Per queste impostazioni sono stati forniti i dettagli per la configurazione manuale.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei file server che eseguono Windows Server 2003 con SP1.
  
-   Per maggiori informazioni sui file server, consultare l'articolo "[Technical Overview of Windows Server 2003 File Services](http://www.microsoft.com/windowsserver2003/techinfo/overview/file.mspx)" (in lingua inglese) all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/file.mspx.
  
-   Per ulteriori informazioni su DFS, consultare il white paper "[DFS Technical Reference](http://technet.microsoft.com/it-it/library/cc757042.aspx)" all'indirizzo www.microsoft.com/windows2000/techinfo/howitworks/fileandprint/dfsnew.asp.
  
-   Per ulteriori informazioni su FRS, consultare l'argomento di [FRS Technical Reference](http://technet.microsoft.com/it-it/library/cc759297.aspx) all'indirizzo www.microsoft.com/windowsserversystem/storage/storservices.mspx\#EGBAAA.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
