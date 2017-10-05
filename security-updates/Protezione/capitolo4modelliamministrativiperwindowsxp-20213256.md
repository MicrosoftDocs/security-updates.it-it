---
TOCTitle: 'Capitolo 4: Modelli amministrativi per Windows XP'
Title: 'Capitolo 4: Modelli amministrativi per Windows XP'
ms:assetid: 'adb79ec2-691f-4a9f-b940-36d2d9807fd7'
ms:contentKeyID: 20213256
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163076(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Capitolo 4: Modelli amministrativi per Windows XP

##### In questa pagina

[](#edaa)[Panoramica](#edaa)
[](#ecaa)[Impostazioni di configurazione del computer](#ecaa)
[](#ebaa)[Impostazioni configurazione utente](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo descrive in dettaglio la configurazione e l'applicazione di impostazioni di protezione aggiuntive a Microsoft Windows XP Professional con Service Pack 2 (SP2) utilizzando i Modelli amministrativi. I file Modelli amministrativi (.adm) sono utilizzati per configurare le impostazioni nel Registro di sistema di Windows XP che regolano il funzionamento di vari servizi, applicazioni e componenti del sistema operativo.

In Windows XP SP2 sono disponibili cinque modelli amministrativi, contenenti oltre centinaia di impostazioni aggiuntive che è possibile utilizzare per migliorare la protezione di Windows XP Professional. Numerose impostazioni dei Modelli amministrativi di Microsoft Windows Server™ 2003 non funzionano con Windows XP. Per un elenco completo di tutte le impostazioni dei Modelli amministrativi disponibili in Windows XP, vedere la cartella di lavoro Microsoft Excel "Impostazioni dei criteri" a cui si fa riferimento nella sezione "Ulteriori informazioni" alla fine del presente capitolo.

La seguente tabella elenca i file .adm e le applicazioni e i servizi che ne sono interessati.

**Tabella 4.1 File dei Modelli amministrativi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome file</th>
<th style="border:1px solid black;" >Sistema operativo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">System.adm</td>
<td style="border:1px solid black;">Windows XP Professional</td>
<td style="border:1px solid black;">Contiene molte impostazioni per personalizzare l'ambiente operativo dell'utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Inetres.adm</td>
<td style="border:1px solid black;">Windows XP Professional</td>
<td style="border:1px solid black;">Contiene le impostazioni per Internet Explorer 6.0.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Conf.adm</td>
<td style="border:1px solid black;">Windows XP Professional</td>
<td style="border:1px solid black;">Contiene le impostazioni per configurare Microsoft NetMeeting.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Wmplayer.adm</td>
<td style="border:1px solid black;">Windows XP Professional</td>
<td style="border:1px solid black;">Contiene le impostazioni per configurare Windows Media Player.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Wuau.adm</td>
<td style="border:1px solid black;">Windows XP Professional</td>
<td style="border:1px solid black;">Contiene le impostazioni per configurare Windows Update.</td>
</tr>
</tbody>
</table>
  
**Nota**: è necessario configurare manualmente le impostazioni dei Modelli amministrativi nell'oggetto Criteri di Gruppo (GPO) per applicarle ai computer e agli utenti dell'ambiente.
  
Esistono due gruppi principali di impostazioni nei Modelli amministrativi:
  
-   Le impostazioni di configurazione computer (archiviate nell'hive del Registro di sistema **HKEY\_Local\_Machine**)
  
-   Le impostazioni di configurazione utente (archiviate nell'hive del Registro di sistema **HKEY\_Current\_User**).
  
Come nel Capitolo 3, "Impostazioni di protezione per i client Windows XP", le prescrizioni per l'impostazione si riferiscono agli ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality) che sono definiti in questa guida.
  
**Nota**: le impostazioni utente sono applicate a un'unità organizzativa (OU) contenente gli utenti attraverso un GPO collegato. Vedere il Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory", per ulteriori dettagli relativi a questa OU.
  
Alcune impostazioni sono disponibili sia in Configurazione computer sia in Configurazione utente nell'Editor oggetti Criteri di gruppo. Se un'impostazione che si applica a un utente che accede a un computer su cui è stata impostata la stessa Configurazione computer attraverso Criteri di gruppo, questa ha la precedenza rispetto alla Configurazione utente.
  
Le versioni precedenti di questa guida contenevano informazioni relative alle impostazioni di Office XP. Tuttavia, queste impostazioni sono state aggiornate per Office 2003 e sono disponibili sul sito Web di Microsoft. Per i collegamenti a queste informazioni, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
Questo capitolo non descrive tutte le impostazioni disponibili nei Modelli amministrativi forniti da Microsoft; molte di queste impostazioni sono relative all'interfaccia utente (UI) e non sono specifiche della protezione. Le configurazioni delle impostazioni descritte in questa guida devono essere applicate all'ambiente in base agli obiettivi di protezione dell'organizzazione.
  
Se si desidera applicare impostazioni aggiuntive a Windows XP Professional attraverso Criteri di gruppo, è possibile sviluppare modelli personalizzati. Vedere i white paper elencati nella sezione "Ulteriori Informazioni" alla fine di questo capitolo per informazioni dettagliate sullo sviluppo di Modelli amministrativi personalizzati.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di configurazione del computer
  
Le sezioni seguenti descrivono le impostazioni stabilite in Configurazione computer nell'Editor oggetti Criteri di gruppo. Configurare queste impostazioni nel seguente percorso:
  
**Configurazione computer\\Modelli amministrativi**
  
Questo percorso è mostrato in contesto nella figura seguente:
  
[![](images/Cc163076.SGFG0401n(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0401n_big(it-it,technet.10).gif)
  
**Figura 4.1 Struttura dei Criteri di gruppo per la Configurazione computer**
  
La struttura di questo capitolo è basata sulla struttura del contenitore nei Criteri di gruppo. Le tabelle nelle sezioni seguenti riassumono le raccomandazioni di impostazione per varie opzioni di Configurazione computer per i computer client sia desktop sia portatili nei due tipi di ambienti protetti, EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality). Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
Applicare queste impostazioni attraverso un GPO collegato a un OU che contiene gli account computer dell'ambiente. Inserire le impostazioni per i computer portatili nel GPO collegato alla OU per portatili e le impostazioni per i computer desktop nel GPO collegato alla OU per desktop.
  
#### Componenti di Windows
  
La figura seguente illustra le sezioni dei Criteri di gruppo che saranno interessate dalle modifiche alle impostazione in questa sezione:
  
[![](images/Cc163076.SGFG0402n(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0402n_big(it-it,technet.10).gif)
  
**Figure 4.2 Struttura dei Criteri di gruppo per la Configurazione computer, Componenti di Windows**
  
##### NetMeeting
  
Microsoft NetMeeting consente agli utenti di condurre riunioni virtuali sulla rete dell'organizzazione. È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\**  
**NetMeeting**
  
**Tabella 4.2 Impostazioni NetMeeting consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disattiva Condivisione desktop remoto</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Disattiva Condivisione desktop remoto
  
Questa impostazione di criterio disattiva la funzionalità di condivisione del desktop remoto di NetMeeting. Se si attiva questa impostazione di criterio, gli utenti non potranno configurare NetMeeting per consentire il controllo remoto del desktop locale.
  
L'impostazione **Disattiva Condivisione desktop remoto** è configurata su **Non configurato** per l'ambiente EC. Tuttavia, è configurata su **Abilitato** per l'ambiente SSLF per evitare che gli utenti condividano i desktop in modalità remota attraverso NetMeeting.
  
##### Internet Explorer
  
I Criteri di gruppo di Microsoft Internet Explorer consentono di applicare requisiti di protezione per le workstation Windows XP e di evitare lo scambio di contenuto indesiderato attraverso Internet Explorer. Utilizzare i seguenti criteri per assicurare la protezione di Internet Explorer sulle workstation dell'ambiente:
  
-   Assicurarsi che le richieste a Internet vengano effettuate solo come diretta risposta ad azioni degli utenti.
  
-   Assicurarsi che le informazioni inviate a specifici siti Web raggiungano soltanto quei siti, a meno che agli utenti sia consentito eseguire azioni particolari per trasmettere informazioni ad altre destinazioni.
  
-   Assicurarsi che i canali attendibili verso i server/siti e i proprietari di questi ultimi su ogni canale siano chiaramente identificati.
  
-   Assicurarsi che gli script o programmi che utilizzano Internet Explorer vengano eseguiti in un ambiente limitato. I programmi inoltrati attraverso canali attendibili possono essere attivati per operare all'esterno dell'ambiente limitato.
  
È possibile configurare le seguenti impostazioni previste per Internet Explorer nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer**
  
La tabella seguente riassume molte delle raccomandazioni di impostazione di Internet Explorer. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.3 Impostazioni consigliate di Internet Explorer**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disattiva l'installazione automatica dei Componenti di Internet Explorer e Accesso a Internet</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disattiva Controllo periodico per aggiornamenti software di Internet Explorer</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disattiva avvisi Shell per aggiornamenti software all'avvio del programma</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non consentire agli utenti di abilitare o disabilitare i componenti aggiuntivi</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Basa impostazioni proxy sul computer (non sull'utente)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Aree di protezione: impedisci l'aggiunta e l'eliminazione di siti</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aree di protezione: impedisci la modifica del criterio</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Aree di protezione: utilizza solo le impostazioni del computer</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disattiva rilevamento errori critici</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Disattiva l'installazione automatica dei Componenti di Internet Explorer e Accesso a Internet
  
Se si attiva questa impostazione di criterio, in Internet Explorer non verrà eseguito il download dei componenti richiesti dai siti Web durante l'esplorazione dell'utente. Se questa impostazione di criterio è disattivata o non è configurata, verrà richiesto agli utenti di scaricare e installare i componenti utilizzati dai siti Web visitati.
  
L'impostazione **Disattiva l'installazione automatica dei Componenti di Internet Explorer e Accesso a Internet** è configurata su **Abilitato** per i due ambienti trattati nel capitolo.
  
**Nota**: prima di attivare questa impostazione di criterio, Microsoft consiglia di configurare una strategia alternativa per aggiornare Internet Explorer attraverso Microsoft Update o un servizio simile.
  
###### Disattiva Controllo periodico per aggiornamenti software di Internet Explorer
  
Se si attiva questa impostazione di criterio, in Internet Explorer non verrà determinata la disponibilità di versioni successive del browser né inviata all'utente alcuna notifica in merito. Disabilitando o non configurando il criterio, per impostazione predefinita viene eseguita una ricerca degli aggiornamenti di Internet Explorer ogni 30 giorni, quindi viene inviata agli utenti una notifica in caso sia disponibile una nuova versione.
  
L'impostazione **Disattiva Controllo periodico per aggiornamenti software di Internet Explorer** è configurata su **Abilitato** per i due ambienti trattati nel capitolo.
  
**Nota**: prima di attivare questa impostazione di criterio, Microsoft consiglia di configurare una strategia alternativa per gli amministratori dell'organizzazione in modo da assicurare che questi accettino periodicamente nuovi aggiornamenti per Internet Explorer sui computer client dell'ambiente.
  
###### Disattiva avvisi Shell per aggiornamenti software all'avvio del programma
  
Questa impostazione di criterio consente di specificare che dai programmi che utilizzano i canali di distribuzione del software Microsoft non verrà inviata alcuna notifica relativa all'installazione di nuovi componenti. Il canale di distribuzione del software consente di aggiornare in modo dinamico il software presente sui computer grazie all'uso delle tecnologie Open Software Distribution (.osd).
  
L'impostazione **Disattiva avvisi Shell per aggiornamenti software all'avvio del programma** è configurata su **Abilitato** per i due ambienti trattati nel capitolo.
  
###### Non consentire agli utenti di abilitare o disabilitare i componenti aggiuntivi
  
Questa impostazione di criterio consente di stabilire se gli utenti hanno la possibilità di abilitare o disabilitare i componenti aggiuntivi attraverso Gestione componenti aggiuntivi. Se si configura questo criterio su **Attivato**, gli utenti non possono abilitare o disabilitare i componenti aggiuntivi attraverso Gestione componenti aggiuntivi. La sola eccezione è se un componente aggiuntivo è stato espressamente inserito nell'**Elenco componenti aggiuntivi** dei criteri in modo da consentire agli utenti di continuare a gestire il componente aggiuntivo. In tal caso, l'utente può gestire il componente aggiuntivo attraverso Gestione componenti aggiuntivi. Se si configura questo criterio su **Disattivato**, gli utenti potranno abilitare o disabilitare i componenti aggiuntivi.
  
**Nota**: per ulteriori informazioni sulla gestione dei componenti aggiuntivi di Internet Explorer in Windows XP con SP2, vedere l'articolo della Microsoft Knowledge Base 883256 "[Gestione dei componenti aggiuntivi di Internet Explorer in Windows XP Service Pack 2](http://support.microsoft.com/kb/883256/it)" all'indirizzo http://support.microsoft.com/kb/883256/it.
  
Gli utenti scelgono spesso di installare componenti aggiuntivi che non sono consentiti dai criteri di protezione di un'organizzazione. Tali componenti possono rappresentare un rischio significativo per la protezione e la privacy della rete. Questa impostazione di criterio è quindi configurata su **Abilitato** per entrambi gli ambienti descritti in questo capitolo.
  
**Nota**: riesaminare le impostazioni dei GPO in Internet Explorer\\Funzioni di protezione\\Gestione componenti aggiuntivi per accertarsi che i componenti aggiuntivi autorizzati e corretti possano ancora essere utilizzati nell'ambiente. Ad esempio, consultare l'articolo della Microsoft Knowledge base "[Outlook Web Access e Area di lavoro sul Web Small Business Server non funzionano se Blocco Aggiuntivo XP Service Pack 2 è attivato tramite il criterio di gruppo](http://support.microsoft.com/kb/555235/it)" all'indirizzo http://support.microsoft.com/kb/555235/it.
  
###### Basa impostazioni proxy sul computer (non sull'utente)
  
Se si attiva questa impostazione di criterio, gli utenti non potranno modificare le impostazioni proxy e dovranno utilizzare le aree create per tutti gli utenti dei computer a cui hanno accesso.
  
L'impostazione **Basa impostazioni proxy sul computer (non sull'utente)** è configurata su **Abilitato** per i computer client desktop dei due ambienti trattati in questo capitolo. Tuttavia, l'impostazione di criterio è configurata su **Disabilitato** per i computer client portatili, perché gli utenti mobili potrebbero dover modificare le impostazioni proxy durante gli spostamenti.
  
###### Aree di protezione: impedisci l'aggiunta e l'eliminazione di siti
  
Attivare questa impostazione di criterio per disattivare le impostazioni per la gestione dei siti nelle aree di protezione (per consultare le impostazioni per la gestione dei siti nelle aree di protezione, aprire Internet Explorer, selezionare **Strumenti** e quindi **Opzioni Internet**, fare clic sulla scheda **Protezione**, quindi su **Siti**). Se questa impostazione di criterio è disattivata o non è configurata, gli utenti potranno aggiungere o rimuovere i siti Web nelle aree **Siti attendibili** e **Siti con restrizioni** e modificare le impostazioni nell'area **Intranet locale**.
  
L'impostazione **Aree di protezione: impedisci l'aggiunta e l'eliminazione di siti** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
**Nota**: se si attiva l'impostazione **Disattiva la scheda Protezione** (che si trova in \\Configurazione utente\\  
Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet), la scheda **Protezione** non sarà più presente sull'interfaccia e l'impostazione **Disabilita** avrà la precedenza su questa impostazione **Aree di protezione:impedisci la modifica del criterio**.
  
###### Aree di protezione: impedisci la modifica del criterio
  
Se si attiva questa impostazione di criterio, vengono disabilitati il pulsante **Livello personalizzato** e il dispositivo di scorrimento **Livello di protezione per l'area** nella scheda **Protezione** della finestra di dialogo **Opzioni Internet.** Se questa impostazione di criterio è disattivata o non è configurata, gli utenti potranno modificare le impostazioni delle aree di protezione. Essa non consente la modifica delle impostazioni dei criteri per le aree di protezione definite dall'amministratore.
  
L'impostazione **Aree di protezione: impedisci la modifica del criterio** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
**Nota**: se si attiva l'impostazione **Disattiva la scheda Protezione** (che si trova in \\Configurazione utente\\  
Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet), la scheda **Protezione** non sarà più presente sul Pannello di controllo di Internet Explorer e l'impostazione **Disabilita** avrà precedenza su **Aree di protezione: impedisci la modifica del criterio**.
  
###### Aree di protezione: utilizza solo le impostazioni del computer
  
Questa impostazione di criterio determina il modo in cui le modifiche alle aree di protezione si applicano a utenti diversi. Assicura che le impostazioni delle aree di protezione siano le stesse per tutti gli utenti di un determinato computer. Se si attiva questa impostazione di criterio, le modifiche apportate da un utente a un'area di protezione verranno applicate a tutti gli utenti dello stesso computer. Se questa impostazione di criterio è disattivata o non è configurata, gli utenti di uno stesso computer potranno stabilire impostazioni personalizzate per le aree di protezione.
  
L'impostazione **Aree di protezione: utilizza solo le impostazioni del computer** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Disattiva rilevamento errori critici
  
Questa impostazione di criterio consente di configurare la funzionalità di rilevamento errori critici nella gestione dei componenti aggiuntivi di Internet Explorer. Se si abilita questa impostazione di criterio, un errore critico in Internet Explorer sarà simile a quello su un computer dotato di Windows XP Professional con Service Pack 1 (SP1) e versioni precedenti: sarà richiamata la Segnalazione errori di Windows. Se si disattiva questo criterio, sarà operativa la funzionalità di rilevamento errori critici nella gestione dei componenti aggiuntivi.
  
Poiché i dati relativi al report di arresti anomali di Internet Explorer potrebbero contenere informazioni riservate della memoria del computer, l'impostazione **Disattiva rilevamento errori critici** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo. Se si verificano errori critici ripetuti di frequente e si ha la necessità di segnalarli per una successiva risoluzione dei problemi, è possibile configurare temporaneamente questa impostazione su **Disabilitato.**
  
##### Internet Explorer\\Pannello di controllo Internet\\Protezione
  
È possibile configurare queste impostazioni del computer nella seguente posizione dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet\\Protezione**
  
SP2 ha introdotto nuove impostazioni di criterio che consentono di proteggere la configurazione delle aree di Internet Explorer nell'ambiente. I valori predefiniti per queste impostazioni forniscono una protezione migliore rispetto alle versioni precedenti di Windows. Tuttavia, è possibile riesaminare queste impostazioni per determinare se renderle obbligatorie o meno rigorose all'interno dell'ambiente, al fine di garantirne l'utilizzabilità o la compatibilità con le applicazioni.
  
Per esempio, SP2 configura Internet Explorer in modo che blocchi i pop-up di tutte le aree di Internet per impostazione predefinita. È possibile garantire che questa impostazione di criterio sia applicata a tutti i computer dell'ambiente, per eliminare le finestre pop-up e ridurre la possibilità che vengano installati software e spyware dannosi che sono spesso generati su siti Web in Internet. Tuttavia, l'ambiente potrebbe contenere applicazioni che richiedono l'uso di pop-up per funzionare. In questo caso, è possibile configurare questo criterio in modo da abilitare i pop-up per i siti Web all'interno di Intranet.
  
##### Internet Explorer\\Pannello di controllo Internet\\Avanzate
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet\\Avanzate**
  
**Tabella 4.4 Impostazioni consigliate Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida.</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
###### Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida.
  
Ai controlli e ai download di file di Microsoft ActiveX sono spesso allegate firme digitali che garantiscono l'integrità del file e l'identità dell'autore della firma (il creatore) del software. Le firme consentono di verificare di aver scaricato software non modificato e di identificare l'autore della firma per determinare se ci si fida abbastanza per eseguire il software.
  
L'impostazione **Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida** consente di stabilire se gli utenti possono installare o utilizzare il software scaricato anche se la firma non è valida. Una firma non valida potrebbe indicare che qualcuno ha manomesso il file. Se si abilita questa impostazione del criterio, sarà richiesta l'autorizzazione per installare o eseguire file con firma non valida. Se si disattiva questa impostazione del criterio, gli utenti non potranno eseguire o installare file con una firma non valida.
  
Poiché il software privo di firma può creare vulnerabilità nella protezione, questa impostazione di criterio è configurata su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: alcuni software e controlli legittimi possono avere una firma non valida ma essere comunque sicuri. Verificare con cura e in sede separata tali software prima di consentirne l'utilizzo sulla rete dell'organizzazione.
  
##### Internet Explorer\\Funzioni di protezione\\Limitazione protocollo di protezione MK
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limitazione protocollo di protezione MK**
  
**Tabella 4.5 Impostazioni consigliate Limitazione protocollo di protezione MK**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Protocollo MK)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Protocollo MK)
  
Questa impostazione di criterio riduce l'area esposta ad attacchi bloccando il protocollo MK, raramente utilizzato. Alcune applicazioni Web meno aggiornate utilizzano il protocollo MK per recuperare le informazioni dai file compressi. Se si configura questa impostazione su **Abilitato**, il protocollo MK viene bloccato per Esplora risorse e Internet Explorer, in modo da interdire le risorse che utilizzano tale protocollo. La disattivazione di questa impostazione consente alle applicazioni di utilizzare l'API del protocollo MK.
  
Poiché il protocollo MK non è diffuso, dovrebbe essere bloccato quando non necessario. Questa impostazione di criterio è configurata su **Attivato** per entrambi gli ambienti descritti in questo capitolo. Microsoft consiglia di bloccare il protocollo MK, a meno che non sia specificamente necessario per l'ambiente.
  
**Nota**: poiché le risorse che utilizzano il protocollo MK verranno interdette quando si utilizza questa impostazione, assicurarsi che nessuna delle applicazioni utilizzi tale protocollo.
  
##### Internet Explorer\\Funzioni di protezione\\Gestione MIME coerente
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Gestione MIME coerente**
  
**Tabella 4.6 Impostazioni consigliate Gestione MIME coerente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Gestione MIME coerente)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Gestione MIME coerente)
  
Internet Explorer utilizza i dati MIME (Multipurpose Internet Mail Extensions) per determinare le procedure di gestione dei file ricevuti attraverso un server Web. L'impostazione **Gestione MIME coerente** determina se Internet Explorer richiede che tutte le informazioni relative al tipo di file fornite dai server Web siano coerenti. Per esempio, se il tipo MIME di un file è text/plain ma i dati MIME indicano che il file è in realtà un eseguibile, Internet Explorer ne modifica l'estensione per riflettere questa condizione. Questa funzione consente di evitare che il codice eseguibile possa essere mascherato come altri tipi di dati non pericolosi.
  
Se si abilita questa impostazione del criterio, Internet Explorer esamina tutti i file ricevuti e applica ad essi i dati MIME coerenti. Se si disattiva o non si configura questa impostazione di criterio, Internet Explorer non richiede che i dati MIME siano coerenti per tutti i file ricevuti e utilizzerà i dati MIME forniti dal file.
  
Lo spoofing del tipo di file MIME è una minaccia potenziale per l'organizzazione. Assicurarsi che questi file siano coerenti e correttamente denominati per evitare che download di file dannosi infettino la rete. Questa impostazione di criterio è configurata su **Attivato** per entrambi gli ambienti descritti in questo capitolo.
  
**Nota**: questa impostazione opera unitamente a, ma non sostituisce, le impostazioni della **Funzionalità di protezione analisi MIME**.
  
##### Internet Explorer\\Funzioni di protezione\\Funzionalità di protezione analisi MIME
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Funzionalità di protezione analisi MIME**
  
**Tabella 4.7 Impostazioni consigliate Analisi MIME**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Analisi MIME)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Analisi MIME)
  
L'analisi MIME è una processo che esamina il contenuto di un file MIME per determinare il suo contesto, cioè se si tratta di un file di dati, di un file eseguibile o di qualche altro tipo di file. Questa impostazione di criterio determina se l'analisi MIME di Internet Explorer eviterà la conversione di un tipo di file a un file di tipo più pericoloso. Quando impostato su **Attivato**, l'analisi MIME non convertirà mai un file a un tipo di file più pericoloso. Se si disattiva questa impostazione di criterio, Analisi MIME configura i processi di Internet Explorer in modo da convertire un tipo di file a un file di tipo più pericoloso. Ad esempio, la conversione di un file di testo in un file eseguibile è pericolosa, perché può essere eseguito qualsiasi codice all'interno del presunto file di testo.
  
Lo spoofing del tipo di file MIME è un pericolo potenziale per l'organizzazione. Microsoft consiglia di assicurarsi che questi file siano gestiti in modo coerente per evitare che i download di file dannosi infettino la rete.
  
L'impostazione **Processi di Internet Explorer (Analisi MIME)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: questa impostazione opera unitamente a, ma non sostituisce, le impostazioni di **Gestione MIME coerente**.
  
##### Internet Explorer\\Funzioni di protezione\\Limitazioni protezione Windows tramite script
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limitazioni protezione Windows tramite script**
  
**Tabella 4.8 Impostazioni consigliate Limitazioni protezione Windows tramite script**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Limitazioni protezione Windows tramite script)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Limitazioni protezione Windows tramite script)
  
Internet Explorer consente agli script di aprire, ridimensionare e riposizionare in modo programmato vari tipi di finestre. I siti Web malintenzionati spesso ridimensioneranno finestre per nascondere altre finestre o costringere l'utente a interagire con una finestra che contiene codice dannoso.
  
L'impostazione **Processi di Internet Explorer** **(Limitazioni protezione Windows tramite script)** limita le finestre pop-up e impedisce agli script di visualizzare finestre nelle quali le barre di titolo e di stato non sono visibili all'utente o nascondono altre barre di titolo e di stato della finestra. Se si attiva questa impostazione di criterio, le finestre pop-up non saranno visualizzate in Esplora risorse e nei processi di Internet Explorer. Se si disattiva o non si configura questa impostazione di criterio, gli script continuano a creare finestre pop-up e finestre che ne nascondono altre.
  
L'impostazione **Processi di Internet Explorer** **(Limitazioni protezione Windows tramite script)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo. Quando attivata, questa impostazione evita che i siti Web dannosi controllino le finestre di Internet Explorer o inducano erroneamente gli utenti a selezionare la finestra sbagliata.
  
##### Internet Explorer\\Funzioni di protezione\\Protezione da promozione di area
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di Protezione\\Protezione da promozione di area**
  
**Tabella 4.9 Impostazioni consigliate Protezione da promozione di area**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Protezione da promozione di area)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Protezione da promozione di area)
  
Internet Explorer pone delle restrizioni a ogni pagina Web aperta, che dipendono dalla posizione della pagina stessa (come l'area Internet, l'area Intranet o l'area Computer locale). Le pagine Web su un computer locale hanno le restrizioni di protezione più basse e risiedono nell'area Computer locale, il che rende l'area di protezione del computer locale uno dei bersagli principali per gli attacchi informatici.
  
Se si attiva l'impostazione **Processi di Internet Explorer (Protezione da promozione di area)**, tutte le aree possono essere protette dalla promozione di area da parte dei processi di Internet Explorer. Questo approccio evita che il contenuto in esecuzione in un'area ottenga i privilegi di promozione di un'altra area. Se si disattiva questa impostazione del criterio, nessuna area riceverà tale protezione per i processi di Internet Explorer.
  
A causa della gravità e della relativa frequenza degli attacchi di promozione di area, l'impostazione **Processi di Internet Explorer (Protezione da promozione di area)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Internet Explorer\\Funzioni di protezione\\Limita installazione ActiveX
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limita installazione ActiveX**
  
**Tabella 4.10 Impostazioni Limita installazione ActiveX**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processi di Internet Explorer (Limita installazione ActiveX)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Processi di Internet Explorer (Limita installazione ActiveX)
  
Questa impostazione di criterio consente di bloccare i prompt di installazione del controllo ActiveX per i processi di Internet Explorer. Se si abilita questa impostazione di criterio, i prompt di installazione del controllo ActiveX per i processi di Internet Explorer saranno bloccati. Se viene disabilitata, i prompt di installazione del controllo ActiveX non verranno bloccati e saranno mostrati agli utenti.
  
Gli utenti installano spesso software come i controlli ActiveX, che non sono permessi dai criteri di protezione aziendale. Tale software può comportare significativi rischi di protezione e di riservatezza per le reti. Perciò, l'impostazione **Processi di Internet Explorer (Limita installazione ActiveX)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: questa impostazione impedisce inoltre agli utenti di installare controlli ActiveX autorizzati e legittimi che interferiscono con importanti componenti di sistema come Windows Update. Se si attiva questa impostazione di criterio, assicurarsi di implementare metodi alternativi per distribuire gli aggiornamenti di protezione, come Windows Server Update Services (WSUS).  
Per ulteriori informazioni su WSUS, vedere la pagina [Windows Server Update Services Product Overview](http://www.microsoft.com/windowsserversystem/updateservices/evaluation/overview.mspx) (in inglese) all'indirizzo www.microsoft.com/windowsserversystem/updateservices/evaluation/overview.mspx.  
Per ulteriori informazioni su Windows Update, vedere la pagina [Windows Update](http://windowsupdate.microsoft.com/) all'indirizzo http://windowsupdate.microsoft.com.
  
##### Internet Explorer\\Funzioni di protezione\\Limita download file
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limita download file**
  
**Tabella 4.11 Impostazioni consigliate Limita download file**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Internet Explorer Elabora (Limita download file)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Internet Explorer Elabora (Limita download file)
  
In certe circostanze, i siti Web possono iniziare il download di file senza l'interazione da parte degli utenti. Questa tecnica può consentire ai siti Web di salvare file non autorizzati sul disco fisso se l'utente fa clic sul pulsante sbagliato e accetta il download.
  
Se si configura l'impostazione **Processi di Internet Explorer (Limita download file)** su **Abilitato**, vengono bloccati per Internet Explorer i prompt di download dei file non avviati dagli utenti. Se si configura questa impostazione di criterio su **Disabilitato**, i prompt di download dei file non avviati dagli utenti saranno consentiti per i processi di Internet Explorer.
  
L'impostazione **Processi di Internet Explorer (Limita download file)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo per evitare che i pirati informatici inseriscano codici arbitrari sui computer degli utenti.
  
##### Internet Explorer\\Funzioni di protezione\\Gestione componenti aggiuntivi
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Gestione componenti aggiuntivi**
  
**Tabella 4.12 Impostazioni Gestione componenti aggiuntivi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Elenco componenti aggiuntivi</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
</tbody>
</table>
  
###### Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi
  
Questa impostazione e il criterio **Elenco componenti aggiuntivi** consentono di controllare i componenti aggiuntivi di Internet Explorer. Per impostazione predefinita, le impostazioni dell'**Elenco componenti aggiuntivi** definiscono un elenco di componenti aggiuntivi che può essere consentito o bloccato attraverso i Criteri di gruppo. L'impostazione **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** assicura che tutti gli elementi aggiuntivi siano bloccati a meno che non siano specificatamente elencati nell'impostazione **Elenco componenti aggiuntivi**.
  
Se si abilita questa impostazione di criterio, Internet Explorer accetta unicamente i componenti aggiuntivi specificamente elencati (e consentiti) in **Elenco componenti aggiuntivi**. Se si disattiva questa impostazione, gli utenti potranno utilizzare Gestione componenti aggiuntivi per consentire o bloccare qualsiasi aggiunta.
  
Si consiglia l'uso di entrambe le impostazioni **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** ed **Elenco componenti aggiuntivi** per controllare i componenti aggiuntivi che possono essere utilizzati nell'ambiente. Questo approccio contribuirà ad assicurare che siano usati soltanto i componenti aggiuntivi autorizzati.
  
###### Elenco componenti aggiuntivi
  
Questa impostazione e il criterio **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** consentono di controllare i componenti aggiuntivi di Internet Explorer. Per impostazione predefinita, le impostazioni dell'**Elenco componenti aggiuntivi** definiscono un elenco di componenti aggiuntivi che può essere consentito o bloccato attraverso i Criteri di gruppo. L'impostazione **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** assicura che tutti gli elementi aggiuntivi siano bloccati a meno che non siano specificatamente elencati nell'impostazione **Elenco componenti aggiuntivi**.
  
Se si attiva l'impostazione **Elenco componenti aggiuntivi**, è necessario creare un elenco di componenti aggiuntivi che Internet Explorer deve accettare o rifiutare. I componenti aggiuntivi specifici che devono essere inclusi in questo elenco varia da un'organizzazione all'altra, perciò questa guida non ne fornisce un elenco dettagliato. Per ogni voce aggiunta all'elenco, è necessario fornire le informazioni seguenti:
  
-   **Il nome del valore**. Il CLSID (identificatore di classe) per il componente aggiuntivo che si desidera aggiungere all'elenco. Il CLSID deve essere tra parentesi; per esempio, {000000000-0000-0000-0000-0000000000000}. È possibile ottenere il CLSID di un componente aggiuntivo leggendo il tag OBJECT all'interno della pagina Web in cui il componente aggiuntivo è presente.
  
-   **Valore**. Un numero che indica se Internet Explorer deve rifiutare o consentire il caricamento del componente aggiuntivo. I valori seguenti sono validi:
  
    -   **0**    Rifiuta il componente aggiuntivo
  
    -   **1**    Accetta il componente aggiuntivo
  
    -   **2**    Accetta il componente aggiuntivo e consente all'utente di gestirlo attraverso Gestione componenti aggiuntivi
  
Se si disattiva l'impostazione **Elenco componenti aggiuntivi**, l'elenco viene eliminato. Si consiglia l'uso di entrambe le impostazioni **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** ed **Elenco componenti aggiuntivi** per controllare i componenti aggiuntivi che possono essere utilizzati nell'ambiente. Questo approccio contribuirà ad assicurare che siano usati soltanto i componenti aggiuntivi autorizzati.
  
##### Servizi terminal\\Reindirizzamento dati client/server
  
Le impostazioni Servizi terminal forniscono opzioni per reindirizzare le risorse del computer client ai server ai quali si accede attraverso i Servizi terminal. L'impostazione seguente è specifica dei Servizi terminal.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Servizi terminal\\Reindirizzamento dati client/server**
  
**Tabella 4.13 Impostazioni consigliate Non consentire il reindirizzamento delle unità**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non consentire il reindirizzamento delle unità</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non consentire il reindirizzamento delle unità
  
Questa impostazione di criterio impedisce agli utenti di condividere le unità locali sui computer client con i Servizi terminal a cui accedono. Le unità mappate sono visibili nella struttura della sessione in Esplora risorse o Risorse del computer nel formato seguente:
  
\\\\TSClient\\*&lt;driveletter&gt;$*
  
Se si condividono le unità locali, saranno vulnerabili verso gli attacchi di intrusi che cercano di sfruttare i dati memorizzati su di esse.
  
Per questa ragione, l'impostazione **Non consentire il reindirizzamento delle unità** è configurata su **Abilitato** per l'ambiente SSLF. Tuttavia, questa impostazione di criterio è impostata su **Non configurato** per l'ambiente EC.
  
##### Servizi terminal\\Crittografia e protezione
  
È possibile configurare le seguenti impostazioni previste nel percorso riportato di seguito utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Servizi terminal \\Crittografia e protezione**
  
**Tabella 4.14 Impostazioni consigliate Servizi terminal\\Crittografia e protezione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Richiedi sempre password del client alla connessione</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Imposta livello di crittografia connessione client</td>
<td style="border:1px solid black;">Livello principale</td>
<td style="border:1px solid black;">Livello principale</td>
<td style="border:1px solid black;">Livello principale</td>
<td style="border:1px solid black;">Livello principale</td>
</tr>
</tbody>
</table>
  
###### Richiedi sempre password del client alla connessione
  
Questa impostazione di criterio consente di specificare se verrà richiesta la password del client per la connessione ai Servizi terminal. È possibile utilizzare questa impostazione per applicare la richiesta di una password agli utenti che si connettono ai Servizi terminal anche nel caso in cui sia già stata specificata la password nel client di Connessione desktop remoto. Per impostazione predefinita, Servizi terminal consente all'utente di connettersi automaticamente mediante l'immissione della password nel client di Connessione desktop remoto.
  
L'impostazione **Richiedi sempre password del client alla connessione** è configurata su **Abilitato** nell'ambiente SSLF. Tuttavia, questa impostazione di criterio è impostata su **Non configurato** per l'ambiente EC.
  
**Nota**: se non si configura questa impostazione, l'amministratore del computer locale può utilizzare lo strumento Configurazione Servizi terminal per consentire o impedire che le password vengano inviate automaticamente.
  
###### Imposta livello di crittografia connessione client
  
Questa impostazione di criterio consente di specificare se il computer che sta per ospitare la connessione remota deve applicare un livello di crittografia per tutti i dati che esso scambia con il computer client per la sessione remota.
  
Il livello di crittografia è impostato su **Livello principale** per imporre la crittografia a 128 bit nei due ambienti trattati in questo capitolo.
  
##### Servizi terminal\\Client
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Modelli amministrativi\\Componenti di Windows\\Servizi terminal\\ Client**
  
**Tabella 4.15 Impostazioni consigliate Non consentire salvataggio password**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non consentire salvataggio password</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non consentire salvataggio password
  
Questa impostazione di criterio impedisce che le password vengano salvate su un computer da client di Servizi terminal. Abilitando questa impostazione, la casella di controllo del salvataggio della password in Client di Servizi terminal viene disabilitata, in modo che gli utenti non possano più salvare le password.
  
Poiché il salvataggio delle password può portare a ulteriori violazioni, l'impostazione **Non consentire salvataggio password** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: se questa impostazione era precedentemente configurata su **Disabilitato** o **Non configurato**, qualsiasi password salvata sarà eliminata la prima volta che un client di Servizi terminal si disconnette da un server.
  
##### Windows Messenger
  
Windows Messenger è utilizzato per inviare messaggi istantanei ad altri utenti su una rete di computer. I messaggi possono contenere file e altri allegati.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Windows Messenger**
  
**Tabella 4.16 Impostazioni consigliate Windows Messenger**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non consentire l'esecuzione di Windows Messenger</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non consentire l'esecuzione di Windows Messenger
  
Con l'impostazione **Non consentire l'esecuzione di Windows Messenger** è possibile disabilitare Windows Messenger e impedire che il programma venga utilizzato. Poiché questa applicazione è stata utilizzata per scopi quali lo spam, la distribuzione di software dannoso e la divulgazione di dati riservati, Microsoft consiglia di configurare l'impostazione **Non consentire l'esecuzione di Windows Messenger** su **Abilitato** sia per l'ambiente EC sia per l'ambiente SSLF.
  
**Nota**: se si configura questa impostazione su **Abilitato**, Assistenza Remota non potrà eseguire Windows Messenger e gli utenti non riusciranno a utilizzare MSN Messenger.
  
##### Windows Update
  
Gli amministratori utilizzano le impostazioni di Windows Update per gestire la modalità di applicazione delle patch degli aggiornamenti rapidi alle workstation Windows XP. Gli aggiornamenti sono disponibili sul sito Web Microsoft Windows Update. In alternativa, è possibile configurare un sito Web Intranet per distribuire le patch e gli aggiornamenti rapidi in modo simile con un ulteriore controllo amministrativo. Il Modello amministrativo Windows Update (WUAU.adm) è stato introdotto con Windows XP Service Pack 1 (SP1).
  
Windows Server Update Services (WSUS) è un servizio di infrastruttura che si fonda sul successo delle tecnologie Microsoft Windows Update e Software Update Services (SUS). WSUS gestisce e distribuisce le patch critiche di Windows che proteggono da vulnerabilità di protezione accertate e da altri problemi di stabilità dei sistemi operativi Microsoft Windows.
  
WSUS elimina le fasi di aggiornamento manuale con un sistema di notifica dinamico degli aggiornamenti critici disponibili per i computer client di Windows attraverso il server Intranet. Non è necessario che i computer client accedano a Internet per utilizzare questo servizio. Questa tecnologia fornisce inoltre un metodo semplice e automatico per distribuire gli aggiornamenti alle workstation e ai server Windows.
  
Windows Server Update Services mette a disposizione ulteriori funzionalità, quali:
  
-   **il controllo amministrativo della sincronizzazione del contenuto all'interno di Intranet**. Questo servizio di sincronizzazione è un componente sul lato server che recupera gli aggiornamenti critici più recenti da Windows Update. Mano a mano che gli aggiornamenti vengono aggiunti a Windows Update, il server che esegue WSUS li scarica e li memorizza automaticamente, in base a un programma definito dall'amministratore.
  
-   **Un server Windows Update ospitato all'interno di Intranet**. Questo server, di facile utilizzazione, agisce da server Windows Update virtuale per i computer client. Contiene un servizio di sincronizzazione e strumenti di amministrazione per gestire gli aggiornamenti. Gestisce le richieste di aggiornamenti approvati dai computer client connessi ad esso attraverso il protocollo HTTP. Questo server può inoltre ospitare aggiornamenti critici scaricati dal servizio di sincronizzazione e indirizzare i computer client verso tali aggiornamenti.
  
-   **Il controllo degli aggiornamenti da parte di un amministratore**. L'amministratore può verificare e approvare gli aggiornamenti dal sito pubblico di Windows Update prima di distribuirli nella rete Intranet dell'organizzazione. La distribuzione avviene sulla base di un programma creato dall'amministratore. Se più server eseguono WSUS, l'amministratore controlla quali computer accedono a determinati server dotati di questo servizio. Gli amministratori possono attivare questo livello di controllo attraverso Criteri di gruppo in un ambiente di servizio di directory Active Directory o attraverso le chiavi del Registro di sistema.
  
-   **Aggiornamenti automatici sui computer (workstation o server).** Aggiornamenti automatici è una funzionalità di Windows che può essere configurata per controllare automaticamente la presenza di aggiornamenti pubblicati su Windows Update. WSUS utilizza questa funzionalità di Windows per pubblicare su Intranet aggiornamenti approvati da un amministratore.
  
    **Nota**: se si desidera distribuire le patch in un altro modo, ad esempio attraverso Microsoft Systems Management Server, questa guida consiglia di disattivare l'impostazione **Configura Aggiornamenti automatici.**
  
Esistono numerose impostazioni di Windows Update. Le impostazioni necessarie al funzionamento di Windows Update sono tre: **Configura Aggiornamenti automatici**, **Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici** e **Nuova pianificazione installazioni pianificate Aggiornamenti automatici.** Una quarta impostazione è facoltativa e dipende dai requisiti aziendali: **Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet**.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Windows Update**
  
Le impostazioni presenti in questa sezione non trattano individualmente specifici rischi legati alla protezione, ma si riferiscono piuttosto alle preferenze dell'amministratore. Tuttavia, la configurazione di Windows Update è essenziale alla protezione dell'ambiente, perché assicura che i computer client ricevano le patch per la protezione da Microsoft appena sono disponibili.
  
**Nota**: Windows Update dipende da diversi servizi, come Registro di sistema remoto e il Servizio trasferimento intelligente in background. Nel Capitolo 3, "Impostazioni di protezione per i client Windows XP", questi servizi sono disattivati nell'ambiente SSLF. Di conseguenza, Windows Update non funzionerà e le seguenti indicazioni di impostazione potrebbero essere ignorate solo per l'ambiente SSLF.
  
La seguente tabella riassume le impostazioni di Windows Update consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.17 Impostazioni consigliate di Windows Update**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non visualizzare l'opzione &quot;Installa aggiornamenti e spegni&quot; nella finestra di dialogo Fine della sessione di lavoro di Windows.</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non impostare &quot;Installa aggiornamenti e spegni&quot; come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro.</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Configura Aggiornamenti automatici</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nuova pianificazione installazioni pianificate Aggiornamenti automatici</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non visualizzare l'opzione "Installa aggiornamenti e spegni" nella finestra di dialogo Fine della sessione di lavoro di Windows.
  
Questa impostazione di criterio consente di decidere se l'opzione **Installa aggiornamenti e spegni** deve essere visualizzata nella finestra di dialogo **Fine della sessione di lavoro di Windows.** Disattivando questa impostazione di criterio l'opzione **Installa aggiornamenti e spegni** viene visualizzata nella finestra di dialogo **Fine della sessione di lavoro di Windows** se gli aggiornamenti sono disponibili quando l'utente seleziona l'opzione **Spegni computer** nel menu **Start** o fa clic sul pulsante **Chiudi sessione** una volta premuto CTRL+ALT+DELETE.
  
Poiché gli aggiornamenti sono importanti per la protezione complessiva di tutti i computer, l'impostazione **Non visualizzare l'opzione "Installa aggiornamenti e spegni" nella finestra di dialogo Fine della sessione di lavoro di Windows** è configurata su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo. Questa impostazione opera unitamente al criterio **Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro**, elencato di seguito.
  
###### Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro.
  
Questa impostazione di criterio consente di stabilire se l'opzione **Installa aggiornamenti e spegni** debba essere quella predefinita nella finestra di dialogo **Fine della sessione di lavoro di Windows.** Disattivando questa impostazione di criterio, l'opzione **Installa aggiornamenti e spegni** sarà quella predefinita nella finestra di dialogo **Fine della sessione di lavoro di Windows** se gli aggiornamenti sono disponibili per l'installazione quando l'utente seleziona l'opzione **Spegni computer** nel menu **Start**.
  
Poiché gli aggiornamenti sono importanti per la protezione complessiva di tutti i computer, l'impostazione **Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro** è configurata su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: questa impostazione non ha alcun effetto se l'opzione **Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Windows Update\\Non visualizzare l'opzione "Installa aggiornamenti e spegni"** nella finestra di dialogo **Fine della sessione di lavoro di Windows** è su **Abilitato**.
  
###### Configura Aggiornamenti automatici
  
Questa impostazione di criterio consente di specificare se i computer riceveranno aggiornamenti per la protezione da Windows Update o WSUS. Se si configura questa impostazione su **Abilitato**, il sistema operativo identifica la disponibilità di una connessione di rete e la utilizza per ricercare aggiornamenti sul sito Web Windows Update o sul sito Intranet specificato che si applicano a tali computer.
  
Una volta configurata questa impostazione di criterio su **Abilitato**, selezionare una delle tre opzioni seguenti nella finestra di dialogo delle proprietà di **Configura Aggiornamenti automatici** per specificare come dovrà operare il servizio:
  
1.  **Avvisa prima di scaricare gli aggiornamenti e prima di installarli nel computer in uso.**
  
2.  **Scarica automaticamente gli aggiornamenti e avvisa quando sono pronti per l'installazione (impostazione predefinita)**
  
3.  **Scarica automaticamente gli aggiornamenti ed esegui l'installazione in base alla pianificazione specificata di seguito.**
  
Se si disattiva questa impostazione di criterio, sarà necessario scaricare e installare manualmente gli aggiornamenti disponibili dal sito Web [Windows Update](http://windowsupdate.microsoft.com/) all'indirizzo http://windowsupdate.microsoft.com.
  
L'impostazione **Configura Aggiornamenti automatici** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici
  
Se questa impostazione di criterio è attivata, il computer attenderà che un utente che ha effettuato l'accesso lo riavvii per completare un'installazione pianificata; in caso contrario, il computer si riavvierà automaticamente. Quando attivata, questa impostazione impedisce inoltre ad Aggiornamenti automatici di riavviare automaticamente i computer nel corso di un'installazione pianificata. Se un utente ha effettuato l'accesso a un computer quando Aggiornamenti automatici richiede di riavviarlo per completare l'installazione degli aggiornamenti, all'utente sarà inviata una notifica e potrà scegliere se ritardare il riavvio. Aggiornamenti automatici non rivelerà aggiornamenti futuri finché il computer non viene riavviato.
  
Se l'impostazione **Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici** è configurata su **Disabilitato** o **Non configurato**, Aggiornamenti automatici comunicherà all'utente che il computer si riavvierà automaticamente entro 5 minuti per completare l'installazione. Se i riavvii automatici costituiscono un problema, è possibile configurare l'impostazione **Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici** su **Abilitato.** Se si attiva questa impostazione, configurare i computer client in modo che vengano riavviati dopo il normale orario di ufficio per assicurare che l'installazione venga completata.
  
L'impostazione **Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici** è configurata su **Disabilitato** per i due ambienti trattati in questo capitolo.
  
**Nota:** questa impostazione funziona solo quando l'opzione Aggiornamenti automatici è configurata per effettuare installazioni pianificate degli aggiornamenti. Se l'impostazione **Configura Aggiornamenti automatici** è impostata su **Disabilitato**, non funzionerà. Di norma, è necessario un riavvio per completare l'installazione degli aggiornamenti.
  
###### Nuova pianificazione installazioni pianificate Aggiornamenti automatici
  
Questa impostazione di criterio determina il periodo di tempo che deve trascorrere prima che le installazioni pianificate in precedenza di Aggiornamenti automatici vengano eseguite una volta che il sistema è stato avviato. Se si configura questa impostazione su **Abilitato**, verrà eseguita l'installazione precedentemente pianificata al successivo avvio del computer una volta trascorso un numero specifico di minuti. Se si configura questa impostazione su **Disabilitato** o **Non configurato**, le installazioni precedentemente pianificate verranno eseguite durante la successiva fase di installazione prestabilita.
  
L'impostazione **Nuova pianificazione installazioni pianificate Aggiornamenti automatici** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo. Una volta attivata questa impostazione, è possibile impostare un tempo di attesa predefinito adatto all'ambiente.
  
**Nota:** questa impostazione funziona solo quando l'opzione Aggiornamenti automatici è configurata per effettuare installazioni pianificate degli aggiornamenti. Se **Configura Aggiornamenti automatici** è su **Disabilitato**, l'impostazione **Nuova pianificazione installazioni pianificate Aggiornamenti automatici** non ha effetto. È possibile attivare queste due impostazioni per assicurare che l'esecuzione delle installazioni mancanti sia pianificata ad ogni riavvio del computer.
  
###### Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet
  
Questa impostazione consente di specificare il server della rete Intranet che ospiterà gli aggiornamenti provenienti dai siti Web Microsoft Update. Questo servizio potrà essere utilizzato per eseguire l'aggiornamento automatico dei computer della rete. L'impostazione consente di specificare un server WSUS sulla rete da utilizzare come servizio di aggiornamento interno. Il client Aggiornamenti Automatici collaborerà con il server WSUS per ricercare aggiornamenti nel servizio che si applicano ai computer della rete.
  
L'impostazione **Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: l'impostazione **Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet** non ha effetto se l'impostazione **Configura Aggiornamenti automatici** è disattivata.
  
#### System
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema**
  
La figura seguente illustra le sezioni dei Criteri di gruppo che saranno interessate dalle modifiche alle impostazione in questa sezione:
  
[![](images/Cc163076.SGFG0403(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0403_big(it-it,technet.10).gif)
  
**Figure 4.3 Struttura dei Criteri di gruppo per la Configurazione computer, Sistema**
  
La seguente tabella riassume le impostazioni di sistema consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.18 Impostazioni di sistema consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disattiva riproduzione automatica</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato -<br />
Tutte le unità</td>
<td style="border:1px solid black;">Attivato -<br />
Tutte le unità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disattiva richiesta ricerca driver periferiche in Windows Update</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Disattiva riproduzione automatica
  
La riproduzione automatica inizia a leggere da un'unità non appena vi si inserisce un supporto multimediale, avviando immediatamente il file di installazione dei programmi o dei supporti audio. Un pirata informatico potrebbe utilizzare questa funzionalità per lanciare un programma con lo scopo di danneggiare il computer o i dati su di esso. Con l'impostazione **Disattiva riproduzione automatica** è possibile disabilitare la funzionalità di riproduzione automatica. La riproduzione automatica è disattivata per impostazione predefinita su alcuni tipi di unità removibili, come i dischi floppy e le unità di rete, ma non sulle unità CD-ROM.
  
L'impostazione **Disattiva riproduzione automatica** è configurata su **Attivato - Tutte le unità** solo per l'ambiente SSLF. Tuttavia, questa impostazione di criterio è impostata su **Non configurato** per l'ambiente EC.
  
**Nota**: non è possibile utilizzare questa impostazione di criterio per attivare la riproduzione automatica sulle unità del computer in cui è disabilitata per impostazione predefinita, come i dischi floppy e le unità di rete.
  
##### Disattiva richiesta ricerca driver periferiche in Windows Update
  
Questa impostazione di criterio verifica se all'amministratore viene richiesto di ricercare driver di periferiche in Windows Update utilizzando Internet. Se questa impostazione è su **Abilitato**, agli amministratori non verrà richiesto di eseguire la ricerca in Windows Update. Se questa impostazione e **Disattiva ricerca driver periferiche in Windows Update** sono impostate su **Disabilitato** o **Non configurato**, verrà chiesto il consenso dell'amministratore prima di ricercare driver di periferiche in Windows Update.
  
Poiché è rischioso scaricare driver da Internet, l'impostazione **Disattiva richiesta ricerca driver periferiche in Windows Update** è configurata su **Abilitato** per l'ambiente SSLF e su **Disabilitato** per l'ambiente EC. Questo perché i tipi di attacchi che possono utilizzare il download di un driver saranno generalmente contenuti da una corretta gestione delle risorse aziendali.
  
**Nota**: questa impostazione è efficace solo se **Disattiva ricerca driver periferiche in Windows Update** in **Modelli amministrativi/Sistema/Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet** è **Disabilitato** o **Non configurato**.
  
##### Accesso
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Accesso**
  
La seguente tabella riassume le impostazioni di accesso consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.19 Impostazioni di accesso consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non elaborare l'elenco di esecuzione precedente</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non elaborare l'elenco di esecuzione unica</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non elaborare l'elenco di esecuzione precedente
  
Questa impostazione di criterio consente di ignorare l'elenco di esecuzione, che è un elenco di programmi che Windows XP esegue automaticamente all'avvio. Gli elenchi di esecuzione personalizzati per Windows XP sono memorizzati nel Registro di sistema nei percorsi seguenti:
  
-   **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Run**
  
-   **HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Run**
  
È possibile attivare l'impostazione **Non elaborare l'elenco di esecuzione precedente** per evitare che un utente malintenzionato esegua un programma ogni volta che Windows XP viene avviato, compromettendo così i dati sul computer o causando altri danni. Quando questa impostazione è attivata, certi programmi del sistema non possono essere eseguiti, ad esempio i software antivirus e i programmi di distribuzione e monitoraggio del software. Microsoft consiglia di valutare il livello di pericolo per l'ambiente prima di decidere di utilizzare questa impostazione di criterio nell'organizzazione.
  
L'impostazione **Non elaborare l'elenco di esecuzione precedente** è **Non configurato** per l'ambiente EC ed è **Attivato** per l'ambiente SSLF.
  
###### Non elaborare l'elenco di esecuzione unica
  
Questa impostazione di criterio consente di ignorare l'elenco di esecuzione unica, che è l'elenco di programmi che Windows XP esegue automaticamente all'avvio. La differenza tra questa impostazione e **Non elaborare l'elenco di esecuzione precedente** consiste nel fatto che i programmi di questo elenco vengono eseguiti una sola volta al successivo riavvio del computer client. I programmi di installazione vengono a volte aggiunti a questo elenco per completare le installazioni dopo il riavvio del computer client. Se si attiva questa impostazione, i pirati informatici non saranno in grado di utilizzare l'elenco di esecuzione unica per lanciare applicazioni illegali, metodo di attacco comune nel passato. Un utente malintenzionato può utilizzare l'elenco di esecuzione unica per installare un programma che potrebbe compromettere la protezione dei computer client Windows XP.
  
**Nota**: gli elenchi di esecuzione unica personalizzati sono memorizzati nel Registro di sistema nel percorso seguente: **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce.**
  
L'impostazione **Non elaborare l'elenco di esecuzione unica** dovrebbe causare una perdita di funzionalità minima agli utenti dell'ambiente, specialmente se i computer client sono stato configurati con il software standard aziendale completo prima che questa impostazione fosse applicata attraverso i criteri di gruppo.
  
L'impostazione **Non elaborare l'elenco di esecuzione unica** è **Non configurato** per l'ambiente EC e **Attivato** per l'ambiente SSLF.
  
##### Criteri di gruppo
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Criteri di gruppo**
  
**Tabella 4.20 Impostazioni dei criteri di gruppo consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Elaborazione del criterio di Registro di sistema</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Elaborazione del criterio di Registro di sistema
  
Questa impostazione consente di definire il momento in cui i criteri del Registro di sistema verranno aggiornati. Si applica a tutti i criteri contenuti nella cartella Modelli amministrativi e a tutti gli altri criteri che memorizzano i valori nel Registro di sistema. Se questa impostazione di criterio è attivata, sono disponibili le seguenti opzioni:
  
-   **Non applicare durante l'elaborazione periodica in background.**
  
-   **Elabora anche se gli oggetti Criteri di gruppo non sono stati modificati.**
  
Alcune impostazioni configurate attraverso i Modelli amministrativi vengono definite in aree del Registro di sistema accessibili agli utenti. Le modifiche apportate dagli utenti a queste impostazioni saranno sovrascritte se viene attivata questa impostazione di criterio.
  
**Elaborazione del criterio di Registro di sistema** è configurata su **Abilitato** per entrambi gli ambienti descritti in questo capitolo.
  
##### Assistenza remota
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Assistenza remota**
  
La seguente tabella riassume le impostazioni di Assistenza remota consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.21 Impostazioni di Assistenza remota consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Offri Assistenza Remota</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Richiedi Assistenza Remota</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
###### Offri Assistenza Remota
  
Questa impostazione di criterio determina se un addetto all'assistenza o un amministratore di sistema (un "esperto") possa offrire assistenza remota ai computer dell'ambiente senza che l'utente ne faccia richiesta esplicita tramite posta elettronica, messaggistica immediata o altro canale di trasmissione.
  
**Nota**: un esperto non potrà collegarsi al computer senza essere identificato oppure controllarlo senza l'opportuna autorizzazione dell'utente. Quando l'esperto tenta di connettersi, l'utente può comunque scegliere di rifiutare la connessione o di fornire privilegi di sola lettura. L'utente deve esplicitamente fare clic sul pulsante **Sì** per consentire all'esperto di controllare la workstation in modalità remota dopo che l'impostazione **Offri Assistenza Remota** è stata configurata su **Abilitato.**
  
Se questa impostazione di criterio è attivata, sono disponibili le seguenti opzioni:
  
-   **Consenti solo di visualizzare il computer**
  
-   **Consenti controllo remoto del computer**
  
Quando si configura questa impostazione di criterio, è inoltre possibile specificare l'elenco degli utenti o dei gruppi di utenti a cui è consentita l'offerta di assistenza remota, denominati "assistenti".
  
**Per configurare l'elenco degli assistenti**
  
1.  Nel finestra di configurazione dell'impostazione **Offri Assistenza Remota**, fare clic su **Mostra.** Si aprirà una nuova finestra nella quale è possibile inserire i nomi degli assistenti.
  
2.  Aggiungere ciascun utente o gruppo all'elenco degli **assistenti** in uno dei formati seguenti:
  
    -   *&lt;Nome dominio&gt;*\\*&lt;Nome utente&gt;*
  
    -   *&lt;Nome dominio&gt;*\\*&lt;Nome gruppo&gt;*
  
Se si disattiva questa impostazione o non la si configura, né utenti né gruppi possono offrire assistenza remota non richiesta agli utenti dei computer dell'ambiente.
  
L'impostazione **Offri Assistenza Remotanon è configurata** per l'ambiente EC. Tuttavia, questa impostazione di criterio è configurata su **Disabilitato** per l'ambiente SSLF, in modo da impedire l'accesso ai computer client Windows XP sulla rete.
  
###### Richiedi Assistenza Remota
  
Questa impostazione di criterio determina se i computer client Windows XP dell'ambiente possono richiedere assistenza remota. È possibile attivare questa impostazione per consentire agli utenti di richiedere assistenza remota da parte degli amministratori di sistema ("esperti").
  
**Nota**: gli esperti non potranno collegarsi a un computer senza essere identificati oppure controllarlo senza l'autorizzazione dell'utente. Quando un esperto tenta di connettersi, l'utente può comunque scegliere di rifiutare la connessione o di fornire privilegi di sola lettura. L'utente deve esplicitamente fare clic sul pulsante **Sì** per consentire all'esperto di controllare la workstation in modalità remota.
  
Se l'impostazione **Richiedi Assistenza Remota** è attivata, sono disponibili le seguenti opzioni:
  
-   **Consenti controllo remoto del computer**
  
-   **Consenti solo di visualizzare il computer**
  
Inoltre, le opzioni seguenti sono disponibili per configurare l'intervallo di tempo nel quale una richiesta di assistenza di un utente è valida:
  
-   **Durata massima ticket (valore):**
  
-   **Durata massima ticket (unità): ore, minuti o giorni**
  
Quando un ticket (la richiesta di assistenza) scade, l'utente deve inviare un'altra richiesta prima che un esperto possa connettersi al computer. Se si disattiva l'impostazione **Richiedi Assistenza Remota**, gli utenti non possono inviare le richieste di assistenza e l'esperto non può connettersi ai loro computer.
  
Se l'impostazione **Richiedi Assistenza Remota** non è configurata, gli utenti possono configurarla attraverso il Pannello di controllo. Le seguenti impostazioni sono attivate per impostazione predefinita nel Pannello di controllo: **Assistenza remota su richiesta**, **Supporto buddy** e **Controllo remoto.** Il valore per la **Durata massima ticket** è impostato su **30 giorni.** Se questa impostazione di criterio è disattivata, non sarà possibile accedere ai computer Windows XP sulla rete.
  
L'impostazione **Richiedi Assistenza Remota** è **Non configurato** per l'ambiente EC ed è configurata su **Disabilitato** per l'ambiente SSLF.
  
##### Segnalazione errori
  
Queste impostazioni controllano la modalità di segnalazione degli errori del sistema operativo e delle applicazioni. Nella configurazione predefinita, quando si verifica un errore, una finestra pop-up chiede all'utente se desidera inviare una segnalazione di errore a Microsoft. Microsoft si serve di criteri rigorosi per proteggere i dati che vengono ricevuti tramite queste segnalazioni. Tuttavia, i dati sono trasmessi nel formato non crittografato, che rappresenta un potenziale rischio per la protezione.
  
Microsoft mette a disposizione delle organizzazioni lo strumento Segnalazione errori a server interno per raccogliere le segnalazioni in locale e non inviarle su Internet. Microsoft consiglia di utilizzare lo strumento Segnalazione errori a server interno nell'ambiente SSLF per evitare l'esposizione di informazioni riservate su Internet. Ulteriori informazioni su questo strumento sono disponibili nella sezione "Ulteriori Informazioni" alla fine di questo capitolo.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Segnalazione errori**
  
La seguente tabella riassume le impostazioni di Segnalazione errori consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.22 Impostazioni di Segnalazione errori consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Visualizza notifica errori</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configura segnalazione errori</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Visualizza notifica errori
  
Questa impostazione di criterio consente di determinare se i messaggi di errore vengono mostrati agli utenti sullo schermo del computer. Se si attiva questa impostazione di criterio, verrà inviata una notifica quando si verifica un errore e gli utenti avranno accesso ai relativi dettagli. Se disattivata, gli utenti non potranno visualizzare le notifiche di errore.
  
Quando si verifica un errore, è importante che l'utente sia consapevole del problema. Gli utenti non lo saranno se si disattiva l'impostazione **Visualizza notifica errori**. Per questa ragione, l'impostazione **Visualizza notifica errori** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Configura segnalazione errori
  
Questa impostazione di criterio consente di determinare se gli errori verranno segnalati o meno. Attivando questa impostazione, l'utente avrà la possibilità di segnalare gli errori a Microsoft tramite Internet oppure a una condivisione file aziendale. Se questa impostazione di criterio è attivata, sono disponibili anche le seguenti opzioni:
  
-   **Non visualizzare collegamenti a siti Microsoft con ulteriori informazioni sugli errori**
  
-   **Non includere file aggiuntivi**
  
-   **Non includere informazioni aggiuntive sul computer**
  
-   **Forza modalità di accodamento per gli errori dell'applicazione**
  
-   **Percorso file caricamento aziendale**
  
-   **Sostituisci le occorrenze della parola Microsoft con**
  
Se l'impostazione **Configura segnalazione errori** è disattivata, gli utenti non potranno segnalare gli errori. Se l'impostazione **Visualizza notifica errori** è attivata, gli utenti riceveranno le notifiche di errore ma non potranno segnalarli. L'impostazione **Configura segnalazione errori** consente di personalizzare una strategia di segnalazione degli errori per l'organizzazione e di raccogliere le segnalazioni per un'analisi locale.
  
L'impostazione **Configura segnalazione errori** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo. Inoltre, per l'ambiente SSLF sono state selezionate le seguenti opzioni:
  
-   **Non includere file aggiuntivi**
  
-   **Non includere informazioni aggiuntive sul computer**
  
-   **Forza modalità di accodamento per gli errori dell'applicazione**
  
È possibile scegliere anche l'opzione **Percorso file caricamento aziendale** e includere il percorso nel server sul quale è installato lo strumento Segnalazione errori a server interno. È consigliabile valutare le necessità dell'organizzazione per determinare quali di queste opzioni utilizzare.
  
##### RPC (Remote Procedure Call)
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Modelli amministrativi\\Sistema\\RPC**
  
La seguente tabella riassume le impostazioni RPC consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.23 Impostazioni RPC consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Restrizioni per client RPC non autenticati</td>
<td style="border:1px solid black;">Attivato – Autenticato</td>
<td style="border:1px solid black;">Attivato – Autenticato</td>
<td style="border:1px solid black;">Attivato – Autenticato</td>
<td style="border:1px solid black;">Attivato – Autenticato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione client mapping degli endpoint RPC</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Restrizioni per client RPC non autenticati
  
Abilitando questa impostazione di criterio, è possibile configurare il runtime RPC in un server RPC per limitare i client RPC non autenticati che si connettono ai server RPC. Un cliente è considerato non autenticato se utilizza un named pipe per comunicare col server o se utilizza la Protezione RPC. Le interfacce RPC che hanno chiesto specificatamente di essere accessibili da client non autenticati possono essere esenti da questa restrizione, in base al valore scelto per questo criterio. Se questa impostazione di criterio è attivata, sono disponibili i seguenti valori:
  
-   **Nessuno**. Consente a tutti i client RPC di connettersi ai server RPC in esecuzione sul computer a cui il criterio è applicato.
  
-   **Autenticato**. Consente soltanto a client RPC autenticati di connettersi ai server RPC in esecuzione sul computer su cui il criterio è applicato. Alle interfacce che hanno chiesto di essere esenti da questa restrizione sarà concessa un'esenzione.
  
-   **Autenticato senza eccezioni**. Consente soltanto a client RPC autenticati di connettersi ai server RPC in esecuzione sul computer su cui il criterio è applicato. Non sono consentite eccezioni.
  
Poiché la comunicazione RPC non autenticata può creare vulnerabilità nella protezione, l'impostazione **Restrizioni per client RPC non autenticati** è configurata su **Abilitato** e il valore Esecuzione **Restrizioni runtime RPC client non autenticati da applicare** è impostato su **Autenticato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: le applicazioni RPC che non autenticano richieste di connessione in ingresso indesiderate potrebbero non funzionare correttamente quando tale configurazione è attiva. Assicurarsi di verificare le applicazioni prima di distribuire tale impostazione nell'ambiente. Sebbene il valore Autenticato per questa impostazione non sia completamente sicuro, può essere utile per assicurare la compatibilità delle applicazioni nell'ambiente.
  
###### Autenticazione client mapping degli endpoint RPC
  
Se si attiva questa impostazione di criterio, i computer client che comunicano con questo computer sono obbligati a fornire l'autenticazione prima che venga stabilita la comunicazione RPC. Per impostazione predefinita, i client RPC non utilizzano l'autenticazione per comunicare con il servizio di mapping degli endpoint del server RPC quando richiedono l'endpoint di un server. Tuttavia, questa impostazione predefinita è stata modificata per l'ambiente SSLF in modo da richiedere l'autenticazione ai computer client prima di consentire la comunicazione RPC.
  
##### Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet
  
Il gruppo Impostazioni di comunicazione Internet contiene parecchie impostazioni di configurazione. Questa guida consiglia di limitare molte di queste impostazioni, principalmente per migliorare la riservatezza dei dati sui sistemi informatici. Se queste impostazioni non sono limitate, le informazioni potrebbero essere intercettate e utilizzate dagli aggressori. Sebbene sia raro che si verifichi questo tipo di attacco, la corretta configurazione di queste impostazioni protegge l'ambiente da attacchi futuri.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Modelli amministrativi\\Sistema\\Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet**
  
La seguente tabella riassume le impostazioni di comunicazione Internet consigliate. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.24 Impostazioni di comunicazione Internet consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disattiva l'operazione per file e cartelle Pubblica sul Web</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disattiva Analisi utilizzo software Windows Messenger</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disattiva aggiornamenti file contenuto Ricerca guidata</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disattiva stampa su HTTP</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disattiva download driver di stampa su HTTP</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disattiva ricerca driver periferiche in Windows Update</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Disattiva l'operazione per file e cartelle Pubblica sul Web
  
Questa impostazione di criterio specifica se visualizzare le operazioni **Pubblica file sul Web**, **Pubblica cartella sul Web** e **Pubblica elementi selezionati sul Web** in Operazioni file e cartella nelle cartelle di Windows. La Pubblicazione guidata sul Web scarica sul computer un elenco di provider e consente agli utenti di pubblicare contenuto sul Web.
  
Se si configura l'impostazione **Disattiva l'operazione per file e cartelle Pubblica sul Web** su **Abilitato**, queste opzioni vengono rimosse da Operazioni file e cartella nelle cartelle di Windows. Per impostazione predefinita, l'opzione di pubblicazione sul Web è disponibile. Poiché questa funzionalità potrebbe essere utilizzata per esporre contenuto protetto a un computer client Web non autenticato, questa impostazione è configurata su **Abilitato** sia per l'ambiente EC sia per l'ambiente SSLF.
  
###### Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet
  
Attraverso questa impostazione di criterio è possibile controllare se Windows scaricherà un elenco di provider per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet. Abilitando questa impostazione, si evita che Windows scarichi i provider; saranno visualizzati solo i provider di servizi memorizzati nel Registro di sistema locale.
  
Poiché l'impostazione **Disattiva** **l'operazione per file e cartelle Pubblica sul Web** è attivata per gli ambienti EC e SSLF (vedere l'impostazione precedente), questa opzione non è necessaria. Tuttavia, l'impostazione **Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet** è configurata su **Abilitato** per ridurre al minimo la superficie di attacco dei computer client e per assicurare che questa funzionalità non venga sfruttata in altri modi.
  
###### Disattiva Analisi utilizzo software Windows Messenger
  
Questa impostazione di criterio specifica se Windows Messenger raccoglie informazioni anonime sulla modalità di utilizzo del software e dei servizi di Windows Messenger. È possibile attivare questa impostazione per assicurare che Windows Messenger non raccolga informazioni di utilizzo e che non vengano visualizzate le impostazioni dell'utente per l'attivazione della raccolta di tali informazioni.
  
In ambienti aziendali di grandi dimensioni non è consigliabile consentire ai computer client gestiti di raccogliere informazioni. L'impostazione **Disattiva Analisi utilizzo software Windows Messenger** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo, al fine di evitare la raccolta delle informazioni.
  
###### Disattiva aggiornamenti file contenuto Ricerca guidata
  
Questa impostazione di criterio specifica se la Ricerca guidata deve scaricare automaticamente gli aggiornamenti di contenuto nel corso delle ricerche locali e in Internet. Configurando questa impostazione su **Abilitato**, la Ricerca guidata non scaricherà gli aggiornamenti di contenuto durante le ricerche.
  
L'impostazione **Disattiva Analisi utilizzo software Windows Messenger** è configurata su **Abilitato** per gli ambienti EC e SSLF, al fine di consentire il controllo di comunicazioni di rete non necessarie da ciascun computer client gestito.
  
**Nota**: le ricerche in Internet inviano comunque il testo della ricerca e altre informazioni sulla ricerca a Microsoft e al provider di ricerca prescelto. Se si seleziona la ricerca classica, la funzionalità di Ricerca guidata non sarà disponibile. È possibile scegliere la ricerca classica facendo clic su **Start**, **Cerca**, **Cambia preferenze**, quindi su **Change Internet Search Behavior**.
  
###### Disattiva stampa su HTTP
  
Questa impostazione di criterio disattiva la funzionalità di stampa su HTTP, che consente a un computer client di utilizzare stampanti su Intranet e Internet. Se si attiva questa impostazione, il computer client non potrà stampare tramite stampanti in Internet su HTTP.
  
Le informazioni trasmesse quando si stampa su HTTP non sono protette e possono essere intercettate da utenti malintenzionati. Per questa ragione, tale impostazione è raramente utilizzata negli ambienti aziendali. L'impostazione **Disattiva stampa su HTTP** è configurata su **Abilitato** per gli ambienti EC e SSLF, al fine di evitare una possibile violazione della protezione a causa di un processo di stampa non sicuro.
  
**Nota**: questa impostazione riguarda unicamente il lato client della stampa su Internet. Indipendentemente dalla configurazione, un computer può agire da server di stampa su Internet e mettere a disposizione stampanti condivise via HTTP.
  
###### Disattiva download driver di stampa su HTTP
  
Questa impostazione di criterio controlla se il computer può scaricare pacchetti di driver di stampa su HTTP. Per impostare la stampa su HTTP, i driver di stampa non disponibili nell'installazione standard del sistema operativo devono essere scaricati su HTTP.
  
L'impostazione **Disattiva download driver di stampa su HTTP** è configurata su **Abilitato** per evitare che i driver di stampa vengano scaricati su HTTP.
  
**Nota**: questa impostazione non evita che il computer client stampi tramite stampanti in Intranet o Internet su HTTP. Impedisce unicamente lo scaricamento di driver che non sono già installati in locale.
  
###### Disattiva ricerca driver periferiche in Windows Update
  
Questa impostazione di criterio specifica se Windows ricerca i driver di periferiche in Windows Update quando non sono presenti driver locali per una periferica.
  
Poiché è rischioso scaricare driver da Internet, l'impostazione **Disattiva ricerca driver periferiche in Windows Update** è configurata su **Abilitato** per l'ambiente SSLF e su **Disabilitato** per l'ambiente EC. Questo perché i tipi di attacchi che possono utilizzare il download di un driver saranno generalmente ridotti da una corretta gestione delle risorse aziendali e della configurazione.
  
**Nota**: vedere anche **Disattiva richiesta ricerca driver periferiche in Windows Update** in **Modelli amministrativi/Sistema**, che consente di gestire le richieste all'amministratore prima di ricercare i driver di periferiche in Windows Update se un driver non è presente in locale.
  
#### Rete
  
Non sono presenti configurazioni specifiche relative alla protezione nel contenitore Rete dei criteri di gruppo. Tuttavia, esistono diverse impostazioni molto importanti nel contenitore **Connessioni di rete\\Windows Firewall**, illustrate nelle seguenti sezioni.
  
La figura seguente illustra le sezioni dei Criteri di gruppo che saranno interessate dalle modifiche alle impostazione in questa sezione:
  
[![](images/Cc163076.SGFG0404(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0404_big(it-it,technet.10).gif)
  
**Figure 4.4 Struttura dei Criteri di gruppo per la Configurazione computer, Connessioni di rete**
  
#### Connessioni di rete\\Windows Firewall
  
Le impostazioni di Windows Firewall sono suddivise in due profili: il Profilo di dominio e il Profilo standard. Si utilizza il Profilo di dominio quando viene rilevato un ambiente di dominio e quando questo non è disponibile, si utilizza il Profilo standard.
  
Quando un'impostazione di Windows Firewall è **Consigliata** in una delle due tabelle seguenti, il valore specifico da utilizzare varierà per ciascuna organizzazione. Per esempio, ogni organizzazione avrà un elenco unico di applicazioni che richiederanno delle eccezioni definite per Windows Firewall. Quindi, questa guida non è in grado di definire un elenco utile.
  
Per determinare per quali applicazioni o porte è necessaria un'eccezione, è utile attivare la registrazione e il controllo di Windows Firewall e la tracciatura di rete. Per ulteriori informazioni, vedere l'articolo "[Configuring a Computer for Windows Firewall Troubleshooting](http://technet.microsoft.com/en-us/library/cc783179.aspx)" (in inglese), disponibile all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/Operations/bfdeda55-46fc-4b53-b4cd-c71838ef4b41.mspx.
  
Per ulteriori informazioni sulla modalità di utilizzo di NLA (Network Location Awareness) da parte di Windows XP per determinare il tipo di rete a cui è connesso, vedere l'articolo "[Network Determination Behavior for Network-Related Group Policy Settings](http://technet.microsoft.com/en-us/library/bb878049.aspx)" (in inglese) sul sito Web di Microsoft all'indirizzo www.microsoft.com/technet/community/columns/cableguy/cg0504.mspx.
  
Di norma, il Profilo di dominio è configurato in modo che sia meno restrittivo del Profilo standard, perché un ambiente di dominio fornisce spesso livelli aggiuntivi di protezione.
  
I nomi delle impostazioni di criterio sono gli stessi per entrambi i profili. Le tabelle seguenti riassumono le impostazioni per i due profili, mentre informazioni più approfondite sono fornite nelle successive sottosezioni.
  
##### Connessioni di rete\\Windows Firewall\\Profilo di dominio
  
Le impostazioni in questa sezione configurano il Profilo di dominio di Windows Firewall.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Modelli amministrativi\\Rete\\Connessioni di rete\\Windows Firewall\\Profilo di dominio**
  
**Tabella 4.25 Impostazioni del Profilo di dominio di Windows Firewall consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Proteggi tutte le connessioni di rete</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non consentire eccezioni</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Definisci le eccezioni programmi</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezioni programmi locali</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezione per amministrazione remota</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezione per condivisione file e stampanti</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezioni ICMP</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezione per Desktop remoto</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezione per framework UPnP</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Proibisci notifiche</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci risposte unicast a richieste multicast o broadcast</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Definisci eccezioni porte</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezioni porte locali</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
**Nota**: quando un'impostazione di Windows Firewall è **Raccomandata** in questa tabella, il valore specifico da utilizzare varierà per ciascuna organizzazione. Per esempio, ogni organizzazione avrà un elenco unico di applicazioni che richiederanno delle eccezioni definite per Windows Firewall. Quindi, questa guida non è in grado di definire un elenco utile.
  
##### Connessioni di rete\\Windows Firewall\\Profilo standard
  
Le impostazioni in questa sezione configurano il profilo standard di Windows Firewall. Questo profilo è spesso più restrittivo del Profilo di dominio, che presume che un ambiente di dominio fornisca un livello di protezione base. Si suppone che il Profilo standard sia utilizzato quando un computer è su una rete non attendibile, come la rete di hotel o un punto di accesso pubblico senza fili. Tali ambienti rappresentano rischi sconosciuti e richiedono precauzioni di protezione aggiuntive.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione all'interno dell'Editor oggetti Criteri di gruppo:
  
**Modelli amministrativi\\Rete\\Connessioni di rete\\Windows Firewall\\Profilo standard**
  
**Tabella 4.26 Impostazioni del Profilo standard di Windows Firewall consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Desktop EC</th>
<th style="border:1px solid black;" >Computer portatile EC</th>
<th style="border:1px solid black;" >Desktop SSLF</th>
<th style="border:1px solid black;" >Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Proteggi tutte le connessioni di rete</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non consentire eccezioni</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Definisci le eccezioni programmi</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezioni programmi locali</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezione per amministrazione remota</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezione per condivisione file e stampanti</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezioni ICMP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti eccezione per Desktop remoto</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezione per framework UPnP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Proibisci notifiche</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci risposte unicast a richieste multicast o broadcast</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Definisci eccezioni porte</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
<td style="border:1px solid black;">Sconsigliato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti eccezioni porte locali</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
**Nota**: quando un'impostazione di Windows Firewall è **Consigliata** in questa tabella, il valore specifico da utilizzare varierà per ciascuna organizzazione. Per esempio, ogni organizzazione avrà un elenco unico di applicazioni che richiederanno delle eccezioni definite per Windows Firewall. Quindi, questa guida non è in grado di definire un elenco utile.
  
###### Windows Firewall: proteggi tutte le connessioni di rete
  
Questa impostazione di criterio attiva Windows Firewall, che sostituisce Firewall connessione Internet su tutti i computer dotati di Windows XP con SP2. Questa guida consiglia di configurare questa impostazione su **Abilitato** per proteggere tutte le connessioni di rete per i computer di tutti gli ambienti trattati.
  
Se l'impostazione **Windows Firewall: proteggi tutte le connessioni di rete** è configurata su **Disabilitato**, Windows Firewall non è attivo e tutte le altre impostazioni di Windows Firewall vengono ignorate.
  
**Nota**: se si abilita questa impostazione di criterio, Windows Firewall viene eseguito e ignora il criterio **Configurazione computer\\Modelli amministrativi\\Rete\\Connessioni di Rete\\Proibisci l'uso del Firewall Connessione Internet nella rete del dominio DNS**.
  
###### Windows Firewall: non consentire eccezioni
  
Questa impostazione di criterio specifica che Windows Firewall deve bloccare tutti i messaggi indesiderati in ingresso. Ignora tutte le altre impostazioni di Windows Firewall che consentono tali messaggi. Se si abilita questa impostazione nel componente Windows Firewall del Pannello di controllo, la casella **Non consentire eccezioni** sarà selezionata e gli amministratori non potranno deselezionarla.
  
Molti ambienti contengono applicazioni e servizi che devono poter ricevere comunicazioni indesiderate in ingresso, come parte del loro normale funzionamento. In tali ambienti potrebbe essere necessario configurare l'impostazione **Windows Firewall: non consentire eccezioni** su **Disabilitato** per consentire alle applicazioni e ai servizi di funzionare correttamente. Tuttavia, prima di configurare questa impostazione è consigliabile verificare l'ambiente per determinare con esattezza quali comunicazioni devono essere consentite.
  
**Nota**: questa impostazione fornisce una solida difesa contro i pirati informatici e dovrebbe essere configurata su **Abilitato** nelle situazioni in cui è necessaria una protezione completa dagli attacchi esterni, come la diffusione di un nuovo worm di rete. L'impostazione di questo criterio su **Disabilitato** consente a Windows Firewall di applicare altre impostazioni di criterio che consentano l'ingresso di messaggi indesiderati.
  
###### Windows Firewall: definisci le eccezioni programmi
  
Alcune applicazioni possono avere bisogno di aprire e utilizzare le porte di rete che non sono normalmente abilitate da Windows Firewall. L'impostazione **Windows Firewall: definisci eccezioni programmi** consente di visualizzare e modificare l'elenco eccezioni di programmi definito nei Criteri di gruppo.
  
Se questa impostazione di criterio è su **Abilitato**, è possibile visualizzare e modificare l'elenco eccezioni di programmi. Se si aggiunge un programma a questo elenco e si imposta lo stato su **Abilitato**, tale programma può ricevere messaggi in ingresso indesiderati su qualunque porta la cui apertura viene richiesta a Windows Firewall, anche se quella porta è bloccata da un'altra impostazione di criterio. Se si configura questo criterio su **Disabilitato**, l'elenco eccezioni di programmi definito nei Criteri di gruppo viene cancellato.
  
**Nota**: se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza cercare errori. Poiché l'immissione non viene controllata, è possibile aggiungere programmi non ancora installati. È inoltre possibile creare accidentalmente più eccezioni per lo stesso programma con valori di stato o ambito in conflitto.
  
###### Windows Firewall: consenti eccezioni programmi locali
  
Questa impostazione di criterio consente di stabilire se gli amministratori possono utilizzare il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di porte locali. Disattivando questa impostazione di criterio si impedisce agli amministratori di definire un elenco di eccezioni programmi locali e assicura che le eccezioni derivino unicamente dai Criteri di gruppo. Se attivata, gli amministratori locali potranno utilizzare il Pannello di controllo per definire eccezioni programmi in locale.
  
Per i computer client aziendali, possono sussistere le condizioni che giustificano la definizione di eccezioni programmi locali. Queste condizioni possono includere applicazioni che non sono state analizzate durante la creazione dei criteri firewall dell'organizzazione o nuove applicazioni che richiedono una configurazione non standard della porta. Se si attiva l'impostazione **Windows Firewall: consenti eccezioni programmi locali** per tali situazioni, ricordare che la superficie di attacco dei computer interessati aumenta.
  
###### Windows Firewall: consenti eccezione per amministrazione remota
  
Molte organizzazioni approfittano dell'amministrazione remota del computer durante le attività quotidiane. Tuttavia, alcuni attacchi hanno sfruttato le porte utilizzate di norma dai programmi di amministrazione remoti; Windows Firewall può bloccare queste porte.
  
Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per amministrazione**. Se questa impostazione di criterio è attivata, il computer può ricevere messaggi in ingresso indesiderati per l'amministrazione remota sulle porte TCP 135 e 445. Questa impostazione di criterio consente inoltre a Svchost.exe e a Lsass.exe di ricevere messaggi in ingresso indesiderati e consente a servizi ospitati di aprire le porte aggiuntive assegnate dinamicamente, di norma nell'intervallo 1024-1034 ma potenzialmente in qualsiasi punto da 1024 a 65535. Per abilitare questa impostazione è necessario specificare gli indirizzi di IP o le sottoreti da cui sono consentiti tali messaggi in ingresso.
  
Se si configura l'impostazione **Windows Firewall: consenti eccezione per amministrazione** su **Disabilitato**, Windows Firewall non applicherà alcuna delle eccezioni descritte. L'impatto esercitato dalla configurazione di questa impostazione su **Disabilitato** potrebbe non essere accettabile per molte organizzazioni, poiché gli strumenti di amministrazione remota e quelli che effettuano la scansione delle vulnerabilità non funzionano. Perciò, Microsoft consiglia di attivare questa impostazione solo nelle organizzazioni in cui la protezione è un elemento fondamentale.
  
Per il Profilo di dominio, Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezione per amministrazione** su **Abilitato** per i computer nell'ambiente EC (se possibile) e su **Disabilitato** per i computer nell'ambiente SSLF. I computer nell'ambiente dovrebbero accettare le richieste di amministrazione remota da parte del minor numero di computer possibili. Per elevare al massimo la protezione fornita da Windows Firewall, assicurarsi di specificare soltanto gli indirizzi IP necessari e le sottoreti di computer utilizzati per l'amministrazione remota.
  
Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezione per amministrazione** su **Disabilitato** per tutti i computer nel Profilo standard, per evitare gli attacchi noti che utilizzano specificamente i punti deboli delle porte TCP 135 e 445.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità di Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
###### Windows Firewall: consenti eccezione per condivisione file e stampanti
  
Questa impostazione di criterio crea un'eccezione che consente di condividere file e stampanti configurando Windows Firewall in modo da aprire le porte UDP 137 e 138 e le porte TCP 139 e 445. Se si abilita questa impostazione di criterio, Windows Firewall apre queste porte in modo che il computer possa ricevere i processi di stampa e le richieste per l'accesso ai file condivisi. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi sono consentiti.
  
Se si disattiva l'impostazione **Windows Firewall: consenti eccezione per condivisione file e stampanti**, Windows Firewall blocca queste porte e impedisce al computer di condividere file e stampanti.
  
Poiché i computer dell'ambiente dotati di Windows XP non condividono di norma i file e le stampanti, Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezione per condivisione file e stampanti** su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità di Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
###### Windows Firewall: consenti eccezioni ICMP
  
Questa impostazione di criterio definisce la serie di tipi di messaggi ICMP (Internet Control Message Protocol) consentiti da Windows Firewall. Le utilità possono utilizzare i messaggi ICMP per determinare lo stato di altri computer. Per esempio, Ping utilizza il messaggio di richiesta echo.
  
Se l'impostazione **Windows Firewall: consenti eccezioni ICMP** è configurata su **Abilitato**, è necessario specificare quali tipi di messaggi ICMP Windows Firewall consente di inviare o ricevere. Se questo criterio è impostato su **Disabilitato**, Windows Firewall blocca tutti i tipi di messaggi ICMP in ingresso indesiderati e i tipi di messaggi ICMP in uscita contenuti nell'elenco. Di conseguenza, le utilità che si basano su ICMP potrebbero non funzionare.
  
Molti strumenti di aggressione approfittano dei computer che accettano i tipi di messaggi ICMP ed utilizzano questi messaggi per preparare vari attacchi. Tuttavia, alcune applicazioni richiedono certi messaggi ICMP per funzionare correttamente. I messaggi ICMP sono inoltre utilizzati per valutare le prestazioni della rete quando i criteri di gruppo vengono scaricati ed elaborati; se i messaggi ICMP sono bloccati, i criteri di gruppo potrebbero non venire applicati ai sistemi interessati. Per tale ragione, Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezioni ICMP** su **Disabilitato** quando possibile. Se l'ambiente richiede che alcuni messaggi ICMP attraversino Windows Firewall, configurare l'impostazione con i tipi di messaggio appropriati.
  
Quando il computer si trova su una rete non attendibile, l'impostazione **Windows Firewall: consenti eccezioni ICMP** dovrebbe essere configurata su **Disabilitato.**
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità di Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
###### Windows Firewall: consenti eccezione per Desktop remoto
  
Molte organizzazioni utilizzano connessioni Desktop remoto per le procedure di risoluzione dei problemi o per le normali attività. Tuttavia, alcuni attacchi sfruttano le porte tipicamente utilizzate dal desktop remoto.
  
Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per Desktop remoto**. Abilitando questa impostazione Windows Firewall apre la porta TCP 3389 per le connessioni in ingresso. Specificare inoltre gli indirizzi di IP o le sottoreti da cui è possibile ricevere questi messaggi in ingresso.
  
Se si disattiva questa impostazione di criterio, Windows Firewall blocca questa porta ed impedisce al computer di ricevere richieste di Desktop remoto. Se un amministratore tenta di aprire questa porta aggiungendola a un elenco di eccezioni porte locali, Windows Firewall non apre la porta.
  
Alcuni attacchi possono utilizzare una porta aperta 3389, perciò Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezione per Desktop remoto** su **Disabilitato** per l'ambiente SSLF. Per mantenere le capacità di gestione migliorate fornite da Desktop remoto, configurare è necessario questa impostazione su **Abilitato** per l'ambiente EC e specificare gli indirizzi di IP e le sottoreti dei computer utilizzati per l'amministrazione remota. I computer nell'ambiente dovrebbero accettare richieste di Desktop remoto da meno computer possibile.
  
###### Windows Firewall: consenti eccezione per framework UPnP
  
Questa impostazione di criterio consente a un computer di ricevere messaggi Plug and Play indesiderati inviati da periferiche di rete, come i router con firewall integrati. Per ricevere questi messaggi, Windows Firewall apre la porta TCP 2869 e porta UDP 1900.
  
Se si attiva l'impostazione **Windows Firewall: consenti eccezione per framework UPnP**, Windows Firewall apre queste porte in modo che il computer possa ricevere i messaggi Plug and Play. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi in ingresso sono consentiti. Se si disattiva questa impostazione di criterio, Windows Firewall blocca queste porte e impedisce al computer di ricevere messaggi Plug and Play.
  
Il blocco del traffico di rete UPnP riduce efficacemente l'esposizione agli attacchi dei computer nell'ambiente. Sulle reti attendibili, Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezione per framework UPnP** su **Disabilitato**, a meno che non si utilizzino periferiche UPnP sulla rete. Questa impostazione dovrebbe essere sempre su **Disabilitato** sulle reti non attendibili.
  
###### Windows Firewall: Proibisci notifiche
  
Windows Firewall può mostrare notifiche agli utenti quando un programma richiede che Windows Firewall aggiunga il programma all'elenco di eccezioni di programmi. Questa situazione si verifica quando i programmi tentano di aprire una porta e non sono autorizzati a farlo, a causa delle regole di Windows Firewall attuali.
  
L'impostazione **Windows Firewall: Proibisci notifiche** consente di scegliere se tali impostazioni devono essere mostrate agli utenti. Se questa impostazione è configurata su **Abilitato**, Windows Firewall impedisce la visualizzazione di queste notifiche. Se configurata su **Disabilitato**, Windows Firewall consente la visualizzazione di queste notifiche.
  
Di norma, gli utenti non possono aggiungere applicazioni e porte in risposta a questi messaggi negli ambienti EC o SSLF. In tali casi, questo messaggio informerà l'utente relativamente a un aspetto su cui non ha controllo e l'impostazione **Windows Firewall: Proibisci notifiche** deve essere configurata su **Abilitato.** In altri ambienti, dove le eccezioni sono consentite per alcuni utenti, l'impostazione deve essere configurata su **Disabilitato.**
  
###### Windows Firewall: impedisci risposte unicast a richieste multicast o broadcast
  
Questa impostazione di criterio impedisce a un computer di ricevere risposte unicast ai messaggi multicast o broadcast in uscita. Quando questa impostazione di criterio è abilitata ed il computer invia messaggi multicast o broadcast ad altri computer, Windows Firewall blocca le risposte unicast inviate da tali computer. Quando l'impostazione è disattivata e il computer invia un messaggio multicast o broadcast agli altri computer, Windows Firewall attende fino a tre secondi le risposte unicast dagli altri computer, quindi blocca tutte le successive risposte.
  
Generalmente, non è corretto ricevere risposte unicast a messaggi multicast o broadcast. Tali risposte possono indicare un attacco DoS (Denial of Service) o il tentativo di sondare un computer noto. Microsoft consiglia di configurare l'impostazione **Windows Firewall: Impedisci risposte unicast a richieste multicast o broadcast** su **Abilitato** per evitare questo tipo di attacco.
  
**Nota**: questa impostazione di criterio non ha effetto se il messaggio unicast è una risposta a un messaggio broadcast DHCP inviato dal computer. Windows Firewall permette sempre tali risposte unicast DHCP. Tuttavia, questa impostazione di criterio può interferire con i messaggi NetBIOS che rilevano conflitti di nome.
  
###### Windows Firewall: definisci eccezioni porte
  
L'elenco eccezioni porte di Windows Firewall deve essere definito dai Criteri di gruppo, che consente di gestire e distribuire centralmente le eccezioni di porta ed assicura che gli amministratori locali non creino impostazioni meno sicure.
  
Se si attiva l'impostazione **Windows Firewall: definisci eccezioni porte**, è possibile visualizzare e modificare l'elenco eccezioni porte definito dai Criteri di gruppo. Per visualizzare e modificare l'elenco eccezioni porte, configurare il criterio su **Abilitato** e fare clic sul pulsante **Mostra**. Se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza controllare la presenza di errori, il che significa che è possibile creare accidentalmente più voci per la stessa porta con valori di stato o ambito in conflitto.
  
Se si disattiva l'impostazione **Windows Firewall: definisci eccezioni porte**, l'elenco eccezioni porte definito dai Criteri di gruppo viene cancellato, ma altre impostazioni possono continuare ad aprire o bloccare le porte. Inoltre, se esiste un elenco di eccezioni porte locali, viene ignorato, a meno che non si abiliti l'impostazione **Windows Firewall: consenti eccezioni porte locali**.
  
Gli ambienti con applicazioni non standard che richiedono porte specifiche per essere aperti dovrebbero considerare le eccezioni di programmi invece delle eccezioni di porte. Microsoft consiglia di configurare l'impostazione **Windows Firewall: definisci eccezioni porte** su **Abilitato** e di specificare un elenco di eccezioni di porte solo quando non è possibile definire le eccezioni di programmi. Le eccezioni di programmi consentono a Windows Firewall di accettare il traffico di rete indesiderato soltanto mentre il programma specificato è in esecuzione, e le eccezioni di porta tengono sempre aperte le porte specificate.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità di Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
###### Windows Firewall: consenti eccezioni porte locali
  
Questa impostazione di criterio consente di stabilire se gli amministratori possono utilizzare il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di porte locali. Windows Firewall può utilizzare due elenchi di eccezioni di porte; l'altro è definito dall'impostazione **Windows Firewall: definisci eccezioni porte**.
  
Se si attiva l'impostazione **Windows Firewall: consenti eccezioni porte locali**, il componente Windows Firewall nel Pannello di controllo consente agli amministratori di definire un elenco di eccezioni di porte locali. Se si disattiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo non consente agli amministratori di definire tale elenco.
  
Di norma, gli amministratori locali non sono autorizzati a ignorare il criterio dell'organizzazione e a stabilire i propri elenchi di eccezioni porte negli ambienti EC o SSLF. Per tale ragione, Microsoft consiglia di configurare l'impostazione **Windows Firewall: consenti eccezioni porte locali** su **Disabilitato.**
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni configurazione utente
  
Le sezioni rimanenti di questo capitolo descrivono le raccomandazioni relative alle impostazioni configurazione utente. Ricordare che queste impostazioni devono essere applicate agli utenti e non ai computer. Devono essere implementate in un criterio di gruppo collegato alla OU che contiene gli utenti che si desidera configurare. Consultare la Figura 2.3, "Espansione della struttura dell'unità organizzativa per computer desktop e portatili con Windows XP" nel Capitolo 2 come riferimento. Queste impostazioni vengono configurate nell'Editor oggetti Criteri di gruppo nel seguente percorso:
  
**Configurazione utente\\Modelli amministrativi**
  
Questo percorso è mostrato in contesto nella figura seguente:
  
[![](images/Cc163076.SGFG0405(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0405_big(it-it,technet.10).gif)
  
**Figura 4.5 Struttura dei Criteri di gruppo per la Configurazione utente**
  
Applicare queste impostazioni attraverso un GPO collegato a una OU che contiene gli account utente.
  
**Nota**: le impostazioni di configurazione utente vengono applicate a tutti i computer dotati di Windows XP ai quali un utente accede in un dominio di Active Directory. Tuttavia, le impostazioni di configurazione del computer si riferiscono a tutti i computer client gestiti da un GPO in Active Directory, indipendentemente dall'utente che accede al computer. Perciò, le tabelle in questa sezione contengono solo impostazioni consigliate per gli ambienti EC e SSLF trattati in questo capitolo. Non sono presenti indicazioni relative ai computer portatili o ai desktop per queste impostazioni.
  
#### Componenti di Windows
  
La figura seguente illustra le sezioni dei Criteri di gruppo che saranno interessate dalle modifiche alle impostazioni nella sezione Componenti di Windows:
  
[![](images/Cc163076.SGFG0406(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0406_big(it-it,technet.10).gif)
  
**Figure 4.6 Struttura dei Criteri di gruppo per la Configurazione utente, Componenti di Windows**
  
##### Internet Explorer
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\**  
**Internet Explorer**
  
La seguente tabella riassume le impostazioni di configurazione utente consigliate per Internet Explorer. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.27 Impostazioni di Configurazione utente consigliate per Internet Explorer**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Computer EC</th>
<th style="border:1px solid black;" >Computer SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Menu Browser\Disattiva l'opzione Salva l'applicazione su disco</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pannello di controllo Internet\Disattiva la scheda Avanzate</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pannello di controllo Internet\Disattiva la scheda Protezione</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pagine non in linea\Impedisci l'aggiunta di canali</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pagine non in linea\Non consentire l'aggiunta di pianificazioni per le pagine non in linea</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pagine non in linea\Disattiva tutte le pagine non in linea pianificate</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pagine non in linea\Disattiva completamente interfaccia utente canali</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pagine non in linea\Disattiva il download dei file di dati della sottoscrizione al sito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pagine non in linea\Impedisci la modifica e la creazione di gruppi di pianificazioni</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pagine non in linea\Non consentire la modifica delle pianificazioni per le pagine non in linea</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pagine non in linea\Disattiva la registrazione del numero di accessi alle pagine non in linea</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pagine non in linea\Impedisci la rimozione di canali</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pagine non in linea\Non consentire la rimozione di pianificazioni per le pagine non in linea</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configura Outlook Express</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci la modifica delle impostazioni della scheda Avanzate</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci la modifica delle impostazioni di Configurazione automatica</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci la modifica delle impostazioni dei certificati</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci la modifica delle impostazioni di connessione</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci la modifica delle impostazioni del server proxy</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non consentire il salvataggio di password in modalità completamento automatico</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Menu Browser\\Disattiva l'opzione Salva l'applicazione su disco
  
Questa impostazione di criterio impedisce agli utenti di salvare un programma o un file scaricato da Internet Explorer sul disco rigido. Se si attiva questa impostazione, gli utenti non possono salvare i programmi sul disco tramite l'opzione **Salva l'applicazione su disco.** Il file di programma non viene scaricato e verrà visualizzato un messaggio in cui viene indicato che il comando non è disponibile. Questa impostazione consente di proteggere gli ambienti ad alta protezione perché gli utenti non possono scaricare programmi potenzialmente dannosi attraverso Internet Explorer e salvarli sul disco.
  
L'impostazione **Menu Browser\\Disattiva l'opzione Salva l'applicazione su disco** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
###### Pannello di controllo Internet\\Disattiva la scheda Avanzate
  
Questa impostazione di criterio opera unitamente ad altri criteri per assicurare che gli utenti non possano cambiare le impostazioni configurate sulla scheda **Avanzate** dell'interfaccia utente di Internet Explorer.
  
L'impostazione **Pannello di controllo Internet\\Disattiva la scheda Avanzate** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
###### Pannello di controllo Internet\\Disattiva la scheda Protezione
  
Questa impostazione di criterio opera unitamente ad altri criteri per assicurare che gli utenti non possano cambiare le impostazioni configurate attraverso i Criteri di gruppo. Questa impostazione rimuove la scheda **Protezione** dalla finestra di dialogo **Opzioni Internet.** Abilitando l'impostazione, non sarà possibile visualizzare né modificare le impostazioni delle aree di protezione relative a script, download e autenticazione utenti. Microsoft consiglia di attivarla per impedire agli utenti di modificare i criteri, il che potrebbe indebolire altre impostazioni di protezione di Internet Explorer.
  
L'impostazione **Pannello di controllo Internet\\Disattiva la scheda Protezione** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
###### Pagine non in linea\\Impedisci l'aggiunta di canali
  
Questa impostazione di criterio impedisce agli utenti di aggiungere canali a Internet Explorer. I canali sono siti Web che vengono aggiornati automaticamente sui computer che eseguono Internet Explorer, in base a una pianificazione specificata dal provider dei canali. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente. È consigliabile consentire di scaricare pagine da Internet solo quando un utente effettua una richiesta direttamente dal computer.
  
Perciò, l'impostazione **Pagine non in linea\\Impedisci l'aggiunta di canali** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Non consentire l'aggiunta di pianificazioni per le pagine non in linea
  
Questa impostazione di criterio non consente agli utenti di scaricare le pagine Web per la visualizzazione in modalità non in linea. Questa funzionalità consente agli utenti di visualizzare le pagine Web senza collegare il computer a Internet.
  
Perciò, l'impostazione **Pagine non in linea\\Non consentire l'aggiunta di pianificazioni per le pagine non in linea** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Disattiva tutte le pagine non in linea pianificate
  
Questa impostazione di criterio disattiva le pianificazioni esistenti configurate per scaricare pagine Web da visualizzare in modalità non in linea. Se si attiva questo criterio, le caselle di controllo relative alle pianificazioni sulla scheda **Pianificazione** della finestra di dialogo **Web page Properties** sono disattivate e non è possibile selezionarle. Per visualizzare la scheda, è sufficiente fare clic sul menu **Strumenti**, quindi scegliere **Sincronizza**, selezionare una pagina Web, scegliere **Proprietà** e infine fare clic sulla scheda **Pianificazione**. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Disattiva tutte le pagine non in linea pianificate** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Disattiva completamente interfaccia utente canali
  
Questa impostazione di criterio impedisce agli utenti di visualizzare l'interfaccia Barra dei canali. I canali sono siti Web che vengono aggiornati automaticamente sui computer in base a una pianificazione specificata dal provider dei canali. Se si attiva questa impostazione di criterio, gli utenti non saranno in grado di accedere all'interfaccia Barra dei canali e selezionare la casella di controllo **Barra dei canali di Internet Explorer** nella scheda **Web** della finestra di dialogo **Proprietà dello schermo**. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Disattiva completamente interfaccia utente canali** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Disattiva il download dei file di dati della sottoscrizione al sito
  
Questa impostazione di criterio consente di impedire il download del contenuto dei siti Web per i quali è stata eseguita la sottoscrizione. Tuttavia, la sincronizzazione con le pagine Web verrà eseguita comunque quando l'utente torna su una pagina visitata in precedenza per determinare se il contenuto è stato aggiornato. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Disattiva il download dei file di dati della sottoscrizione al sito** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Impedisci la modifica e la creazione di gruppi di pianificazioni
  
Questa impostazione di criterio impedisce agli utenti di aggiungere, modificare o rimuovere le pianificazioni per la visualizzazione in modalità non in linea delle pagine Web o dei gruppi di pagine Web per le quali è stata eseguita la sottoscrizione. Un gruppo di sottoscrizioni è costituito da una pagina Web preferita e dalle pagine Web ad essa collegate. Abilitando questo criterio, i pulsanti **Aggiungi**, **Rimuovi** e **Modifica** diventano inattivi nella scheda **Pianificazione** della finestra di dialogo delle **Web page Properties**. Per visualizzare la scheda, è sufficiente fare clic su **Strumenti**, quindi scegliere **Sincronizza** su Internet Explorer, selezionare una pagina Web, scegliere **Proprietà** e infine fare clic sulla scheda **Pianificazione.** Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Impedisci la modifica e la creazione di gruppi di pianificazioni** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Non consentire la modifica delle pianificazioni per le pagine non in linea
  
Questa impostazione di criterio impedisce agli utenti di modificare le pianificazioni esistenti configurate per scaricare pagine Web da visualizzare in modalità non in linea. Se si attiva questo criterio, non sarà possibile visualizzare le proprietà relative alla pianificazione delle pagine impostate per la visualizzazione in modalità non in linea. Facendo clic su **Strumenti**, **Sincronizza** su Internet Explorer, selezionando una pagina Web e facendo clic sul pulsante **Proprietà** non verrà visualizzata alcuna proprietà. Gli utenti non ricevono alcun messaggio che li informa dell'indisponibilità del comando. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Non consentire la modifica delle pianificazioni per le pagine non in linea** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Disattiva la registrazione del numero di accessi alle pagine non in linea
  
Questa impostazione di criterio consente di impedire ai provider dei canali di registrare la frequenza di visualizzazione delle pagine dei canali da parte di utenti connessi in modalità non in linea. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Disattiva la registrazione del numero di accessi alle pagine non in linea** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Impedisci la rimozione di canali
  
Questa impostazione di criterio non consente di disabilitare la sincronizzazione dei canali in Internet Explorer. È consigliabile consentire di scaricare pagine da Internet solo quando un utente effettua una richiesta direttamente dal computer.
  
Perciò, l'impostazione **Pagine non in linea\\Impedisci la rimozione di canali** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Pagine non in linea\\Non consentire la rimozione di pianificazioni per le pagine non in linea
  
Questa impostazione di criterio consente di impedire la deselezione delle impostazioni preconfigurate relative alle pagine Web da scaricare per la visualizzazione in modalità non in linea. Se si attiva questa impostazione di criterio, le impostazioni preconfigurate relative alle pagine Web sono protette. Questa impostazione di criterio è una delle diverse impostazioni che bloccano la capacità di Internet Explorer di scaricare contenuti automaticamente.
  
Perciò, l'impostazione **Pagine non in linea\\Non consentire la rimozione di pianificazioni per le pagine non in linea** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
###### Configura Outlook Express
  
Questa impostazione di criterio consente agli amministratori di abilitare e disabilitare il salvataggio o l'apertura in Microsoft Outlook Express di allegati che potrebbero contenere virus. Gli utenti non possono disattivare l'impostazione **Configura Outlook Express** per impedire il bloccaggio degli allegati. Per applicare questa impostazione di criterio, fare clic su **Attiva** e selezionare **Blocca gli allegati che potrebbero contenere virus.**
  
L'impostazione **Configura Outlook Express** è configurata su **Abilitato** con l'opzione **Blocca gli allegati che potrebbero contenere virus** per i due ambienti trattati in questo capitolo.
  
###### Impedisci la modifica delle impostazioni della scheda Avanzate
  
Questa impostazione di criterio impedisce agli utenti di modificare le impostazioni sulla scheda **Avanzate** nella finestra di dialogo **Opzioni Internet** di Internet Explorer. Se si attiva questa impostazione, non sarà possibile modificare le impostazioni avanzate relative a protezione, multimedia e stampa nel browser. Inoltre, non sarà possibile selezionare o deselezionare le caselle di controllo per queste opzioni sulla scheda **Avanzate** della finestra di dialogo **Opzioni Internet.** Questa impostazione di criterio impedisce inoltre agli utenti di modificare le impostazioni configurate attraverso i Criteri di gruppo.
  
L'impostazione **Impedisci la modifica delle impostazioni della scheda Avanzate** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
**Nota**: se si configura l'impostazione **Disattiva la scheda Avanzate** (che si trova in Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet), non è necessario impostare questo criterio perché **Disattiva la scheda Avanzate** rimuove la scheda **Avanzate** dalla finestra di dialogo **Opzioni Internet.**
  
###### Impedisci la modifica delle impostazioni di Configurazione automatica
  
Questo criterio impedisce agli utenti di modificare le impostazioni configurate automaticamente. Gli amministratori utilizzano la configurazione automatica per aggiornare periodicamente le impostazioni del browser. Se si attiva questo criterio, le impostazioni di configurazione automatica non sono disponibili in Internet Explorer (queste impostazioni si trovano nell'area **Configurazione Automatica** della finestra di dialogo **Impostazioni LAN**). Questo criterio impedisce inoltre di modificare le impostazioni configurate attraverso i Criteri di gruppo.
  
**Per visualizzare la finestra di dialogo Impostazioni LAN**
  
1.  Aprire la finestra di dialogo **Opzioni Internet**, quindi fare clic sulla scheda **Connessioni**.
  
2.  Scegliere **Impostazioni LAN** per visualizzare le impostazioni.
  
L'impostazione **Impedisci la modifica delle impostazioni di Configurazione automatica** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
**Nota**: l'impostazione **Disattiva la scheda Connessioni** (che si trova in \\Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet) rimuove la scheda **Connessioni** dal Pannello di controllo di Internet Explorer e assume la precedenza rispetto a **Impedisci la modifica delle impostazioni di Configurazione automatica**. Se la prima impostazione è attivata, la seconda viene ignorata.
  
###### Impedisci la modifica delle impostazioni dei certificati
  
Questa impostazione di criterio non consente di disabilitare le impostazioni dei certificati in Internet Explorer. I certificati vengono utilizzati per verificare l'identità di autori o distributori di software. Se si attiva questo criterio, le impostazioni dei certificati nell'area **Certificati** della scheda **Contenuto** nella finestra di dialogo **Opzioni Internet** non sono disponibili. Questa impostazione di criterio impedisce inoltre agli utenti di modificare le impostazioni configurate attraverso i Criteri di gruppo.
  
L'impostazione **Impedisci la modifica delle impostazioni dei certificati** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
**Nota**: abilitando questo criterio, gli utenti possono comunque fare doppio clic sul file .spc (Software Publishing Certificate) per eseguire l'Importazione guidata gestione certificati. Questa procedura guidata consente di importare e configurare le impostazioni dei certificati di autori o distributori di software non ancora configurati per Internet Explorer.
  
**Nota**: l'impostazione **Disattiva la scheda Contenuto** (che si trova in \\Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet) rimuove la scheda **Contenuto** dal Pannello di controllo di Internet Explorer e assume la precedenza rispetto a **Impedisci la modifica delle impostazioni dei certificati**. Se la prima impostazione è attivata, la seconda viene ignorata.
  
###### Impedisci la modifica delle impostazioni di connessione
  
Questo criterio impedisce agli utenti di modificare le impostazioni di connessione. Se si abilita questa impostazione di criterio, il pulsante **Impostazioni** sulla scheda **Connessioni** nella finestra di dialogo **Opzioni Internet** è inattivo. Questa impostazione di criterio impedisce inoltre agli utenti di modificare le impostazioni configurate attraverso i Criteri di gruppo. È possibile disattivare questo criterio per gli utenti di computer portatili se i loro spostamenti richiedono di modificare le impostazioni di connessione.
  
L'impostazione **Impedisci la modifica delle impostazioni di connessione** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
**Nota**: se si configura l'impostazione **Disattiva la scheda connessioni** (in Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet), non è necessario configurare questa impostazione di criterio. L'impostazione **Disattiva la scheda connessioni** rimuove la scheda **Connessioni** dall'interfaccia.
  
###### Impedisci la modifica delle impostazioni del server proxy
  
Questo criterio impedisce agli utenti di modificare le impostazioni proxy. Se questo criterio è abilitato, le impostazioni proxy sono inattive (le impostazioni proxy si trovano nell'area **Server proxy** della finestra di dialogo **Impostazioni LAN** che viene visualizzata facendo clic sulla scheda **Connessioni** e quindi sul pulsante **Impostazioni LAN** nella finestra di dialogo **Opzioni Internet)**. Questa impostazione di criterio impedisce inoltre agli utenti di modificare le impostazioni configurate attraverso i Criteri di gruppo. È possibile disattivare questo criterio per gli utenti di computer portatili se i loro spostamenti richiedono di modificare le impostazioni di connessione.
  
L'impostazione **Impedisci la modifica delle impostazioni del server proxy** è configurata su **Abilitato** soltanto per l'ambiente SSLF. Questa impostazione di criterio non è configurata per l'ambiente EC.
  
**Nota**: se si configura l'impostazione **Disattiva la scheda connessioni** (in Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet), non è necessario configurare questa impostazione di criterio. L'impostazione **Disattiva la scheda connessioni** rimuove la scheda **Connessioni** dall'interfaccia.
  
###### Non consentire il salvataggio di password in modalità completamento automatico
  
Questa impostazione di criterio consente di disattivare il completamento automatico del nome utente e della password sui moduli delle pagine Web evitando la visualizzazione dei prompt che richiedono il salvataggio della password. Se si abilita questa impostazione di criterio, le caselle di controllo **Nome utente e password sui moduli** e **Richiedi salvataggio password** diventeranno inattive e gli utenti non potranno salvare le password in locale. Per visualizzare le caselle di controllo, è sufficiente aprire la finestra di dialogo **Opzioni Internet**, fare clic sulla scheda **Contenuto** e infine scegliere **Completamento automatico**.
  
L'impostazione **Non consentire il salvataggio di password in modalità completamento automatico** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
##### Gestione allegati
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione utente\\Modelli amministrativi\\Componenti di Windows**\\  
**Gestione allegati**
  
La seguente tabella riassume le impostazioni di configurazione utente consigliate per Gestione allegati. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.28 Impostazioni di Configurazione utente consigliate per Gestione allegati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Computer EC</th>
<th style="border:1px solid black;" >Computer SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non conservare le informazioni di area nei file allegati</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nascondi meccanismi di rimozione informazioni sull'area</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Notifica programmi antivirus quando vengono aperti allegati</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Non conservare le informazioni di area nei file allegati
  
Questa impostazione di criterio consente di configurare Windows in modo da contrassegnare i file allegati di Internet Explorer o Outlook Express con informazioni relative all'area di origine (come limitato, Internet, Intranet o locale). Questa impostazione richiede che i file siano scaricati sulle partizioni del disco NTFS per funzionare correttamente. Se le informazioni di area non sono conservate, Windows non può valutare correttamente il rischio in base alla zona da cui proviene l'allegato.
  
Se l'impostazione **Non conservare le informazioni di area nei file allegati** è attivata, i file allegati non vengono contrassegnati con le informazioni relative all'area di origine. Se questa impostazione di criterio è disattivata, Windows memorizza i file allegati con le informazioni relative all'area di origine. Poiché gli allegati pericolosi vengono spesso scaricati da aree di Internet Explorer non attendibili come l'area Internet, Microsoft consiglia di configurare questa impostazione su **Disabilitato** per assicurare che i file conservino il più possibile informazioni relative alla protezione.
  
L'impostazione **Non conservare le informazioni di area nei file allegati** è configurata su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo.
  
###### Nascondi meccanismi di rimozione informazioni sull'area
  
Questa impostazione di criterio consente di scegliere se gli utenti possono rimuovere manualmente le informazioni sull'area dai file allegati salvati. Di norma, è possibile fare clic sul pulsante **Annulla blocco** nella finestra **Proprietà** del file o selezionare la casella di controllo nella finestra di dialogo **Avviso di protezione**. Se si rimuovono le informazioni sull'area, gli utenti possono aprire file allegati potenzialmente pericolosi che Windows impedisce di aprire.
  
Quando l'impostazione **Nascondi meccanismi di rimozione informazioni sull'area** è attivata, Windows nasconde la casella di controllo e il pulsante **Annulla blocco**. Quando l'impostazione è disattivata, Windows visualizza la casella di controllo e il pulsante **Annulla blocco**. Poiché gli allegati pericolosi vengono spesso scaricati da aree di Internet Explorer non attendibili come l'area Internet, Microsoft consiglia di configurare questa impostazione su **Abilitato** per assicurare che i file conservino il più possibile informazioni relative alla protezione.
  
L'impostazione **Nascondi meccanismi di rimozione informazioni sull'area** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: per configurare il salvataggio dei file con le informazioni sull'area, vedere la precedente impostazione **Non conservare le informazioni di area nei file allegati.**
  
###### Notifica programmi antivirus quando vengono aperti allegati
  
I programmi antivirus sono obbligatori nella maggior parte degli ambienti e sono una solida linea di difesa contro gli attacchi.
  
L'impostazione **Notifica programmi antivirus quando vengono aperti allegati** consente di gestire le notifiche relative ai programmi antivirus registrati. Se attivata, questa impostazione di criterio configura Windows in modo da chiedere al programma antivirus registrato di eseguire una scansione dei file allegati quando vengono aperti dagli utenti. Se la scansione antivirus non è completata con successo, l'apertura degli allegati non è consentita. Se questa impostazione di criterio è disattivata, Windows non richiama il programma antivirus registrato quando i file allegati vengono aperti. Per assicurarsi che i programmi antivirus esaminino ogni file prima che venga aperto, Microsoft consiglia di configurare questo criterio su **Abilitato** in tutti gli ambienti.
  
L'impostazione **Notifica programmi antivirus quando vengono aperti allegati** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: perché questa impostazione funzioni correttamente, è necessario installare un programma antivirus aggiornato. Molti programmi antivirus aggiornati utilizzano API nuove incluse con SP2.
  
##### Esplora risorse
  
Esplora risorse è utilizzato per consultare il file system sui computer client dotati di Windows XP Professional.
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione utente\\Modelli amministrativi\\Componenti di Windows**\\  
**Esplora risorse**
  
La seguente tabella riassume le impostazioni di configurazione utente consigliate per Esplora risorse. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.29 Impostazioni di Configurazione utente consigliate per Esplora risorse**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Computer EC</th>
<th style="border:1px solid black;" >Computer SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Rimuovi le funzionalità di creazione dei CD</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Rimuovi la scheda Protezione</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
###### Rimuovi le funzionalità di creazione dei CD
  
Questa impostazione di criterio consente di rimuovere le funzionalità integrate di Windows XP che consentono agli utenti di masterizzare CD attraverso Esplora risorse. Windows XP consente di creare e modificare CD riscrivibili se si dispone di un'unità CD di lettura/scrittura collegata al computer. È possibile utilizzare questa funzionalità per copiare grandi quantità di dati da un disco rigido su un CD, che può essere poi estratto dal computer.
  
L'impostazione **Rimuovi le funzionalità di creazione dei CD** è configurata su **Non configurato** per l'ambiente EC. Tuttavia, questa impostazione di criterio è **Attivata** per l'ambiente SSLF.
  
**Nota**: questa impostazione non impedisce agli utenti di utilizzare applicazioni di altri produttori per creare o modificare i CD mediante un masterizzatore. Questa guida consiglia di utilizzare i criteri di restrizione software per impedire la creazione o la modifica di CD attraverso applicazioni di altri produttori. Per ulteriori informazioni, vedere il Capitolo 6, "Criteri di restrizione software per i client Windows XP".
  
Un altro modo per evitare che gli utenti masterizzino CD consiste nel rimuovere i masterizzatori dai computer client dell'ambiente o di sostituirli con unità CD di sola lettura.
  
###### Rimuovi la scheda Protezione
  
Questa impostazione di criterio disattiva la scheda **Protezione** nelle finestre di dialogo delle proprietà dei file e delle cartelle in Esplora risorse. Se si attiva questa impostazione di criterio, gli utenti non possono accedere alla scheda **Protezione** dopo aver aperto la finestra di dialogo **Proprietà** per tutti gli oggetti del file system, come le cartelle, i file, i collegamenti e le unità. Non potendo accedere alla scheda **Protezione**, non è possibile modificare le impostazioni o visualizzare l'elenco degli utenti.
  
Per tali ragioni, l'impostazione **Rimuovi la scheda Protezione** è **Non** **configurato** per l'ambiente EC. Tuttavia, questa impostazione di criterio è **Attivata** per l'ambiente SSLF.
  
#### System
  
La figura seguente illustra le sezioni dei Criteri di gruppo che saranno interessate dalle modifiche alle impostazioni nella sezione Sistema:
  
[![](images/Cc163076.SGFG0407(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163076.sgfg0407_big(it-it,technet.10).gif)
  
**Figure 4.7 Struttura dei Criteri di gruppo per la Configurazione utente, Sistema**
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione utente\\Modelli amministrativi\\Sistema**
  
##### Impedisci accesso agli strumenti di modifica del Registro di sistema
  
La seguente tabella riassume le impostazioni di configurazione utente consigliate per l'Editor del Registro di sistema.
  
**Tabella 4.30 Impostazioni di configurazione utente consigliate per l'Editor del Registro di sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Computer EC</th>
<th style="border:1px solid black;" >Computer SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Impedisci accesso agli strumenti di modifica del Registro di sistema</td>
<td style="border:1px solid black;">Non configurato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
Questa impostazione di criterio disattiva gli Editor del Registro di sistema di Windows, Regedt32.exe e Regedit.exe. Se questa impostazione è attivata e un utente tenta di utilizzare un Editor del Registro di sistema, verrà visualizzato un messaggio che informa dell'impossibilità di eseguire questa operazione. Questa impostazione di criterio impedisce agli utenti e agli intrusi di accedere al Registro di sistema tramite questi strumenti, ma non impedisce l'accesso al Registro stesso.
  
L'impostazione **Impedisci accesso agli strumenti di modifica del Registro di sistema** è **Non configurato** per l'ambiente EC. Tuttavia, questa impostazione di criterio è **Attivata** per l'ambiente SSLF.
  
##### Sistema\\Gestione dell’alimentazione
  
È possibile configurare le seguenti impostazioni previste nella seguente posizione utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione utente\\Modelli amministrativi\\Sistema\\Gestione dell’alimentazione**
  
###### Richiedi la password al termine dalla modalità di sospensione
  
La tabella seguente riassume le impostazioni **Richiedi la password al termine dalla modalità di sospensione** consigliate.
  
**Tabella 4.31 Impostazioni di configurazione utente Sistema\\Gestione dell’alimentazione consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Computer EC</th>
<th style="border:1px solid black;" >Computer SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Richiedi la password al termine dalla modalità di sospensione</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
Questa impostazione consente di configurare i computer client dell'ambiente in modo che restino bloccati alla ripresa dallo stato di sospensione. Se questa impostazione viene attivata, i computer client si bloccano alla ripresa dallo stato di sospensione e gli utenti devono inserire la password per sbloccarli. Se questa impostazione di criterio è disattivata o non è configurata, potrebbero verificarsi gravi violazioni della protezione, perché chiunque potrebbe accedere ai computer client.
  
Per tale ragione, l'impostazione **Richiedi la password al termine dalla modalità di sospensione** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo ha descritto molte delle più importanti impostazioni di protezione disponibili nei Modelli amministrativi forniti con Windows XP. È possibile utilizzare questi modelli per proteggere i computer desktop e portatili dell'organizzazione dotati di Windows XP. Al momento di valutare i criteri di protezione per un'organizzazione, è consigliabile bilanciare le azioni di protezione con la produttività degli utenti. Lo scopo è proteggere gli utenti da programmi dannosi e virus attraverso una struttura informatica sicura che consenta di eseguire i propri compiti senza i disagi causati da impostazioni di protezione eccessivamente restrittive.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni su argomenti relativi alla protezione di Windows XP Professional.
  
-   Per un elenco completo delle impostazioni relative ai criteri di gruppo dei Modelli amministrativi disponibili in Windows XP e Windows Server 2003, scaricare la cartella di lavoro "[Group Policy Settings Reference for Windows Server 2003 with Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=7821c32f-da15-438d-8e48-45915cd2bc14&displaylang=en)" (in inglese) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyId=  
    7821C32F-DA15-438D-8E48-45915CD2BC14.
  
-   Per informazioni sulla creazione di Modelli amministrativi personalizzati, vedere il white paper "[Implementing Registry-Based Group Policy](http://technet.microsoft.com/en-us/library/bb742499.aspx)" (in inglese) all'indirizzo  
    www.microsoft.com/windows2000/techinfo/howitworks/management/rbppaper.asp.
  
-   Per informazioni sulla Segnalazione errori, vedere il sito Web di Windows [Corporate Error Reporting](http://technet.microsoft.com/en-us/library/cc775885.aspx) (in inglese) all'indirizzo www.microsoft.com/resources/satech/cer/.
  
-   Per informazioni generali su Windows Server Update Service (WSUS), vedere [Windows Server Update Services Product Overview](http://www.microsoft.com/windowsserversystem/updateservices/evaluation/overview.mspx) (in inglese) all'indirizzo  
    www.microsoft.com/windowsserversystem/updateservices/evaluation/overview.mspx.
  
-   Per informazioni sulla distribuzione di WSUS, vedere [Deploying Microsoft Windows Server Update Services](http://technet.microsoft.com/en-us/library/cc720507.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/WSUS/WSUSDeploymentGuideTC/.
  
-   Per ulteriori informazioni sulla gestione dei Criteri di gruppo, vedere "[Enterprise Management with the Group Policy Management Console](http://www.microsoft.com/windowsserver2003/gpmc/default.mspx)" (in inglese) all'indirizzo www.microsoft.com/windowsserver2003/gpmc/.
  
-   Il sito principale sulla protezione di Office 2003 ([Security](http://office.microsoft.com/en-us/assistance/ha011403061033.aspx), in inglese) dispone di collegamenti ad articoli che spiegano l'utilizzo delle impostazioni di protezione e delle funzionalità di Office 2003 ed è disponibile all'indirizzo  
    http://office.microsoft.com/en-us/assistance/HA011403061033.aspx.
  
-   La pagina "[Office 2003 Policy Template Files and Deployment Planning Tools](http://office.microsoft.com/en-us/ork2003/ha011513711033.aspx)" (in inglese) include i file relativi ai Modelli amministrativi dei Criteri di gruppo di Office e fogli di lavoro che riassumono tutte le impostazioni disponibili. Questi strumenti sono disponibili all'indirizzo  
    http://download.microsoft.com/download/9/5/f/95f7e000-d7ab-4b86-8a5d-804b124c7a69/Office-2003-SP1-ADMs-OPAs-and-Explain-Text.exe.
  
-   La pagina "[Office 2003 Resource Kit toolset](http://download.microsoft.com/download/0/e/d/0eda9ae6-f5c9-44be-98c7-ccc3016a296a/ork.exe)" (in inglese) include "Office 2003 Policy Template Files and Deployment Planning Tools" e altri utili strumenti per distribuire e gestire Office 2003; è disponibile all'indirizzo http://download.microsoft.com/download/0/e/  
    d/0eda9ae6-f5c9-44be-98c7-ccc3016a296a/ork.exe.
  
-   Per ulteriori informazioni su [*Internet Explorer Administration Kit*](http://www.microsoft.com/technet/prodtechnol/ie/ieak/), vedere www.microsoft.com/technet/prodtechnol/ie/ieak/.
  
##### Download
  
[![](images/Cc163076.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
