---
TOCTitle: 'Capitolo 3: Impostazioni di protezione per i client Windows XP'
Title: 'Capitolo 3: Impostazioni di protezione per i client Windows XP'
ms:assetid: 'bca34b8d-a1ca-42e4-b743-aa3ca12fd8f9'
ms:contentKeyID: 20213255
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163074(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Capitolo 3: Impostazioni di protezione per i client Windows XP

##### In questa pagina

[](#enaa)[Panoramica](#enaa)
[](#emaa)[Impostazioni dei criteri di account](#emaa)
[](#elaa)[Impostazioni dei criteri locali](#elaa)
[](#ekaa)[Impostazioni del Criterio Controllo](#ekaa)
[](#ejaa)[Impostazioni di Assegnazione diritti utente](#ejaa)
[](#eiaa)[Impostazioni di Opzioni di protezione](#eiaa)
[](#ehaa)[Impostazioni di protezione di Registro eventi](#ehaa)
[](#egaa)[Gruppi con restrizioni](#egaa)
[](#efaa)[Servizi di sistema](#efaa)
[](#eeaa)[Altre impostazioni del Registro di sistema](#eeaa)
[](#edaa)[Modifica dell'interfaccia utente dell'Editor di configurazione della protezione](#edaa)
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)
[](#ebaa)[Protezione del File System](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo descrive in dettaglio le impostazioni di protezione primarie che sono configurate attraverso i Criteri di gruppo in un dominio di servizio directory Microsoft Windows 2000 o Windows Serve 2003 Active Directory. Implementare le impostazioni di criterio prescritte per assicurare che i computer desktop e i computer portatili dell'organizzazione che utilizzano Microsoft Windows XP Professional con Service Pack 2 (SP2) siano configurati in modo sicuro. La guida non descrive tutte le impostazioni di criterio disponibili in Windows  XP, ma solo quelle direttamente pertinenti per la protezione del computer.

Come descritto nel Capitolo 1, "Introduzione alla Guida per la protezione di Windows XP," la guida che è presentata in questo capitolo è specifica per gli ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality) che sono definiti in questa guida. In alcuni casi, questo capitolo suggerisce impostazioni di criterio per i computer portatili diverse da quelle per i desktop, perché i computer portatili sono mobili e non sempre connessi ai controller di dominio nell'ambiente attraverso la rete dell'organizzazione. Si presuppone inoltre che gli utenti di computer portatili lavorino a volte a ore in cui il supporto tecnico non è disponibile. Di conseguenza, le impostazioni dei criteri che richiedono la connettività a un controller di dominio o che regolamentano le ore di accesso sono diverse per i computer client portatili.

Le impostazioni di criterio non specificate per ambienti specifici sono definite a volte a livello di dominio, come descritto nel Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory". Le altre impostazioni di criterio elencate in questo capitolo come **Non definite** sono gestite in questo modo perché il valore predefinito è sufficientemente sicuro per tale ambiente specifico. Inoltre, le impostazioni di criterio non definite in questi GPO (Group Policy objects) semplificano la distribuzione di applicazioni che devono modificare le impostazioni durante l'installazione. Per esempio, gli strumenti di gestione aziendale possono dover assegnare diritti utente specifici agli account di servizio locale sui computer gestiti. Questo capitolo contiene suggerimenti, ed è sempre necessario valutare attentamente le proprie esigenze commerciali prima di modificare l'ambiente in qualsiasi modo.

Nella seguente tabella sono riportati i file infrastruttura (.inf) disponibili con questa guida. I file contengono tutte le indicazioni di impostazione della protezione di base per i due ambienti definiti in questo capitolo.

**Tabella 3.1 Modelli di protezione di base**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>EC</th>
<th>SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Modelli di protezione di base per i desktop</td>
<td style="border:1px solid black;">EC-Desktop.inf</td>
<td style="border:1px solid black;">SSLF-Desktop.inf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modelli di protezione di base per i portatili</td>
<td style="border:1px solid black;">EC-Laptop.inf</td>
<td style="border:1px solid black;">SSLF-Laptop.inf</td>
</tr>
</tbody>
</table>
  
Per informazioni più dettagliate sulle impostazioni di criterio descritte in questo capitolo, vedere la guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), scaricabile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni dei criteri di account
  
Questo capitolo non fornisce informazioni sulle impostazioni dei criteri degli account. Queste impostazioni sono descritte nel Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory," della presente guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni dei criteri locali
  
Le impostazioni dei criteri locali possono essere configurate su qualunque computer con Windows XP Professional attraverso la console dei Criteri di protezione locali o attraverso i GPO basati su dominio Active Directory. Le impostazioni dei criteri locali includono Criteri di controllo, Assegnazione diritti utente e Opzioni di protezione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Un criterio di controllo stabilisce gli eventi relativi alla protezione da riferire agli amministratori, per permettere di registrare l'attività utente o di sistema nelle categorie evento specificate. L'amministratore può controllare l'attività legata alla protezione, ad esempio chi accede a un oggetto, quando un utente effettua l'accesso o si disconnette da un computer, o se vengono apportate modifiche a un'impostazione di Criteri di controllo. Per tutti questi motivi, è consigliabile creare un criterio di controllo per un amministratore da implementare nel proprio ambiente.
  
Tuttavia, prima di implementare un criterio di Controllo, è necessario decidere quali categorie evento hanno bisogno di essere verificate nell'ambiente. Dalle impostazioni di controllo scelte all'interno delle categorie di eventi dipende il criterio di controllo aziendale. Quando si definiscono le impostazioni di controllo per categorie evento specifiche, un amministratore può creare un criterio di controllo che soddisferà le esigenze di sicurezza dell'organizzazione.
  
Se non vengono configurate impostazioni di controllo, sarà difficile o impossibile stabilire cosa è accaduto in caso di un problema di protezione. Tuttavia, se il controllo è configurato in modo che vengano generati eventi da troppe attività autorizzate, il registro degli eventi di protezione si riempirà di dati inutili. Le informazioni nelle sezioni seguenti sono strutturate per consentire di decidere cosa controllare e come raccogliere dati di controllo pertinenti per l'organizzazione.
  
Le impostazioni Criteri di controllo possono essere configurate in Windows XP nel seguente percorso utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Criteri di controllo**
  
La seguente tabella riassume i suggerimenti per le impostazioni del criterio di controllo per i computer client desktop e per i computer portatili relativamente ai due tipi di ambienti sicuri trattati nel presente capitolo. L'ambiente Enterprise Client è denominato EC, e l'ambiente Specialized Security – Limited Functionality è denominato SSLF. È necessario esaminare queste raccomandazioni e modificarle in base alle esigenze dell'organizzazione. Tuttavia, prestare particolare attenzione alle impostazioni di controllo che possono generare un grande volume di traffico. Per esempio, se si attiva il controllo sia degli eventi riusciti sia di quelli non riusciti per **Controlla uso dei privilegi**, saranno generati così tanti eventi di controllo che potrebbe non essere possibile trovare altri tipi di voci nel registro eventi di Protezione. Tale configurazione potrebbe avere anche un impatto significativo sulle prestazioni. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
**Tabella 3.2 Raccomandazioni per le impostazioni dei criteri di controllo**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controlla eventi accesso account</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla gestione degli account</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla accesso al servizio directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla eventi di accesso</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
<td style="border:1px solid black;">Operazione riuscita, Operazione non riuscita</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla accesso agli oggetti</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Operazione non riuscita</td>
<td style="border:1px solid black;">Operazione non riuscita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modifica del criterio di controllo</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla uso dei privilegi</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Operazione non riuscita</td>
<td style="border:1px solid black;">Operazione non riuscita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla tracciato processo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla eventi di sistema</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
</tr>
</tbody>
</table>
  
#### Controlla eventi accesso account
  
Se questa impostazione di criterio è attivata, sono generati gli eventi per la convalida delle credenziali. Questi eventi si verificano sul computer che possiede l'autorità per le credenziali. Per gli account di dominio il punto di riferimento principale è costituito dal controller di dominio, mentre per gli account locali è costituito dal computer locale. Negli ambienti di dominio, la maggior parte degli eventi di accesso account si verificano nel Registro di protezione dei controller di dominio più autorevole per gli account di dominio. Tuttavia, questi eventi possono verificarsi sugli altri computer dell'organizzazione, in base agli account utilizzati per effettuare l'accesso.
  
In questa guida, l'impostazione **Controlla eventi accesso account** è configurata su **Operazione riuscita** soltanto per l'ambiente di EC e su **Operazione riuscita** e **Operazione non riuscita** per l'ambiente SSLF.
  
#### Controlla gestione degli account
  
Questa impostazione di criterio è utilizzata per tenere traccia dei tentativi di creare nuovi utenti o gruppi, rinominare utenti o gruppi, attivare o disattivare account utente, modificare le password degli account e attivare il controllo degli eventi di gestione degli account. Se si attiva questa impostazione del criterio di controllo, gli amministratori possono monitorare gli eventi e rilevare la creazione malevola, accidentale e autorizzata di account utente e gruppi.
  
L'impostazione **Controlla gestione degli account** è configurata su **Operazione riuscita** per l'ambiente EC e su **Operazione riuscita** e **Operazioni non riuscita** per l'ambiente SSLF.
  
#### Controlla accesso al servizio directory
  
Questa impostazione di criterio può essere attivata soltanto per eseguire operazioni di controllo sui controller di dominio. Per questo motivo, non è definita a livello di workstation. Questa impostazione di criterio non concerne i computer con Windows XP Professional. Verificare quindi che l'impostazione **Controlla accesso al servizio directory** sia configurata su **Non definito** per i due ambienti trattati in questo capitolo.
  
#### Controlla eventi di accesso
  
Questa impostazione di criterio genera eventi che registrano la creazione e la distruzione di sessioni di accesso. Questi eventi si verificano sul computer al cui si accede. Per gli accessi interattivi, questi eventi sono generati sul computer a cui è stato effettuato l'accesso. Se è stato effettuato un accesso alla rete per accedere a una condivisione, questi eventi sono generati sul computer che ospita la risorsa a cui è stato effettuato l'accesso.
  
Se si configura l'impostazione **Controlla eventi di accesso** su **Nessun controllo**, è difficile o impossibile determinare quale utente ha effettuato o tentato di effettuare l'accesso ai computer dell'organizzazione.
  
L'impostazione **Controlla eventi di accesso** è configurata per registrare gli eventi **Operazione riuscita** per l'ambiente di EC. Questa impostazione di criterio è configurata per l'ambiente SSLF su **Operazione riuscita** e **Operazione non riuscita**.
  
#### Controlla accesso agli oggetti
  
Di per sé questa impostazione non comporta il controllo di alcun evento. Essa determina se controllare l'evento di un utente che accede a un oggetto, per esempio, un file, una cartella, una chiave del registro di sistema o una stampante, per cui è stato specificato un SACL (System Access Control List).
  
In un SACL sono presenti le voci di controllo degli accessi (ACE, Access Control Entry). Ciascun ACE contiene tre informazioni:
  
-   L’identità di protezione (utente, computer o gruppo) da controllare.
  
-   Il tipo di accesso da controllare, ovvero la maschera di accesso.
  
-   Un contrassegno che indica se devono essere controllati gli eventi relativi agli accessi non riusciti, gli eventi relativi agli accessi riusciti o entrambi.
  
Se si configura l'impostazione **Controlla accesso agli oggetti** su **Operazione riuscita**, ogni volta che un utente riesce ad accedere a un oggetto per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento riuscito. Se si configura l'impostazione su **Operazione non riuscita**, ogni volta che un utente non riesce ad accedere a un oggetto per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento non riuscito.
  
Quando si configurano gli elenchi di controllo di accesso di sistema, è importante definire solo le azioni che devono essere abilitate. Ad esempio, potrebbe essere utile abilitare l'impostazione **Write and Append Data auditing** per tenere traccia delle sostituzioni o modifiche apportate ai file eseguibili, che sono di norma il bersaglio di virus, worm e cavalli di Troia. Analogamente, può essere utile tenere traccia degli accessi e delle modifiche apportate a documenti riservati.
  
L'impostazione **Controlla accesso agli oggetti** è configurata su **Nessun controllo** per l'ambiente EC e su **Operazioni non riuscite** per l'ambiente SSLF. È necessario attivare questa impostazione perché le seguenti procedure abbiano effetto.
  
Nelle procedure seguenti viene spiegato dettagliatamente come impostare manualmente le regole di controllo su un file o una cartella e come verificarle singolarmente per ciascun oggetto presente nella cartella o nel file specificato. La procedura di testing può essere automatizzata per mezzo di un file di script.
  
**Per definire una regola di controllo per un file o la cartella**
  
1.  Tramite Esplora risorse, individuare e selezionare il file o la cartella.
  
2.  Selezionare **Proprietà** dal menu **File**.
  
3.  Selezionare la scheda **Protezione**, quindi fare clic sul pulsante **Avanzate**.
  
4.  Selezionare la scheda **Controllo**.
  
5.  Fare clic sul pulsante **Aggiungi**, verrà visualizzata la finestra di dialogo **Seleziona utente, computer o gruppo**.
  
6.  Fare clic sul pulsante **Tipi di oggetto…** , quindi nella finestra di dialogo **Tipi di oggetto** selezionare i tipi di oggetto che si desidera trovare.
  
    **Nota:** i tipi di oggetto Utente, Gruppo e Identità di protezione incorporata sono selezionati per impostazione predefinita.
  
7.  Fare clic sul pulsante **Percorsi...** e scegliere il dominio o il computer locale nella finestra di dialogo **Percorso:**.
  
8.  Nella finestra di dialogo **Seleziona utente o gruppo**, digitare il nome del gruppo o dell'utente che si desidera controllare. Quindi, nella finestra di dialogo **Immettere i nomi degli oggetti da selezionare**, digitare **Authenticated Users** per controllare l'accesso di tutti gli utenti autenticati e scegliere **OK**. Viene visualizzata la finestra di dialogo **Voci di controllo**.
  
9.  Stabilire il tipo di accesso da controllare sul file o sulla cartella tramite la finestra di dialogo **Voci di controllo**.
  
    **Nota**: tenere presente che ciascun accesso può generare più eventi nel registro eventi, le cui dimensioni potrebbero di conseguenza crescere rapidamente.
  
10. Nella finestra di dialogo **Voci di controllo**, accanto a **Visualizzazione contenuto cartella / Lettura dati**, selezionare **Operazioni riuscite e Operazioni non riuscite**, quindi scegliere **OK**.
  
11. Le voci di controllo attivate verranno visualizzate nella scheda **Controllo** della finestra di dialogo **Impostazioni di protezione avanzate**.
  
12. Scegliere **OK** per chiudere la finestra di dialogo **Proprietà.**
  
**Per verificare una regola di controllo per il file o la cartella**
  
1.  Aprire il file o la cartella.
  
2.  Chiudere il file o la cartella.
  
3.  Avviare il Visualizzatore eventi. Diversi eventi Accesso agli oggetti con **ID evento 560** verranno visualizzati nel registro eventi di protezione.
  
4.  Fare doppio clic sugli eventi desiderati per visualizzare i relativi dettagli.
  
#### Modifica del criterio di controllo
  
Questa impostazione di criterio determina se controllare tutti gli eventi di modifica dei criteri di assegnazione dei diritti utente, dei criteri Windows Firewall, dei criteri di affidabilità o le modifiche ai criteri di controllo stessi. L’impostazione consigliata consente di vedere tutti i privilegi dell’account che un pirata informatico sta cercando di elevare, ad esempio aggiungendo il privilegio **Debug di programmi** o il privilegio **Backup di file e directory**.
  
L'impostazione **Modifica del criterio di controllo** è configurata su **Operazione riuscita** per i due ambienti trattati in questo capitolo. Il valore di impostazione per **Operazione non riuscita** non figura perché non fornisce significative informazioni di accesso al registro eventi di protezione.
  
#### Controlla uso dei privilegi
  
Consente di controllare tutte le istanze di esercizio di un diritto utente da parte di un utente. Se si configura questo valore su **Operazione riuscita**, viene generata una voce ogni volta che viene esercitato un diritto utente. Se si configura questo valore su **Operazione non riuscita**, viene generata una voce ogni volta che un utente non riesce a esercitare un diritto utente. Questa impostazione di criterio può generare un numero molto elevato di record di eventi.
  
L'impostazione **Controlla uso dei privilegi** è configurata su **Nessun controllo** per i computer nell'ambiente EC e su **Operazione non riuscita** per l'ambiente SSLF, in modo da controllare tutti i tentativi non riusciti di utilizzare i privilegi.
  
#### Controlla tracciato processo
  
Consente di controllare i tracciati di eventi quali l’attivazione di programmi, l’uscita da processi, la duplicazione di handle e l’accesso indiretto agli oggetti. Se si attiva l’impostazione **Controlla tracciato processo**, viene generato un numero elevato di eventi, quindi di norma si specifica **Nessun controllo**. Queste impostazioni, tuttavia, possono essere molto utili in caso di incidenti, in quanto è possibile ottenere informazioni dettagliate sui processi che sono stati avviati e sull’orario di avvio.
  
L'impostazione **Controlla tracciato processo** è configurata su **Nessun controllo** per i due ambienti trattati in questo capitolo.
  
#### Controlla eventi di sistema
  
Questa impostazione è molto importante perché consente di controllare gli eventi di sistema riusciti e non e ne fornisce un record che può aiutare a stabilire le istanze di accesso di sistema non autorizzato. Gli eventi di sistema includono l'avvio o l'arresto dei computer dell'ambiente, registri eventi completi o altri eventi relativi alla protezione che hanno ripercussioni sull'intero sistema.
  
L'impostazione **Controlla eventi di sistema** è configurata su **Operazione riuscita** per i due ambienti trattati in questo capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Assegnazione diritti utente
  
In concomitanza con molti dei gruppi con privilegi in Windows XP Professional, è possibile assegnare a determinati utenti o gruppi un certo numero di diritti utente di cui gli utenti normali non godono.
  
Per impostare il valore di un diritto utente su **Nessuno**, attivare l'impostazione senza però aggiungere alcun gruppo o utente. Per impostare il valore di un diritto utente su **Non definito**, non attivare l'impostazione.
  
È possibile configurare le impostazioni per l'assegnazione dei diritti utente nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Assegnazioni diritti utenti**
  
La tabella seguente riassume le raccomandazioni relative alle impostazioni di assegnazione dei diritti utente che iniziano con le lettere dalla A alla E. Le raccomandazioni si riferiscono sia ai computer client desktop sia ai portatili, nei due tipi di ambienti protetti trattati in questo capitolo. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
Le raccomandazioni relative ai diritti utente che iniziano con le lettere restanti dell'alfabeto sono riassunte nella Tabella 3.4 e ulteriori informazioni dettagliate su di essi sono presenti nelle sottosezioni che seguono la tabella.
  
**Note**: molte funzionalità di Internet Information Server (IIS) richiedono che certi account, come IIS\_WPG, IIS IUSR\_*&lt;nomecomputer&gt;*, e* *IWAM\_*&lt;nomecomputer&gt;* dispongano di specifici privilegi. Per ulteriori informazioni sui tipi di diritti utente richiesti dagli account relativi a IIS, vedere "[IIS and Built-In Accounts (IIS 6.0)](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/iis/3648346f-e4f5-474b-86c7-5a86e85fa1ff.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/  
IIS/3648346f-e4f5-474b-86c7-5a86e85fa1ff.mspx.
  
#### Diritti utente A – E
  
**Tabella 3.3 Raccomandazioni relative alle impostazioni di assegnazione dei diritti utente – Parte 1**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso al computer dalla rete</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Agisci come parte del sistema operativo</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Regolazione quote di memoria per un processo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators, Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Administrators, Servizio locale, Servizio di rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti accesso locale</td>
<td style="border:1px solid black;">Users, Administrators</td>
<td style="border:1px solid black;">Users, Administrators</td>
<td style="border:1px solid black;">Users, Administrators</td>
<td style="border:1px solid black;">Users, Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti accesso tramite Servizi terminal</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Backup di file e directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ignora controllo visite</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modifica dell'orario di sistema</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di file di paging</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione di oggetti condivisi permanenti</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di un oggetto token</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Debug di programmi</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso al computer dalla rete</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso come processo batch</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Support_<br />
388945a0,<br />
Guest, tutti gli account di servizio</td>
<td style="border:1px solid black;">Support_<br />
388945a0, Guest, tutti gli account di servizio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso tramite Servizi terminal</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Everyone</td>
<td style="border:1px solid black;">Everyone</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impostazione account computer ed utente a tipo trusted per la delega</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
</tbody>
</table>
  
##### Accesso al computer dalla rete
  
Questa impostazione di criterio consente ad altri utenti sulla rete di connettersi al computer ed è richiesta da vari protocolli di rete che contengono a loro volta protocolli basati su SMB (Server Message Block), NetBIOS, CIFS (Common Internet File System) e COM+ (Component Object Model Plus).
  
L'impostazione **Accesso al computer dalla rete** è configurata su **Non definito** per l'ambiente EC e su **Administrators** per l'ambiente SSLF.
  
##### Agisci come parte del sistema operativo
  
Questa impostazione di criterio consente a un processo di assumere l'identità di un utente per ottenere l'accesso alle risorse cui l'utente è autorizzato ad accedere.
  
Per tale ragione, l'impostazione **Agisci come parte del sistema operativo** è limitata a **Nessuno** per entrambi gli ambienti trattati in questo capitolo.
  
##### Regolazione quote di memoria per un processo
  
Questa impostazione di criterio consente agli utenti di regolare la quantità massima di memoria disponibile per un processo. La capacità di regolare le quote di memoria è utile per ottimizzare le prestazioni del sistema, ma può essere oggetto di abuso. Nelle mani sbagliate, infatti, potrebbe essere utilizzata per sferrare un attacco di tipo Denial of Service (DoS).
  
Per tale ragione, l'impostazione **Regolazione quote di memoria per un processo** è limitata agli **Administrators**, al **Servizio locale**, e al **Servizio di Rete** per entrambi i tipi di computer dell'ambiente SSLF ed è configurata su **Non definito** per i computer dell'ambiente EC.
  
##### Consenti accesso locale
  
Questa impostazione di criterio permette di stabilire quali utenti possono accedere interattivamente al computer nell'ambiente. Gli accessi avviati premendo la sequenza CTRL + ALT + CANC sulla tastiera del computer client richiedono questo diritto utente. Anche gli utenti che tentano di effettuare l'accesso tramite Servizi terminal o Microsoft IIS (Internet Information Services) richiedono tale diritto.
  
All'account **Guest** questo diritto utente viene concesso per impostazione predefinita. Sebbene questo account sia disattivato per impostazione predefinita, Microsoft consiglia di attivare questa impostazione attraverso i Criteri di gruppo. Questo diritto utente dovrebbe tuttavia essere limitato, in genere, ai gruppi **Administrators** e **Users**. Assegnare questo diritto utente ai **Backup Operators** se l'organizzazione richiede che dispongano di tale funzionalità.
  
L'impostazione **Consenti accesso locale** è limitata ai gruppi **Users** e **Administrators** per i due ambienti trattati in questo capitolo.
  
##### Consenti accesso tramite Servizi terminal
  
Questa impostazione di criterio determina quali utenti o gruppi hanno il diritto di effettuare l'accesso come client di Servizi terminal. Questo è un diritto necessario per gli utenti desktop remoto. Se l'organizzazione utilizza Assistenza remota come parte della strategia Help Desk, creare un gruppo e assegnargli questo diritto utente attraverso i Criteri di gruppo. Se l'help desk dell'organizzazione non utilizza Assistenza remota, assegnare questo diritto utente soltanto al gruppo **Administrators** o utilizzare la funzione Gruppi con restrizioni per assicurarsi che nessun account utente faccia parte del gruppo **Utenti desktop remoto**.
  
Limitare la concessione di questo diritto al gruppo **Administrators** ed, eventualmente, al gruppo **Utenti desktop remoto** eviterà che utenti indesiderati accedano ai computer della rete tramite la funzione Assistenza remota in Windows XP Professional.
  
L'impostazione **Consenti accesso tramite Servizi terminal** è configurata su **Non definito** per l'ambiente EC. Al fine di ottenere una maggiore protezione, questa impostazione di criterio è configurata su **Nessuno** per l'ambiente SSLF.
  
##### Backup di file e directory
  
Questa impostazione di criterio consente agli utenti di aggirare le autorizzazioni per file e directory per eseguire il backup del sistema. Questo diritto utente è attivato soltanto quando un'applicazione (come NTBACKUP) tenta di accedere a un file o a una directory tramite l'API (Application Programming Interface) dell'applicazione di backup del file system NTFS. In caso contrario, si applicano le autorizzazioni di file e directory assegnate.
  
L'impostazione **Backup di file e directory** è configurata su **Non definito** per i computer nell'ambiente EC. Questa impostazione di criterio è configurata su **Administrators** per l'ambiente SSLF.
  
##### Ignora controllo visite
  
Questa impostazione di criterio consente agli utenti che non dispongono dell'autorizzazione di accesso "Visita cartelle" di "passare attraverso" le cartelle quando si spostano lungo un percorso nel file system NTFS o nel Registro di sistema. Questo diritto utente non consente agli utenti di visualizzare l'elenco del contenuto di una cartella, ma esclusivamente di attraversare le directory.
  
L'impostazione **Ignora controllo visite** è configurata su **Non definito** per i computer nell'ambiente EC. È configurata sui gruppi **Administrators** e **Users** per l'ambiente SSLF.
  
##### Modifica dell'orario di sistema
  
Questa impostazione di criterio determina quali utenti e gruppi possono modificare l'ora e la data dell'orologio interno dei computer dell'ambiente. Gli utenti ai quali è assegnato questo diritto utente possono influenzare l'aspetto dei registri eventi. Se si cambia l'ora di un computer, gli eventi registrati riporteranno la nuova ora, non quella effettiva in cui si sono verificati gli eventi.
  
L'impostazione **Modifica dell'orario di sistema** è configurata sul gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: le discrepanze fra l'ora nel computer locale e quella nei controller del dominio nell'ambiente possono causare problemi per il protocollo di autenticazione Kerberos, il che potrebbe impedire agli utenti di accedere al dominio o ottenere l'autorizzazione per accedere alle risorse del dominio dopo la connessione in rete. Inoltre, se l'ora del sistema non è sincronizzata con quella dei controller del dominio, si verificheranno problemi quando si applicano i Criteri di gruppo ai computer client.
  
##### Creazione di file di paging
  
Questa impostazione di criterio consente agli utenti di modificare le dimensioni del file di paging. Rendendo le dimensioni del file di paging estremamente grandi o ridotte, un pirata informatico potrebbe influenzare le prestazioni di un computer compromesso.
  
L'impostazione **Creazione di file di paging** è configurata su **Administrators** per tutti i computer degli ambienti EC e SSLF.
  
##### Creazione di oggetti condivisi permanenti
  
Questa impostazione di criterio consente agli utenti di creare oggetti della directory nel gestore oggetti. Questo privilegio è utile per i componenti in modalità kernel che estendono lo spazio dei nomi degli oggetti. Tuttavia, questo diritto utente è assegnato per impostazione predefinita ai componenti che vengono eseguiti in modalità kernel. Pertanto, di norma non è necessario assegnarlo esplicitamente.
  
L'impostazione **Creazione di oggetti condivisi permanenti** è configurata su **Non definito** per l'ambiente EC e su **Nessuno** per l'ambiente SSLF.
  
##### Creazione di un oggetto token
  
Questa impostazione di criterio consente a un processo di creare un token di accesso, in grado di fornire diritti elevati per accedere a dati riservati. Negli ambienti dove la protezione ha priorità elevata, questo diritto non dovrebbe essere assegnato a nessun utente. I processi che richiedono questa funzionalità dovrebbero utilizzare l'account di sistema locale, a cui questo diritto utente è assegnato per impostazione predefinita.
  
L'impostazione **Creazione di un oggetto token** è configurata su **Non definito** per l'ambiente EC e su **Nessuno** per l'ambiente SSLF.
  
##### Debug di programmi
  
Questa impostazione di criterio determina quali utenti possono allegare un debugger ai processi o al kernel, che fornisce accesso completo ai componenti del sistema operativo riservati e critici. Questo diritto utente è necessario quando gli amministratori vogliono approfittare delle patch che supportano la funzionalità "in-memory patching", conosciuta anche come "hotpatching". Per ulteriori informazioni sulle funzionalità più recenti in Microsoft Package Installer, vedere "[The Package Installer (Formerly Called Update.exe) for Microsoft Windows Operating Systems and Windows Components](http://support.microsoft.com/kb/832475/)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/deployment/winupdte.mspx. Un pirata informatico potrebbe sfruttare questo diritto utente, perciò viene assegnato soltanto al gruppo **Administrators** per impostazione predefinita.
  
**Nota**: Microsoft ha rilasciato numerose patch di protezione nell'ottobre 2003 che utilizzavano una versione di Update.exe per la quale era necessario che l'amministratore disponesse del diritto utente **Debug di programmi**. Gli amministratori che non disponevano di questo diritto non sono stati in grado di installare queste patch finché non hanno riconfigurato i loro diritti utente. Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Blocco di Aggiornamenti prodotto di Windows o utilizzo della maggior parte o di tutte le risorse della CPU](http://support.microsoft.com/default.aspx?kbid=830846)" all'indirizzo http://support.microsoft.com/default.aspx?kbid=830846.
  
Il diritto utente **Debug di programmi** è molto potente. Perciò, questa impostazione di criterio è configurata su **Administrators** per l'ambiente EC e sul suo valore predefinito di **Nessuno** per l'ambiente SSLF.
  
##### Nega accesso al computer dalla rete
  
Questa impostazione di criterio impedisce agli utenti di connettersi a un computer dalla rete, il che consentirebbe agli utenti di accedere ai dati ed eventualmente di modificarli in modo remoto. In un ambiente con livello di protezione alto, gli utenti remoti non dovrebbero poter accedere ai dati su un computer. Si dovrebbe invece adottare la condivisione dei file tramite l'utilizzo dei server di rete.
  
L'impostazione **Nega accesso al computer dalla rete** è configurata sugli account **Support\_388945a0** e **Guest** per i computer in entrambi gli ambienti trattati in questo capitolo.
  
##### Nega accesso come processo batch
  
Questa impostazione di criterio impedisce agli utenti di effettuare l'accesso attraverso una funzionalità di coda batch, utilizzata in Windows Server 2003 per pianificare i processi da eseguire automaticamente una o più volte in futuro.
  
L'impostazione **Nega accesso come processo batch** è configurata su **Non definito** per l'ambiente EC e su **Support\_388945a0** e **Guest** per l'ambiente SSLF.
  
##### Nega accesso locale
  
Questa impostazione di criterio impedisce agli utenti di accedere in locale alla console del computer. Se utenti non autorizzati potessero accedere in locale a un computer, potrebbero scaricare codici dannosi o elevare i loro privilegi sul computer (se i pirati informatici hanno accesso fisico alla console, ci sono altri rischi di considerare). Questo diritto utente non dovrebbe essere assegnato agli utenti che devono accedere fisicamente alla console del computer.
  
L'impostazione **Nega accesso locale** è configurata su **Non definito** per l'ambiente EC e su **Support\_388945a0** e **Guest** per l'ambiente SSLF. Inoltre, questo diritto utente dovrebbe essere assegnato agli account di servizio per l'ambiente SSLF aggiunti al computer per evitarne l'abuso.
  
##### Nega accesso tramite Servizi terminal
  
Questa impostazione di criterio impedisce agli utenti di accedere a computer dell'ambiente tramite connessioni Desktop remoto. Se si assegna questo diritto utente al gruppo **Everyone**, è possibile evitare che anche i membri del gruppo predefinito **Administrators** utilizzino i Servizi terminal per accedere ai computer dell'ambiente.
  
L'impostazione **Nega accesso tramite Servizi terminal** è configurata su **Non definito** per l'ambiente EC e sul gruppo **Everyone** per l'ambiente SSLF.
  
##### Impostazione account computer ed utente a tipo trusted per la delega
  
Questa impostazione di criterio consente agli utenti di modificare l'impostazione relativa all'**attendibilità per la delega** su un oggetto computer in Active Directory. L'abuso di questo privilegio potrebbe consentire a utenti non autorizzati di rappresentare altri utenti sulla rete.
  
Per questa ragione, l'impostazione **Impostazione account computer ed utente a tipo trusted per la delega** è configurata su **Non definito** per l'ambiente EC e su **Nessuno** per l'ambiente SSLF.
  
#### Diritti utente F –T
  
**Tabella 3.3 Raccomandazioni relative alle impostazioni di assegnazione dei diritti utente – Parte 2**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Arresto forzato da un sistema remoto</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Generazione controlli di protezione</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aumenta priorità di esecuzione</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Installa e disinstalla driver periferica</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco di pagine in memoria</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso come processo batch</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso come servizio</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Servizio di rete, Servizio locale</td>
<td style="border:1px solid black;">Servizio di rete, Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione file registro di controllo e di protezione</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Modificare le variabili di ambiente del firmware</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Esecuzione operazioni di manutenzione volume</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di profilo del singolo processo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione di profilo delle prestazioni del sistema</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rimozione del computer dall'alloggiamento</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sostituzione token a livello di processo</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
<td style="border:1px solid black;">Servizio locale, Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ripristina file e directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Arresto del sistema</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
<td style="border:1px solid black;">Administrators, Users</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Diventa proprietario (di file o altri oggetti)</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
</tbody>
</table>
  
La tabella seguente riassume le raccomandazioni relative alle impostazioni di assegnazione dei diritti utente che iniziano con le lettere dalla F alla T. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
##### Arresto forzato da un sistema remoto
  
Questa impostazione di criterio consente agli utenti di arrestare i computer basati su Windows XP da postazioni remote sulla rete. Qualsiasi utente a cui è stato assegnato questo diritto utente può dare origine a una condizione di negazione del servizio DoS, rendendo il computer non disponibile per le richieste di servizio degli utenti. Perciò, Microsoft consiglia di assegnare questo diritto utente solo ad amministratori estremamente affidabili.
  
L'impostazione **Arresto forzato da un sistema remoto** è configurata sul gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Generazione controlli di protezione
  
Questa impostazione di criterio determina quale utente o processo può generare registrazioni di controllo nel registro di protezione. Un pirata informatico potrebbe utilizzare questa funzionalità per creare numerosi eventi controllati, il che renderebbe più difficile localizzare un'attività illecita da parte dell'amministratore del sistema. Inoltre, se il registro eventi è configurato in modo da sovrascrivere gli eventi come necessario, le prove di attività non autorizzate potrebbero venire sovrascritte da una grande quantità di eventi non correlati.
  
Per questa ragione, l'impostazione **Generazione controlli di protezione** è configurata sui gruppi **Servizio locale** e **Servizio di rete** per entrambi gli ambienti trattati in questo capitolo.
  
##### Aumenta priorità di esecuzione
  
Questa impostazione di criterio consente agli utenti di modificare il tempo di elaborazione necessario per un processo. Un pirata informatico potrebbe utilizzare questa funzionalità per aumentare la priorità di un processo fino al livello In tempo reale e creare una condizione di negazione del servizio DoS per un computer.
  
Per questa ragione, l'impostazione **Aumenta priorità di esecuzione** è configurata sul gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Installa e disinstalla driver periferica
  
Questa impostazione di criterio consente agli utenti di caricare dinamicamente un nuovo driver della periferica su un sistema. Un pirata informatico potrebbe potenzialmente utilizzare questa funzionalità per installare un codice dannoso che sembra un driver della periferica. Questo diritto utente e questa appartenenza al gruppo **Power Users** o **Administrators** sono necessari perché gli utenti possano aggiungere stampanti locali o driver della stampante in Windows XP.
  
Poiché questo diritto utente può essere utilizzato da un pirata informatico, l'impostazione **Installa e disinstalla driver periferica** è configurata sul gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Blocco di pagine in memoria
  
Consente a un processo di conservare i dati nella memoria fisica, il che impedisce al sistema di eseguire il paging dei dati alla memoria virtuale su disco. Se si assegna questo diritto utente, le prestazioni del computer ne risentiranno notevolmente.
  
Per questa ragione, l'impostazione **Blocco di pagine in memoria** è configurata su **Nessuno** per entrambi gli ambienti trattati in questo capitolo.
  
##### Accesso come processo batch
  
Questa impostazione di criterio consente agli account di effettuare l'accesso utilizzando il servizio Utilità di pianificazione. Poiché l'utilità di pianificazione è spesso utilizzata per scopi amministrativi, può essere necessaria nell'ambiente EC. Tuttavia, il suo utilizzo dovrebbe essere limitato nell'ambiente SSLF per evitare l'abuso delle risorse di sistema o per impedire ai pirati informatici di utilizzare tale diritto per avviare codice dannoso dopo aver ottenuto l'accesso a livello di utente a un computer.
  
L'impostazione **Accesso come processo batch** è configurata su **Non definito** per l'ambiente EC e su **Nessuno** per l'ambiente SSLF.
  
##### Accesso come servizio
  
Questa impostazione di criterio consente agli account di avviare servizi di rete o di registrare un processo come un servizio in esecuzione sul sistema. Questo diritto utente dovrebbe essere limitato su qualunque computer in un ambiente SSLF, ma poiché molte applicazioni potrebbero richiedere questo privilegio, è necessario valutarlo e verificarlo attentamente prima di configurarlo in un ambiente EC.
  
L'impostazione **Accesso come servizio** è configurata su **Non definito** per l'ambiente EC e su **Servizio di rete** e **Servizio locale** per l'ambiente SSLF.
  
##### Gestione file registro di controllo e di protezione
  
Questa impostazione di criterio determina quali utenti possono modificare le opzioni di controllo per i file e le directory e cancellare il registro di protezione.
  
Poiché questa funzionalità rappresenta un pericolo relativamente ridotto, l'impostazione **Gestione file registro di controllo e di protezione** impone il valore predefinito del gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Modificare le variabili di ambiente del firmware
  
Questa impostazione di criterio consente agli utenti di configurare le variabili ambientali di tutto il sistema che interessano la configurazione hardware. Queste informazioni vengono di norma conservate nell'Ultima configurazione valida. La modifica di questi valori potrebbe causare errori hardware che risulterebbero in una condizione di negazione del servizio.
  
Poiché questa funzionalità rappresenta un pericolo relativamente ridotto, l'impostazione **Modificare le variabili di ambiente del firmware** impone il valore predefinito del gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Esecuzione operazioni di manutenzione volume
  
Questa impostazione di criterio consente agli utenti di gestire il volume del sistema o la configurazione del disco, con la possibilità di eliminare un volume, causare una perdita di dati e una condizione di negazione del servizio.
  
L'impostazione **Esecuzione operazioni di manutenzione volume** impone il valore predefinito del gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Creazione di profilo del singolo processo
  
Questa impostazione di criterio determina quali utenti possono utilizzare gli strumenti per controllare le prestazioni dei processi non di sistema. Di norma, non è necessario configurare questo diritto utente per utilizzare lo snap-in MMC (Microsoft Management Console) Prestazioni. Tuttavia, questo diritto è necessario se il Monitor di sistema è configurato per raccogliere dati utilizzando Strumentazione gestione Windows (WMI). La limitazione del diritto utente **Creazione di profilo del singolo processo** impedisce agli intrusi di ottenere ulteriori informazioni che potrebbero essere utilizzate per organizzare un attacco al sistema.
  
L'impostazione **Creazione di profilo del singolo processo** è configurata su **Non definito** per i computer nell'ambiente EC e sul gruppo **Administrators** per l'ambiente SSLF.
  
##### Creazione di profilo delle prestazioni del sistema
  
Questa impostazione di criterio consente agli utenti di utilizzare strumenti per visualizzare le prestazioni di diversi processi di sistema, che potrebbero essere abusati per consentire ai pirati informatici di determinare i processi attivi di un sistema, fornendo informazioni sulla superficie di attacco potenziale del computer.
  
L'impostazione **Creazione di profilo delle prestazioni del sistema** impone il valore predefinito del gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
##### Rimozione del computer dall'alloggiamento
  
Questa impostazione di criterio consente all'utente di un computer portatile di selezionare **Rilascia PC** dal menu **Start** per rimuovere il computer dall'alloggiamento.
  
L'impostazione **Rimozione del computer dall'alloggiamento** è configurata sui gruppi **Administrators** e **Users** per entrambi gli ambienti trattati in questo capitolo.
  
##### Sostituzione token a livello di processo
  
Questa impostazione di criterio consente a un processo o servizio di avviare un altro servizio o processo con un token di accesso di protezione diverso, che può essere utilizzato per modificare il token di accesso di protezione di quel sottoprocesso e causare l'acquisizione di privilegi più elevati.
  
L'impostazione **Sostituzione token a livello di processo** è configurata sui valori predefiniti di **Servizio locale** e **Servizio di rete** per entrambi gli ambienti trattati in questo capitolo.
  
##### Ripristina file e directory
  
Questa impostazione di criterio determina quali utenti possono aggirare file, directory, registro e altre autorizzazioni sugli oggetti persistenti al momento di ripristinare i file e le directory sottoposti a backup nei computer dell'ambiente su cui è in esecuzione Windows XP. Questo diritto utente determina inoltre quali utenti possono impostare identità di protezione valide come proprietari degli oggetti; è simile al diritto utente **Backup di file e directory.**
  
L'impostazione **Ripristina file e directory** è configurata su **Non definito** per l'ambiente EC e sul gruppo **Administrators** per l'ambiente SSLF.
  
##### Arresto del sistema
  
Questa impostazione di criterio determina quali utenti che hanno effettuato l'accesso in locale ai computer dell'ambiente possono arrestare il sistema operativo con il comando Chiudi sessione. Abusi di questo diritto utente possono portare alla negazione del servizio. Negli ambienti con livello di protezione alto, Microsoft consiglia di assegnare questo diritto utente soltanto ai gruppi **Administrators** e **Users**.
  
L'impostazione **Arresto del sistema** è configurata sui gruppi **Administrators** e **Users** per entrambi gli ambienti trattati in questo capitolo.
  
##### Diventa proprietario (di file o altri oggetti)
  
Questa impostazione di criterio consente agli utenti di assumersi la proprietà di file, cartelle, chiavi del Registro di sistema, processi o thread. Questo diritto utente ignora qualunque autorizzazione configurata per proteggere gli oggetti e assegnare la proprietà all'utente specificato.
  
L'impostazione **Diventa proprietario (di file o altri oggetti)** è configurata sul valore predefinito del gruppo **Administrators** per entrambi gli ambienti trattati in questo capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Opzioni di protezione
  
Le impostazioni delle Opzioni di protezione applicate attraverso i Criteri di gruppo sui computer dotati di Windows XP nell'ambiente sono utilizzate per attivare o disattivare le funzionalità come l'accesso all'unità floppy e ai CD-ROM e i prompt di accesso. Queste impostazioni sono inoltre utilizzate per configurarne altre, ad esempio la firma digitale dei dati, i nomi account Administrator e Guest e la modalità di installazione dei driver.
  
È possibile configurare le impostazioni per le opzioni di protezione nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione del computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione**
  
Non tutte le impostazioni trattate in questa sezione sono presenti in tutti i tipi di sistema. Pertanto, nei sistemi in cui sono presenti potrebbe essere necessario modificare manualmente le impostazioni che comprendono la parte Opzioni di protezione dei Criteri di gruppo definite in questa sezione, per renderle pienamente operative. In alternativa, per assicurare la piena operatività delle prescrizioni delle impostazioni, è possibile modificare singolarmente i modelli dei Criteri di gruppo per includere le opzioni di impostazione appropriate.
  
Le sezioni seguenti forniscono le raccomandazioni relative alle impostazioni delle Opzioni di protezione e sono raggruppate secondo il tipo di oggetto. Ogni sezione contiene una tabella che riassume le impostazioni e nelle sottosezioni che seguono ogni tabella sono presenti informazioni dettagliate. Le raccomandazioni sono relative sia ai computer client desktop sia portatili nei due tipi di ambienti protetti trattati in questo capitolo, cioè gli ambienti EC (Enterprise Client) e gli ambienti SSLF (Specialized Security – Limited Functionality).
  
#### Account
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per gli account. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.5 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – account**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Account: stato account Administrator</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Account: stato account Guest</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Account: limitare l'uso locale di account con password vuote all'accesso alla console</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Account: rinomina account amministratore</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Account: rinomina account guest</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
<td style="border:1px solid black;">Consigliata</td>
</tr>
</tbody>
</table>
  
##### Account: stato account Administrator
  
Questa impostazione di criterio attiva o disattiva l'account Administrator durante il normale funzionamento. Quando un computer viene avviato in modalità provvisoria, l'account Administrator è sempre attivato, indipendentemente dalla configurazione di questa impostazione.
  
L'impostazione **Account: stato account Administrator** è configurata su **Non definito** per l'ambiente EC e su **Abilitato** per l'ambiente SSLF.
  
##### Account: stato account Guest
  
Questa impostazione di criterio determina se l'account Guest è attivato o disattivato. L'account Guest consente agli utenti della rete non autenticati di ottenere l'accesso al sistema.
  
L'opzione di protezione **Account: stato account Guest** è configurata su **Disabilitato** per i due ambienti trattati in questo capitolo.
  
##### Account: limitare l'uso locale di account con password vuote all'accesso alla console
  
Questa impostazione di criterio determina se è possibile utilizzare gli account locali non protetti con password per eseguire l’accesso da postazioni che non siano la console fisica del computer. Se si attiva questa impostazione di criterio, non sarà possibile utilizzare gli account locali con password vuote per accedere alla rete da computer client remoti. Sarà possibile effettuare l'accesso con questi account soltanto dalla tastiera del computer.
  
L'impostazione **Account: limitare l'uso locale di account con password vuote all'accesso alla console** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
##### Account: rinomina account amministratore
  
L'account amministratore locale incorporato è un nome account ben noto agli intrusi. Microsoft consiglia di sceglierne un altro, evitando nomi che denotino account amministrativi o ad accesso con privilegi elevati. Ricordarsi inoltre di cambiare la descrizione predefinita per l'amministratore locale tramite la console di Gestione computer.
  
La raccomandazione di utilizzare l'impostazione **Account: rinomina account amministratore** si riferisce a entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: l'impostazione di questo criterio non viene configurata nei modelli di protezione, né viene indicato un nuovo nome utente per l'account nella guida. I nomi utente suggeriti sono omessi per assicurare che le organizzazioni che adottano questa guida non utilizzino lo stesso nome utente nuovo nei rispettivi ambienti.
  
##### Account: rinomina account guest
  
Anche il nome dell'account guest locale incorporato è ben noto agli hacker. Microsoft consiglia di scegliere un nome per questo account che non ne indichi lo scopo. Per una maggiore protezione, assicurarsi di rinominare questo account anche dopo averlo disattivato (operazione consigliata).
  
La raccomandazione di utilizzare l'impostazione **Account: rinomina account guest** si riferisce a entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: l'impostazione di questo criterio non viene configurata nei modelli di protezione, né viene indicato un nuovo nome utente per l'account nella guida. I nomi utente suggeriti sono omessi per assicurare che le organizzazioni che adottano questa guida non utilizzino lo stesso nome utente nuovo nei rispettivi ambienti.
  
#### Controllo
  
La tabella seguente riassume le impostazioni di controllo consigliate. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.6 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – controllo**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controllo: controllo accesso oggetti di sistema globale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo: controllo utilizzo dei privilegi di backup e di ripristino</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
</tr>
</tbody>
</table>
  
##### Controllo: controllo accesso oggetti di sistema globale
  
Questa impostazione di criterio crea un elenco di controllo di accesso di sistema (SACL) predefinito per gli oggetti di sistema come i mutex, gli eventi, i semafori e le periferiche M-DOS e consente la verifica dell'accesso a tali oggetti.
  
Se l'impostazione **Controllo: controllo accesso oggetti di sistema globale** è attivata, una grande quantità di eventi di protezione potrebbe riempire velocemente il registro eventi di protezione. Quindi, questa impostazione di criterio è configurata su **Non definito** per l'ambiente EC e su **Disattivato** per l'ambiente SSLF.
  
##### Controllo: controllo utilizzo dei privilegi di backup e di ripristino
  
Questa impostazione di criterio determina se controllare l'utilizzo di tutti i privilegi utente, incluso Backup e ripristino, quando l'impostazione **Controlla uso dei privilegi** è attiva. Se si attivano entrambi i criteri, sarà generato un evento di controllo per ogni file del quale viene eseguito il backup o che viene ripristinato.
  
Se l'impostazione **Controllo: controllo utilizzo dei privilegi di backup e di ripristino** è attivata, una grande quantità di eventi di protezione potrebbe riempire velocemente il registro eventi di protezione. Quindi, questa impostazione di criterio è configurata su **Non definito** per l'ambiente EC e su **Disattivato** per l'ambiente SSLF.
  
##### Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione
  
Questa impostazione di criterio determina se il sistema debba essere arrestato quando non è in grado di registrare gli eventi di protezione. In conformità ai criteri TCSEC (Trusted Computer System Evaluation Criteria) di classe C2 e alla certificazione Criteri comuni, questa impostazione è un requisito necessario per impedire il verificarsi di eventi controllabili nel caso in cui questi non possano essere registrati dal sistema di controllo. Microsoft ha scelto di garantire la conformità a tale requisito mediante l'arresto del sistema e la visualizzazione di un messaggio di interruzione in caso di errore del sistema di controllo. Quando questa impostazione di criterio è attivata, il sistema viene arrestato se per qualsiasi ragione il controllo di protezione non può essere registrato.
  
Se l'impostazione **Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione** è attivata, possono verificarsi errori di sistema non previsti. Quindi, questa impostazione di criterio è configurata su **Non definito** per entrambi gli ambienti descritti in questo capitolo.
  
#### Periferiche
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per le periferiche. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.6 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – periferiche**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Periferiche: consenti il disinserimento senza dover effettuare l'accesso</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibili</td>
<td style="border:1px solid black;">Administrator, Interactive Users</td>
<td style="border:1px solid black;">Administrator, Interactive Users</td>
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Administrators</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periferiche: non consentire agli utenti di installare i driver della stampante</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periferiche: limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periferiche: funzionamento installazione driver privo di firma digitale</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
</tr>
</tbody>
</table>
  
##### Periferiche: consenti il disinserimento senza dover effettuare l'accesso
  
Questa impostazione di criterio determina se un computer portabile può essere disinserito se l'utente non accede al sistema. Attivare questa impostazione di criterio per eliminare un requisito per l'accesso e consentire l’utilizzo di un pulsante di rimozione hardware esterno per rimuovere il computer dall’alloggiamento di espansione. Se si disattiva questa impostazione di criterio, a un utente che non non ha effettuato l'accesso deve essere assegnato il diritto utente **Rimozione del computer dall'alloggiamento** (non definito in questa guida).
  
L'impostazione **Periferiche:** **consenti il disinserimento senza dover effettuare l'accesso** è configurata su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
##### Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibili
  
Questa impostazione di criterio determina consente di determinare chi può formattare e rimuovere supporti removibili. È possibile utilizzare questa impostazione di criterio per impedire agli utenti non autorizzati di rimuovere dati su un computer per accedervi su un altro computer su cui hanno privilegi di amministratore locale.
  
Per una maggiore protezione, l'impostazione **Periferiche:** **è consentita la formattazione e la rimozione dei supporti rimovibili** è limitata ai gruppi **Administrators** e **Interactive Users** per l'ambiente EC e al solo gruppo **Administrators** per l'ambiente SSLF.
  
##### Periferiche: non consentire agli utenti di installare i driver della stampante
  
Un hacker può mascherare un programma cavallo di Troia da driver di stampante. Gli utenti potrebbero essere indotti a utilizzare obbligatoriamente il programma per stampare, ma quest'ultimo potrebbe invece liberare codice dannoso sulla rete dei computer. Per ridurre la possibilità che si verifichi tale evento, soltanto gli amministratori dovrebbero poter installare i driver della stampante. Tuttavia, dato che i portatili sono dispositivi mobili, per poter continuare a lavorare gli utenti che li utilizzano potrebbero dover installare di quando in quando un driver di stampante da un'origine remota. Pertanto questa impostazione dovrebbe essere disattivata per gli utenti mobili, mentre dovrebbe essere sempre attivata per quelli desktop.
  
L'impostazione **Periferiche:** **non consentire agli utenti di installare i driver della stampante** è configurata su **Abilitato** per i computer desktop in entrambi gli ambienti trattati in questo capitolo e su **Disabilitato** per gli utenti mobili in entrambi gli ambienti.
  
##### Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale
  
Questa impostazione di criterio determina se l'unità CD-ROM è accessibile contemporaneamente sia agli utenti locali sia a quelli remoti. Se si attiva questa impostazione di criterio, solo gli utenti connessi interattivamente possono accedere ai supporti dall'unità CD-ROM. Quando questa impostazione è attivata e nessuno è connesso, è possibile accedere all'unità CD-ROM dalla rete. Se si abilita questa impostazione, l'utilità di backup di Windows non funzionerà, se per il processo di backup sono state specificate copie shadow del volume. Anche i prodotti di backup di terze parti che utilizzano le copie shadow del volume non funzioneranno.
  
L'impostazione **Periferiche:** **limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale** è configurata su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
##### Periferiche: limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale
  
Questa impostazione di criterio determina se l'unità floppy è accessibile contemporaneamente sia agli utenti locali sia a quelli remoti. Se si attiva questa impostazione di criterio, solo gli utenti connessi interattivamente possono accedere ai supporti dell'unità floppy. Quando questa impostazione è attivata e nessuno è connesso, è possibile accedere ai supporti dell'unità floppy dalla rete. Se si abilita questa impostazione, l'utilità di backup di Windows non funzionerà, se per il processo di backup sono state specificate copie shadow del volume. Anche i prodotti di backup di terze parti che utilizzano le copie shadow del volume non funzioneranno.
  
L'impostazione **Periferiche:** **limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale** è configurata su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
##### Periferiche: funzionamento installazione driver privo di firma digitale
  
Determina che cosa accade quando viene effettuato un tentativo di installare un driver di periferica (tramite l'API del programma di installazione)che non è dotato di firma digitale WHQL (Windows Hardware Quality Lab). Questa opzione consente di impedire l’installazione di driver privi di firma digitale oppure di avvisare l'amministratore che è in corso un tentativo di installazione di un driver privo di firma digitale, in modo da evitare che vengano installati driver non certificati per Windows XP. Se si configura questa impostazione di criterio sul valore **Avvisa ma consenti installazione**, un problema potenziale consiste nel fatto che non è possibile eseguire script di installazione automatica se si tenta di installare driver privi di firma digitale.
  
Per questa ragione, l'impostazione **Periferiche:** **funzionamento installazione driver privo di firma digitale** è configurata su **Avvisa ma consenti installazione** per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: al momento di implementare questa impostazione di criterio, per ridurre il rischio che essa provochi errori di installazione, i client dovrebbero essere configurati completamente con tutte le applicazioni software standard prima di applicare i Criteri di gruppo.
  
#### Membro di dominio
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per i membri di dominio. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.8 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – Membro di dominio**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controller di dominio: disabilitazione cambio password account computer</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controller di dominio: validità massima password account computer</td>
<td style="border:1px solid black;">30 giorni</td>
<td style="border:1px solid black;">30 giorni</td>
<td style="border:1px solid black;">30 giorni</td>
<td style="border:1px solid black;">30 giorni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Membro di dominio: chiave di sessione avanzata (Windows 2000 o versioni successive)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)
  
Questa impostazione di criterio determina se il traffico del canale protetto avviato dal membro di dominio deve essere firmato o crittografato. Se per un sistema è abilitata questa opzione, il sistema non potrà stabilire un canale protetto con un controller di dominio che non sia in grado di crittografare o firmare tutto il traffico del canale protetto.
  
L'impostazione **Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)
  
Questa impostazione di criterio permette di stabilire se un membro del dominio può richiedere la crittografia per tutto il traffico del canale protetto da esso avviato. Se si attiva questa impostazione di criterio, il membro di dominio richiederà la crittografia di tutto il traffico del canale protetto. Se si disattiva questa impostazione di criterio, al membro di dominio sarà impedito di richiedere la crittografia del canale protetto.
  
L'impostazione **Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)
  
Questa impostazione di criterio permette di stabilire se un membro del dominio può richiedere la firma digitale per tutto il traffico del canale protetto da esso avviato. Le firme digitali evitano che il traffico venga modificato da un intruso che riesca ad acquisire i dati mentre questi viaggiano sulla rete.
  
L'impostazione **Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Controller di dominio: disabilitazione cambio password account computer
  
Questa impostazione di criterio determina se un membro di dominio può modificare periodicamente la password dell'account del computer. Se si attiva questa impostazione di criterio, il membro di dominio non sarà in grado di modificare la password dell'account del computer. Se si disattiva questa impostazione di criterio, il membro di dominio può modificare la password dell'account del computer come specificato dall'impostazione **Controller di dominio: validità massima password account computer**, ovvero ogni 30 giorni per impostazione predefinita. I computer sui quali non è possibile modificare automaticamente le password dell'account sono potenzialmente vulnerabili, poiché un pirata informatico potrebbe essere in grado di determinare la password dell'account di dominio del sistema.
  
Perciò, l'impostazione **Controller di dominio: disabilitazione cambio password account computer** è configurata su **Disabilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Controller di dominio: validità massima password account computer
  
Questa impostazione di criterio determina la durata massima della password dell'account di un computer. Per impostazione predefinita, le password dei membri del dominio vengono cambiate automaticamente ogni 30 giorni. Se si aumenta in modo significativo tale intervallo o si imposta il numero di giorni su 0 in modo che i computer non possano più modificare le password, i pirati informatici avranno a disposizione più tempo per eseguire un attacco di tipo "brute force" contro gli account dei computer.
  
Perciò, l'impostazione **Controller di dominio: validità massima password account computer** è configurata su **30 giorni** per entrambi gli ambienti trattati in questo capitolo.
  
##### Membro di dominio: chiave di sessione avanzata (Windows 2000 o versioni successive)
  
Quando questa impostazione di criterio è attivata, è possibile stabilire un canale protetto solo con controller di dominio in grado di crittografare i dati del canale protetto tramite una chiave di sessione avanzata (128 bit).
  
Per attivare questa impostazione di criterio, tutti i controller nel dominio devono essere in grado di crittografare i dati del canale protetto tramite una chiave avanzata, il che significa che devono essere dotati di Microsoft Windows 2000 o versioni successive. Se è necessaria la comunicazione con domini non dotati di Windows 2000, Microsoft consiglia di disattivare questa impostazione di criterio.
  
L'impostazione **Membro di dominio: richiesta chiave di sessione avanzata (Windows** **2000 o versioni successive)** è configurata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
#### Accesso interattivo
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per l'accesso interattivo. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.9 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – accesso interattivo**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso interattivo: non visualizzare l'ultimo nome utente</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso interattivo: non richiedere CTRL + ALT + DEL</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso</td>
<td style="border:1px solid black;">Questo sistema è limitato agli utenti autorizzati. Coloro che tentano di effettuare un accesso senza averne l'autorizzazione verranno perseguiti legalmente.</td>
<td style="border:1px solid black;">Questo sistema è limitato agli utenti autorizzati. Coloro che tentano di effettuare un accesso senza averne l'autorizzazione verranno perseguiti legalmente.</td>
<td style="border:1px solid black;">Questo sistema è limitato agli utenti autorizzati. Coloro che tentano di effettuare un accesso senza averne l'autorizzazione verranno perseguiti legalmente.</td>
<td style="border:1px solid black;">Questo sistema è limitato agli utenti autorizzati. Coloro che tentano di effettuare un accesso senza averne l'autorizzazione verranno perseguiti legalmente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso</td>
<td style="border:1px solid black;">CONTINUARE SENZA LA DEBITA AUTORIZZA<br />
ZIONE È ILLEGALE.</td>
<td style="border:1px solid black;">CONTINUARE SENZA LA DEBITA AUTORIZZA<br />
ZIONE È ILLEGALE.</td>
<td style="border:1px solid black;">CONTINUARE SENZA LA DEBITA AUTORIZZA<br />
ZIONE È ILLEGALE.</td>
<td style="border:1px solid black;">CONTINUARE SENZA LA DEBITA AUTORIZZA<br />
ZIONE È ILLEGALE.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso interattivo: richiesta cambio password prima della scadenza</td>
<td style="border:1px solid black;">14 giorni</td>
<td style="border:1px solid black;">14 giorni</td>
<td style="border:1px solid black;">14 giorni</td>
<td style="border:1px solid black;">14 giorni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso interattivo: funzionamento rimozione Smart card</td>
<td style="border:1px solid black;">Blocca workstation</td>
<td style="border:1px solid black;">Blocca workstation</td>
<td style="border:1px solid black;">Blocca workstation</td>
<td style="border:1px solid black;">Blocca workstation</td>
</tr>
</tbody>
</table>
  
##### Accesso interattivo: non visualizzare l'ultimo nome utente
  
Questa impostazione di criterio permette di stabilire se il nome account dell'ultimo utente che ha effettuato l'accesso ai computer client dell'organizzazione verrà visualizzato sullo schermo di accesso Windows di ciascun computer. L'attivazione di questa impostazione impedisce agli intrusi di raccogliere visivamente i nomi degli account dagli schermi dei computer desktop o portatili dell'organizzazione.
  
L'impostazione **Accesso interattivo: non visualizzare l'ultimo nome utente** è configurata su **Abilitato** per i due ambienti trattati in questo capitolo.
  
##### Accesso interattivo: non richiedere CTRL + ALT + DEL
  
La combinazione dei tasti CTRL+ALT+CANC stabilisce un percorso protetto al sistema operativo quando un utente immette un nome utente e una password. Quando questa impostazione del criterio è attivata, non è necessario che gli utenti immettano questa combinazione di tasti per accedere alla rete. Questa configurazione pone tuttavia un rischio di protezione, in quanto offre agli utenti la possibilità di effettuare l'accesso utilizzando credenziali di accesso più deboli.
  
L'impostazione **Accesso interattivo: non richiedere CTRL + ALT + CANC** è configurata su **Disabilitato** per i due ambienti trattati in questo capitolo.
  
##### Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso
  
Questa impostazione di criterio consente di specificare un messaggio di testo che viene visualizzato agli utenti quando effettuano l'accesso. Questo testo viene utilizzato principalmente per motivi legali, ad esempio per informare gli utenti delle conseguenze di un uso improprio delle informazioni aziendali o per avvisarli che le loro azioni potrebbero essere controllate. Il testo del messaggio specificato nella tabella precedente è un esempio consigliato sia per l'ambiente EC sia per l'ambiente SSLF.
  
L'impostazione **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** è attivata con il testo appropriato per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: qualsiasi avviso visualizzato deve essere preventivamente approvato dai responsabili legali e del personale dell'organizzazione. Inoltre, le impostazioni **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** e **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** devono essere entrambe abilitate perché una delle due funzioni correttamente.
  
##### Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso
  
Questa impostazione di criterio consente di specificare il testo sulla barra del titolo della finestra che gli utenti vedono visualizzata quando accedono al sistema. La ragione per implementare questa impostazione di criterio relativa al testo del messaggio è la stessa della precedente. In caso di attacchi le organizzazioni che non utilizzano questa opzione risultano meno tutelate dal punto di vista legale.
  
L'impostazione **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** è attivata con il testo appropriato per entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: qualsiasi avviso visualizzato deve essere preventivamente approvato dai responsabili legali e del personale dell'organizzazione. Inoltre, le impostazioni **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** e **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** devono essere entrambe abilitate perché una delle due funzioni correttamente.
  
##### Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)
  
Questa impostazione di criterio determina se un utente può accedere a un dominio Windows utilizzando le informazioni sull'account memorizzate nella cache. Le informazioni di accesso per gli account del dominio possono essere memorizzate nella cache in locale, per consentire agli utenti di effettuare l'accesso anche se non è possibile contattare un controller di dominio. Questa impostazione del criterio consente di specificare per quanti utenti univoci è possibile memorizzare informazioni nella cache locale. Il valore predefinito per questa impostazione è 10. Se questo valore è regolato su 0, la funzionalità di accesso alla cache è disattivata. Un pirata informatico in grado di accedere al file system del server potrebbe individuare le informazioni memorizzate nella cache e determinare le password degli utenti mediante un attacco di tipo "brute force".
  
L'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** è configurata su **2** per i computer desktop e portatili nell'ambiente EC e per i computer portatili nell'ambiente SSLF. Tuttavia, questa impostazione di criterio è configurata su **0** per i computer desktop nell'ambiente SSLF, perché questi devono essere sempre connessi alla rete dell'organizzazione in modo sicuro.
  
##### Accesso interattivo: richiesta cambio password prima della scadenza
  
Questa impostazione di criterio permette di stabilire con quale anticipo gli utenti vengono avvisati in merito alla scadenza della password. Microsoft consiglia di configurare questa impostazione di criterio su 14 giorni per dare agli utenti un preavviso sufficiente.
  
L'impostazione **Accesso interattivo: richiesta cambio password prima della scadenza** è configurata su **14 giorni** per entrambi gli ambienti trattati in questo capitolo.
  
##### Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation
  
Quando questa impostazione di criterio è attivata, l'account di dominio utilizzato per sbloccare il computer deve essere autenticato da un controller di dominio. Quando questa impostazione è disattivata, è possibile utilizzare le credenziali nella cache per sbloccare il computer. Microsoft consiglia di disattivare questa impostazione per gli utenti mobili in entrambi gli ambienti, perché questi utenti non hanno accesso di rete ai controller di dominio.
  
L'impostazione **Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation** è configurata su **Abilitato** per i computer desktop negli ambienti EC e SSLF. Tuttavia, questa impostazione di criterio è configurata su **Disabilitato** per i computer portatili in entrambi gli ambienti, in modo da consentire a questi utenti di lavorare quando non si trovano in ufficio.
  
##### Accesso interattivo: funzionamento rimozione Smart card
  
Determina l'azione conseguente alla rimozione della smart card dal lettore da parte di un utente connesso. Quando questa impostazione di criterio è configurata su **Blocca workstation**, la workstation viene bloccata quando si rimuove la smart card, consentendo agli utenti di allontanarsi dalla postazione, portare con sé la smart card e bloccare automaticamente la workstation. Se si configura questa impostazione di criterio su **Imponi disconnessione**, gli utenti saranno automaticamente disconnessi quando la smart card viene rimossa.
  
L'impostazione **Accesso interattivo: funzionamento rimozione Smart card** è configurata sull'opzione **Blocca workstation** per entrambi gli ambienti trattati in questo capitolo.
  
#### Client di rete Microsoft
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per i computer client di rete Microsoft. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.10 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – client di rete Microsoft**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Client di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal server)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)
  
Questa impostazione di criterio determina se il componente client SMB deve richiedere la firma del pacchetto. Se si attiva questa impostazione di criterio, si impedisce al computer client di rete Microsoft di comunicare con un server di rete Microsoft, a meno che il server non accetti di firmare i pacchetti SMB. Negli ambienti misti con client precedenti è importante impostare questa opzione su **Disabilitato**, perché questi computer non possono eseguire l’autenticazione o accedere ai controller di dominio. È possibile, tuttavia, utilizzare questa impostazione in ambienti con Windows 2000 o versioni successive.
  
L'impostazione **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** è configurata su **Abilitato** per i computer di entrambi gli ambienti trattati in questo capitolo.
  
**Nota**: quando questa impostazione di criterio è attivata su computer Windows XP che si connettono a condivisioni di file o di stampa su server remoti, è importante che su di essi l'impostazione sia sincronizzata con quella correlata **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)**. Per ulteriori dettagli su queste impostazioni, vedere la sezione "Client e server di rete Microsoft: aggiungi firma digitale alle comunicazioni (quattro impostazioni correlate)" nel Capitolo 5 della guida correlata [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), che è possibile scaricare all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
##### Client di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal server)
  
questa impostazione di criterio determina se il client SMB tenterà di negoziare la firma del pacchetto SMB. L'implementazione della firma digitale nelle reti Windows facilita la prevenzione del dirottamento delle sessioni. Se questa impostazione di criterio viene attivata, il Client di rete Microsoft utilizzerà la firma soltanto se il server con cui comunica accetta la comunicazione con firma digitale.
  
L'impostazione **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
**Nota**: attivare questa impostazione di criterio sui client SMB nella rete per renderli pienamente validi per la firma del pacchetto con tutti i client e i server nell'ambiente.
  
##### Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi
  
Disattivare questa impostazione di criterio per impedire al redirector di SMB di inviare password non crittografate durante l'autenticazione nei server SMB non Microsoft che non supportano la crittografia di password. Microsoft consiglia di disattivare questa impostazione di criterio a meno che non vi siano valide ragioni aziendali per attivarla. Se questa impostazione di criterio è attivata, attraverso la rete sarà consentito l'uso di password non crittografate.
  
L'impostazione **Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi** è configurata su **Disabilitato** per i due ambienti trattati nel presente capitolo.
  
#### Server di rete Microsoft
  
La tabella seguente riassume le impostazioni delle Opzioni di protezione consigliate per i server di rete Microsoft. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.11 Raccomandazioni relative alle impostazioni delle Opzioni di protezione – Server di rete Microsoft**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal client)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione
  
Questa impostazione di criterio consente di specificare il periodo di inattività continua che deve trascorrere in una sessione SMB prima che avvenga la disconnessione a causa dell'inattività. Gli amministratori possono utilizzare questa impostazione per controllare quando un computer deve sospendere una sessione SMB inattiva. Se l'attività del client riprende, la sessione viene automaticamente ristabilita.
  
L'impostazione **Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione** è configurata su **Abilitato** per **15 minuti** in entrambi gli ambienti trattati nel presente capitolo.
  
##### Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)
  
questa impostazione di criterio determina se il servizio SMB sul lato server è necessario per l'esecuzione della firma del pacchetto SMB. Abilitare questa impostazione di criterio in un ambiente misto, al fine di impedire ai client downstream di utilizzare la workstation come server di rete.
  
L'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** è impostata su **Abilitato** per entrambi gli ambienti trattati in questo capitolo.
  
##### Server di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal client)
  
Questa impostazione di criterio determina se il servizio SMB sul lato server sia in grado di firmare i pacchetti SMB quando richiesto da un client che tenta di stabilire una connessione. Se dal client non proviene alcuna richiesta di firma, sarà possibile effettuare una connessione senza firma se l'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** non è abilitata.
  
L'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal client)** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
**Nota**: attivare questo criterio sui client SMB nella rete per renderli pienamente validi per la firma del pacchetto con tutti i client e i server nell'ambiente.
  
#### Accesso di rete
  
La tabella seguente riassume le impostazioni delle opzioni di protezione consigliate per l'accesso di rete. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.12 Raccomandazioni sull'impostazione delle opzioni di protezione – Accesso di rete**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso di rete: consenti conversione anonima SID/NOME</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso di rete: non consentire l'enumerazione anonima degli account SAM</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso di rete: consenti l'accesso libero agli utenti anonimi</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso di rete: named pipe a cui è possibile accedere in modo anonimo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">* Consultare la seguente descrizione dell'impostazione per l'elenco completo dei named pipe</td>
<td style="border:1px solid black;">* Consultare la seguente descrizione dell'impostazione per l'elenco completo dei named pipe</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto.</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">* Consultare la seguente descrizione dell'impostazione per l'elenco completo dei percorsi</td>
<td style="border:1px solid black;">* Consultare la seguente descrizione dell'impostazione per l'elenco completo dei percorsi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">comcfg, dfs$</td>
<td style="border:1px solid black;">comcfg, dfs$</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso di rete: modello di condivisione e protezione per gli account locali</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione di se stessi</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione di se stessi</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione di se stessi</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione di se stessi</td>
</tr>
</tbody>
</table>
  
##### Accesso di rete: consenti conversione anonima SID/NOME
  
Questa impostazione di criterio permette di stabilire se un utente anonimo possa chiedere attributi identificatore di protezione (SID) per un altro utente o utilizzare un SID per ottenere il nome utente corrispondente. Disattivare questa impostazione di criterio per evitare che utenti non autenticati ottengano nomi utente associati ai rispettivi SID.
  
L'impostazione **Accesso di rete: consenti conversione anonima SID/nome** è configurata su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Accesso di rete: non consentire l'enumerazione anonima degli account SAM
  
Questa impostazione di criterio controlla la capacità di utenti anonimi di enumerare gli account in Gestione account di protezione (SAM). Se questa impostazione di criterio viene abilitata, gli utenti con connessioni anonime non saranno in grado di enumerare i nomi utente degli account di dominio sulle workstation nell'ambiente. Consente inoltre ulteriori restrizioni sulle connessioni anonime.
  
L' impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM
  
Questa impostazione di criterio controlla la capacità degli utenti anonimi di enumerare le condivisioni e gli account SAM. Se questa impostazione di criterio viene abilitata, gli utenti anonimi non saranno in grado di enumerare i nomi utente degli account di dominio e i nomi di condivisione di rete sulle workstation nell'ambiente.
  
L' impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete
  
Questa impostazione di criterio controlla l'archiviazione delle credenziali di autenticazione e delle password nel sistema locale.
  
L' impostazione **Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Accesso di rete: consenti l'accesso libero agli utenti anonimi
  
Questa impostazione di criterio determina le autorizzazioni aggiuntive da assegnare per le connessioni anonime al computer. Se questa impostazione di criterio viene abilitata, gli utenti Windows anonimi possono svolgere determinate attività, ad esempio l'enumerazione dei nomi degli account di dominio e delle condivisioni di rete. Un utente non autorizzato potrebbe elencare in modo anonimo i nomi degli account e le risorse condivise e utilizzare queste informazioni per cercare di scoprire le password o per eseguire altri attacchi.
  
Di conseguenza, l'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi** è configurata su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Accesso di rete: named pipe a cui è possibile accedere in modo anonimo
  
Questa impostazione di criterio determina le sessioni di comunicazione (pipe) a cui verranno assegnati gli attributi e le autorizzazioni che consentono l’accesso anonimo.
  
Per l'ambiente EC, l'impostazione **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo** è configurata su **Non definito.** Tuttavia, per l'ambiente SSLF, sono applicati i seguenti valori predefiniti:
  
-   COMNAP
  
-   COMNODE
  
-   SQL\\QUERY
  
-   SPOOLSS
  
-   LLSRPC
  
-   Browser
  
##### Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto.
  
Questa impostazione di criterio determina i percorsi del Registro di sistema che saranno accessibili dopo aver fatto riferimento alla chiave WinReg per stabilire le autorizzazioni di accesso a tali percorsi.
  
Per l'ambiente EC, l' impostazione **Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto** è configurata su **Non definito.** Tuttavia, per l'ambiente SSLF, sono applicati i seguenti valori predefiniti:
  
-   System\\CurrentControlSet\\Control\\ProductOptions
  
-   System\\CurrentControlSet\\Control\\Print\\Printers
  
-   System\\CurrentControlSet\\Control\\Server Applications
  
-   System\\CurrentControlSet\\Control\\ContentIndex
  
-   System\\CurrentControlSet\\Control\\Terminal Server
  
-   System\\CurrentControlSet\\Control\\Terminal Server\\UserConfig
  
-   System\\CurrentControlSet\\Control\\Terminal Server\\DefaultUserConfiguration
  
-   System\\CurrentControlSet\\Services\\Eventlog
  
-   Software\\Microsoft\\OLAP Server
  
-   Software\\Microsoft\\Windows NT\\CurrentVersion
  
##### Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo
  
Questa impostazione di criterio determina a quali condivisioni possono accedere gli utenti anonimi. La configurazione predefinita per l'impostazione di criterio ha un effetto limitato, poiché tutti gli utenti devono essere autenticati per poter accedere alle risorse condivise del server.
  
Per l'ambiente EC, l' impostazione **Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo** è configurata su **Non definito**. Tuttavia, verificare che, per l'ambiente SSLF, questa impostazione sia configurata su **comcfg, il dfs$**.
  
**Nota**: può essere estremamente pericoloso aggiungere ulteriori condivisioni a questa impostazione Criteri di gruppo. Qualsiasi condivisione elencata è accessibile a tutti gli utenti della rete e ciò potrebbe provocare l'esposizione o il danneggiamento di dati riservati.
  
##### Accesso di rete: modello di condivisione e protezione per gli account locali
  
Questa impostazione di criterio determina la modalità di autenticazione degli accessi in rete che utilizzano account locali. L'opzione **Classico** consente un controllo preciso dell'accesso alle risorse, compresa la possibilità di assegnare tipi di accesso differenti a utenti diversi per la stessa risorsa. L'impostazione **Solo Guest** consente di trattare tutti gli utenti in modo uguale. In questo contesto, tutti gli utenti si autenticano come **Solo Guest** per ricevere lo stesso livello di accesso a una determinata risorsa.
  
Quindi, l'impostazione **Modello di condivisione e protezione per gli account locali** utilizza l'opzione predefinita **Classico** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Protezione di rete
  
La tabella seguente riassume le impostazioni delle opzioni di protezione consigliate per la protezione di rete. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.12 Raccomandazioni sull'impostazione delle opzioni di protezione – Protezione di rete**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protezione di rete: livello di autenticazione di LAN Manager</td>
<td style="border:1px solid black;">Invia solo risposta NTLMv2\Rifiuta LM</td>
<td style="border:1px solid black;">Invia solo risposta NTLMv2\Rifiuta LM</td>
<td style="border:1px solid black;">Invia solo risposte NTLMv2\Rifiuta LM e NTLM</td>
<td style="border:1px solid black;">Invia solo risposte NTLMv2\Rifiuta LM e NTLM</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione di rete: requisiti per la firma client LDAP</td>
<td style="border:1px solid black;">Negozia firma</td>
<td style="border:1px solid black;">Negozia firma</td>
<td style="border:1px solid black;">Negozia firma</td>
<td style="border:1px solid black;">Negozia firma</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
<td style="border:1px solid black;">Richiedi confidenzialità messaggio, Richiedi integrità messaggio, Richiedi protezione sessione NTLMv2<br />
, Richiedi crittografia 128 bit</td>
</tr>
</tbody>
</table>
 

##### Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password

Questa impostazione di protezione determina se il valore hash di LAN Manager (LM) per la nuova password verrà memorizzato al successivo cambio di password. L'hash di Lan Manager è relativamente debole e vulnerabile agli attacchi, rispetto all'hash di Windows NT crittograficamente più forte.

Per questa ragione, l'impostazione **Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password** è configurata su **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.

**Nota**: quando questa impostazione è attivata, sistemi operativi precedenti molto vecchi e alcune applicazioni di terze parti potrebbero non funzionare. Inoltre, alla sua attivazione, è necessario cambiare la password su tutti gli account.

##### Protezione di rete: livello di autenticazione di LAN Manager

Permette di specificare il tipo di autenticazione In attesa/Risposta per gli accessi in rete con client non Windows 2000 e Window XP Professional. Autenticazione di LAN Manager (LM) è il metodo meno sicuro; consente di violare le password crittografate poiché facilmente intercettabili sulla rete. NT LAN Manager (NTLM) è più sicuro. NTLMv2 è una versione più affidabile di NTLM disponibile in Windows  XP Professional, Windows 2000 e Windows NT 4.0 Service Pack 4 (SP4) e versioni successive. NTLMv2 è disponibile anche per Windows 95 e Windows 98 assieme a Directory Services Client opzionale.

Microsoft consiglia di configurare questa impostazione di criterio sul massimo livello di autenticazione possibile per l'ambiente. Negli ambienti che eseguono Windows 2000 Server o Windows Server 2003 con workstation Windows XP Professional, configurare questa impostazione di criterio sull'opzione **Invia solo risposte NTLMv2\\Rifiuta LM e NTLM** per la protezione più elevata.

Per l'ambiente EC, l'impostazione **Protezione di rete: livello di autenticazione di LAN Manager** è configurata su **Invia solo risposta NTLMv2\\Rifiuta LM e NTLM**. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata sull'opzione più restrittiva **Invia solo risposta NTLMv2\\Rifiuta LM e NTLM**.

##### Protezione di rete: requisiti per la firma client LDAP

Questa impostazione di criterio determina il livello di firma dei dati che viene richiesto per conto dei client che emettono richieste di binding LDAP. Poiché il traffico di rete privo di firma è esposto ad attacchi man-in-the-middle, un pirata informatico potrebbe indurre un server LDAP a prendere decisioni sulla base di query false dal client LDAP.

Quindi, il valore dell'impostazione **Protezione di rete: requisiti per la firma client LDAP** è configurato su **Negozia firma** per entrambi gli ambienti trattati nel presente capitolo.

##### Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)

Questa impostazione di criterio determina gli standard minimi di protezione delle comunicazioni fra le applicazioni per i client. Le opzioni per questa impostazione di criterio sono:

-   Richiedi integrità messaggio

-   Richiedi confidenzialità messaggio

-   Richiedi protezione sessione NTLMv2

-   Richiedi crittografia a 128 bit

Se tutti i computer in rete supportano NTLMv2 e la crittografia a 128 bit (ad esempio, Windows XP Professional SP2 e Windows Server 2003 SP1), per garantire la massima protezione è possibile selezionare tutte e quattro le opzioni.

Per l'impostazione **Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)** sono abilitate tutte e quattro le impostazioni in entrambi gli ambienti trattati nel presente capitolo.

##### Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)

Questa impostazione di criterio è simile alla precedente ma interessa il lato server della comunicazione con le applicazioni. Le opzioni per l'impostazione sono le stesse:

-   Richiedi integrità messaggio

-   Richiedi confidenzialità messaggio

-   Richiedi protezione sessione NTLMv2

-   Richiedi crittografia a 128 bit

Se tutti i computer in rete supportano NTLMv2 e la crittografia a 128 bit (ad esempio, Windows XP Professional SP2 e Windows Server 2003 SP1), per la massima protezione è possibile selezionare tutte e quattro le opzioni.

Per l'impostazione **Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)** tutte e quattro le impostazioni sono attivate in entrambi gli ambienti trattati nel presente capitolo.

#### Console di ripristino di emergenza

La tabella seguente riassume le impostazioni delle opzioni di protezione consigliate per la console di ripristino di emergenza. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.

**La tabella 3.14 Raccomandazioni sull'impostazione delle opzioni di protezione – Console di ripristino di emergenza**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Console di ripristino di emergenza: consente l'accesso di amministrazione automatico</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Console di ripristino di emergenza: consente l'accesso di amministrazione automatico
  
La console di ripristino di emergenza è un ambiente della riga di comando utilizzato per il ripristino in seguito a problemi di sistema. Se si abilita questa impostazione di criterio, l'account Administrator ha accesso automatico alla console di ripristino di emergenza quando questa impostazione viene richiamata durante l'avvio. Microsoft consiglia di disattivare questa impostazione di criterio, in modo da richiedere agli amministratori l'immissione della password per accedere alla console di ripristino di emergenza.
  
L'impostazione **Console di ripristino di emergenza: consente l'accesso di amministrazione automatico** è configurata su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
##### Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle
  
Questa impostazione di criterio rende disponibile il comando SET della Console di ripristino di emergenza, che consente di impostare le seguenti variabili di ambiente della console:
  
-   **AllowWildCards**. abilita il supporto dei caratteri jolly per alcuni comandi, ad esempio per il comando DEL.
  
-   **AllowAllPaths**. consente l'accesso a tutti i file e a tutte le cartelle del computer.
  
-   **AllowRemovableMedia**. consente di copiare i file su supporti rimovibili, ad esempio su dischi floppy.
  
-   **NoCopyPrompt**. Non viene richiesta conferma per la sovrascrittura di file
  
L' impostazione **Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle**, per l'ambiente EC è configurata su **Non definito**. Tuttavia, per garantire la massima protezione, questa impostazione è configurata su **Disabilitato** per l'ambiente SSLF.
  
#### Arresto del sistema
  
La tabella seguente riassume le raccomandazioni sull'impostazione delle opzioni di protezione dell'arresto del sistema. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.6 Raccomandazioni sull'impostazione delle opzioni di protezione – Arresto del sistema**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Arresto del sistema: cancella il file di paging della memoria virtuale</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso
  
Questa impostazione di criterio determina se un computer può essere arrestato quando un utente non è connesso ad esso. Se questa impostazione di criterio è attivata, il comando di arresto del sistema è disponibile sulla schermata di accesso di Windows. Microsoft consiglia di disattivare questa impostazione di criterio per limitare la capacità di arrestare il computer agli utenti con credenziali su di esso.
  
L'impostazione **Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso** è configurata su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
##### Arresto del sistema: cancella il file di paging della memoria virtuale
  
Questa impostazione di criterio determina se il contenuto del file di paging della memoria virtuale deve essere cancellato all’arresto del sistema. Se questa impostazione è abilitata, il contenuto del file di paging del sistema viene cancellato ogni volta che il sistema viene arrestato normalmente. Se si abilita questa impostazione, nei computer portatili in cui è disabilitata la sospensione viene cancellato anche il contenuto del file di sospensione (Hiberfil.sys). Richiederà più tempo per arrestare e riavviare il server, specialmente nel caso di server con file di paging di notevoli dimensioni.
  
Per questi motivi, l'impostazione **Arresto del sistema: cancella il file di paging della memoria virtuale** è configurata su **Disabilitato** per tutti i computer in entrambi gli ambienti trattati nel presente capitolo.
  
#### Crittografia di sistema
  
La tabella seguente riassume le impostazioni delle opzioni di protezione consigliate per la crittografia di sistema. Ulteriori informazioni sono riportate dopo la tabella.
  
**Tabella 3.16 Raccomandazioni sull'impostazione delle opzioni di protezione – Crittografia di sistema**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma
  
Questa impostazione di criterio determina se il provider di protezione TL/SS (Transport Layer Security/Secure Sockets Layer) supporta solo il pacchetto di crittografia TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA. Nonostante questa impostazione di criterio aumenti la protezione, la maggior parte dei siti Web pubblici che sono protetti da TLS o SSL non supporta questi algoritmi. I computer client su cui è attivata questa impostazione di criterio non potranno inoltre connettersi ai Servizi terminal sui server che non sono configurati per l'utilizzo di algoritmi FIPS compatibili.
  
L'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma** è configurata su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
**Nota**: se si abilita questa impostazione di criterio, le prestazioni del computer saranno più lente in quanto il processo 3DES viene eseguito tre volte su ciascun blocco di dati nel file. Questa impostazione di criterio deve essere attivata solo se è necessario che l'organizzazione sia conforme a FIPS.
  
#### Oggetti di sistema
  
La tabella seguente riassume le impostazioni delle opzioni di protezione consigliate per gli oggetti di sistema. Sono disponibili ulteriori informazioni nelle sottosezioni che seguono la tabella.
  
**Tabella 3.17 Raccomandazioni sull'impostazione delle opzioni di protezione – Oggetti di sistema**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators</td>
<td style="border:1px solid black;">Creatore oggetto</td>
<td style="border:1px solid black;">Creatore oggetto</td>
<td style="border:1px solid black;">Creatore oggetto</td>
<td style="border:1px solid black;">Creatore oggetto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema globale</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators
  
Questa impostazione di criterio consente di stabilire se il proprietario predefinito dei nuovi oggetti di sistema è il gruppo **Administrators** o il gruppo **Creatore oggetto**.
  
Ai fini di una maggiore responsabilizzazione, l'impostazione **Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators** è configurata sul gruppo di **Creatore oggetto** per i due ambienti trattati nel presente capitolo.
  
##### Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows
  
Questa impostazione di criterio determina se per tutti i sottosistemi deve essere ignorata la differenza tra maiuscole e minuscole. Nel sottosistema Microsoft Win32 viene ignorata la differenza tra maiuscole e minuscole. Tuttavia, il kernel supporta la differenziazione tra maiuscole e minuscole per altri sottosistemi, quali POSIX (Portable Operating System Interface for UNIX). Dal momento che in Windows non viene fatta distinzione tra maiuscole e minuscole (mentre il sottosistema POSIX distingue tra maiuscole e minuscole), non applicando questa impostazione un utente del sottosistema POSIX potrebbe creare un file con lo stesso nome di un altro file, ma con un uso diverso di maiuscole e minuscole. Una situazione del genere può bloccare un altro utente che accede a questi file con i normali strumenti Win32, perché solo uno dei file sarebbe disponibile.
  
Per garantire uniformità per i nomi dei file, l'impostazione **Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows** è configurata su **Non definito** per l'ambiente EC e su **Abilitato** per l'ambiente SSLF.
  
##### Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema globale
  
Determina la forza del DACL (Discretionary Access Control List) predefinito per gli oggetti di sistema. Questa opzione contribuisce a proteggere gli oggetti che possono essere posizionati e condivisi dai processi e la configurazione predefinita rende più potente l'elenco DACL, consentendo agli utenti che non sono amministratori di leggere gli oggetti condivisi, ma non di modificare quelli che sono stati creati da altri utenti.
  
Quindi, l'impostazione **Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema globale** (ad esempio, i collegamenti simbolici) è configurata sull'impostazione predefinita **Abilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione di Registro eventi
  
Nel Registro eventi vengono registrati gli eventi del sistema, mentre nel Registro di protezione vengono registrati gli eventi di controllo. Il contenitore Registro eventi di Criteri di gruppo viene utilizzato per definire gli attributi relativi ai registri eventi per le applicazioni, la protezione e il sistema, quali la dimensione massima del registro, i diritti di accesso e le impostazioni e i criteri di gestione. Le impostazioni dei registri eventi per le applicazioni, la protezione e il sistema sono configurate nel criterio MSBP (member server baseline policy) e vengono applicate a tutti i server membro del dominio.
  
È possibile configurare le impostazioni per il Registro eventi nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Registro eventi**
  
In questa sezione sono riportati i dettagli sulle impostazioni richieste per gli ambienti trattati nel presente capitolo. Per un riepilogo delle impostazioni necessarie indicate in questa sezione, vedere la cartella di lavoro Microsoft Excel "Impostazioni della Guida per la protezione di Windows XP". Per informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata in questa sezione, fare riferimento alla guida correlata [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159. La guida correlata contiene inoltre informazioni dettagliate sulla possibilità di perdita di dati dei registri degli eventi quando le dimensioni di registro sono impostate su valori molto ampi.
  
Nella tabella seguente viene fornito un riepilogo delle impostazioni consigliate da applicare al registro eventi protezione per client desktop e portatili nei due ambienti trattati nel presente capitolo—ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality) Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
**Tabella 3.18 Raccomandazioni per l'impostazione di protezione di Registro eventi**

 
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
<th>Impostazione</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Dimensione massima registro applicazioni</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dimensione massima registro protezione</td>
<td style="border:1px solid black;">81920 KB</td>
<td style="border:1px solid black;">81920 KB</td>
<td style="border:1px solid black;">81920 KB</td>
<td style="border:1px solid black;">81920 KB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Dimensione massima registro eventi di sistema</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
<td style="border:1px solid black;">16384 KB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro applicazione</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro applicazione</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro eventi di sistema</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri gestione registro applicazione</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri gestione registro protezione</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri gestione registro eventi di sistema</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
<td style="border:1px solid black;">Se necessario</td>
</tr>
</tbody>
</table>
  
#### Dimensione massima registro applicazioni
  
Questa impostazione di criterio specifica la dimensione massima del registro eventi applicazioni, la cui capacità massima è di 4 GB. Tuttavia, queste dimensioni non sono raccomandate a causa del rischio di frammentazione della memoria, che causa prestazioni lente e una registrazione degli eventi non affidabile. I requisiti per la dimensione del registro applicazioni variano a seconda della funzione della piattaforma e della necessità di conservare record degli eventi relativi alle applicazioni.
  
L'impostazione **Dimensione massima registro applicazioni** è configurata su **16384 KB** per tutti i computer nei due ambienti trattati nel presente capitolo.
  
#### Dimensione massima registro protezione
  
Questa impostazione di criterio specifica la dimensione massima del registro eventi di protezione, la cui capacità massima è di 4 GB. Tuttavia, queste dimensioni non sono raccomandate a causa del rischio di frammentazione della memoria, che causa prestazioni lente e una registrazione degli eventi non affidabile. I requisiti per la dimensione del Registro protezione variano a seconda della funzione della piattaforma e della necessità di conservare record degli eventi relativi alle applicazioni.
  
L'impostazione **Dimensione massima registro protezione** è configurata su **81920 KB** per tutti i computer nei due ambienti trattati nel presente capitolo.
  
#### Dimensione massima registro eventi di sistema
  
Questa impostazione di criterio specifica la dimensione massima del Registro eventi sistema, la cui capacità massima è di 4 GB. Tuttavia, queste dimensioni non sono raccomandate a causa del rischio di frammentazione della memoria, che causa prestazioni lente e una registrazione degli eventi non affidabile. I requisiti per la dimensione del registro applicazioni variano a seconda della funzione della piattaforma e della necessità di conservare record degli eventi relativi alle applicazioni.
  
L'impostazione **Dimensione massima del registro eventi di sistema** è configurata su **16384 KB** per tutti i computer nei due ambienti trattati nel presente capitolo.
  
#### Impedisci accesso guest locale al registro applicazione
  
Questa impostazione di criterio determina se ai membri del gruppo Guests deve essere impedito l’accesso al registro eventi applicazioni. Per impostazione predefinita, in Windows Server 2003 l'accesso guest è negato in tutti i sistemi. Pertanto, questa impostazione non ha alcun effetto sui sistemi con configurazioni predefinite. Tuttavia, è considerata una soluzione di protezione avanzata senza effetti collaterali.
  
L' impostazione **Impedisci accesso guest locale al registro applicazione** è configurata su **Abilitato** per i due ambienti trattati nel presente capitolo.
  
#### Impedisci accesso guest locale al registro applicazione
  
Questa impostazione di criterio determina se ai membri del gruppo Guests deve essere impedito l’accesso al registro eventi protezione. Per accedere al registro di protezione un utente deve avere il diritto utente **Gestione file registro di controllo e di protezione** (non definito in questa guida). Pertanto, questa impostazione non ha alcun effetto sui sistemi con configurazioni predefinite. Tuttavia, è considerata una soluzione di protezione avanzata senza effetti collaterali.
  
L' impostazione **Impedisci accesso guest locale al registro di protezione** è configurata su **Abilitato** per i due ambienti trattati nel presente capitolo.
  
#### Impedisci accesso guest locale al registro eventi di sistema
  
Questa impostazione di criterio determina se ai membri del gruppo Guests deve essere impedito l’accesso al registro eventi di sistema. Per impostazione predefinita, in Windows Server 2003 l'accesso guest è negato in tutti i sistemi. Pertanto, questa impostazione non ha alcun effetto sui sistemi con configurazioni predefinite. Tuttavia, è considerata una soluzione di protezione avanzata senza effetti collaterali.
  
L' impostazione **Impedisci accesso guest locale al registro di sistema** è configurata su **Abilitato** per i due ambienti trattati nel presente capitolo.
  
#### Criteri gestione registro applicazione
  
Questa impostazione di criterio determina il metodo di permanenza dei record nel registro applicazioni. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. La sovrascrittura degli eventi quando necessario garantisce che il registro contenga sempre gli eventi più recenti, anche se questa configurazione può causare la perdita dei dati meno recenti.
  
I **Criteri gestione registro applicazione** sono configurati su **Se necessario** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Criteri gestione registro protezione
  
Questa impostazione di criterio determina il metodo di gestione del registro protezione. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. La sovrascrittura degli eventi quando necessario garantisce che il registro contenga sempre gli eventi più recenti, anche se questa configurazione può causare la perdita dei dati meno recenti.
  
I **Criteri gestione registro protezione** sono configurati su **Se necessario** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Criteri gestione registro eventi di sistema
  
Questa impostazione di criterio determina il metodo di permanenza dei record nel registro di sistema. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. La sovrascrittura degli eventi quando necessario garantisce che il registro contenga sempre gli eventi più recenti, anche se questa configurazione può causare la perdita dei dati meno recenti.
  
I **Criteri gestione registro eventi di sistema** sono configurati su **Se necessario** per entrambi gli ambienti trattati nel presente capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Gruppi con restrizioni
  
L'impostazione Gruppi con restrizioni consente di gestire l'appartenenza dei gruppi in Windows XP Professional attraverso i Criteri di gruppo di Active Directory. In primo luogo, esaminare le esigenze dell'organizzazione per stabilire i gruppi a cui imporre le restrizioni. Ai fini di questa guida, i gruppi **Power Users** e **Backup Operators** sono limitati in entrambi gli ambienti ma, per l'ambiente SSLF, è limitato solamente il gruppo **Utenti desktop remoto**. Sebbene i membri del gruppo **Power Users** e **Backup Operators** abbiano un accesso al sistema più limitato rispetto a quelli del gruppo **Administrators,** possono tuttavia accedere al sistema con notevoli capacità.
  
**Nota:** se l'organizzazione utilizza uno qualsiasi di questi gruppi, controllare attentamente la loro appartenenza e non implementare le istruzioni relative all'impostazione dei gruppi con restrizioni. Se l'organizzazione aggiunge utenti al gruppo Power Users, è possibile implementare le autorizzazioni di file system opzionali descritte nella sezione "Protezione del File System" più avanti nel presente capitolo.
  
**Tabella 3.19 Raccomandazioni di Gruppi con Restrizioni**

 
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
<th>Gruppo locale</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Operatori backup</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Power Users</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Utenti desktop remoto</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Nessun membro</td>
<td style="border:1px solid black;">Nessun membro</td>
</tr>
</tbody>
</table>
  
È possibile configurare le impostazioni dei Gruppi con restrizioni nella seguente posizione, utilizzando l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Gruppi con restrizioni\\**
  
Gli amministratori possono configurare i gruppi con restrizioni per un oggetto Criteri di gruppo (GPO) aggiungendo il gruppo desiderato direttamente al nodo **Gruppi con restrizioni** dello spazio dei nomi del GPO.
  
Quando viene posta la restrizione su un gruppo, si ha l'opzione di definire i suoi membri e altri gruppi a cui esso appartiene. Se i membri del gruppo non vengono specificati, il gruppo rimane con tutte le restrizioni. Solo utilizzando i modelli di protezione è possibile imporre restrizioni ai gruppi.
  
**Per visualizzare o modificare l'impostazione Gruppi con restrizioni**
  
1.  Aprire la console Modelli di protezione.
  
    **Nota:** la console Modelli di protezione non è inclusa per impostazione predefinita nel menu Strumenti di amministrazione. Per aggiungerla, avviare la Microsoft Management Console (mmc.exe) e aggiungere il componente aggiuntivo Modelli di protezione.
  
2.  Fare doppio clic sulla directory del file di configurazione, quindi sul file di configurazione.
  
3.  Fare doppio clic sulla voce **Gruppi con restrizioni**.
  
4.  Fare clic con il tasto destro su **Gruppi con restrizioni**, quindi selezionare **Aggiungi gruppo.**
  
5.  Fare clic sul pulsante **Sfoglia**, quindi su **Percorsi**, selezionare il percorso da esplorare e scegliere **OK**.
  
    **Nota:** in genere questa procedura pone al primo posto della lista un computer locale.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare** immettere il nome del gruppo e fare clic sul pulsante **Controlla nomi**.
  
    – oppure –
  
    Fare clic sul pulsante **Avanzate**, quindi su **Trova** per elencare tutti i gruppi disponibili.
  
7.  Selezionare il gruppo a cui imporre le restrizioni, quindi scegliere **OK**.
  
8.  Scegliere **OK** per chiudere la finestra di dialogo **Aggiungi gruppi**.
  
In questa guida, le impostazioni sono state rimosse per tutti i membri—utenti e gruppi—dei gruppi Power User e Backup Operators per limitarli completamente in entrambi gli ambienti. Inoltre, per quanto riguarda l'ambiente SSLF, per il gruppo Utenti desktop remoto sono stati rimossi tutti i membri. Microsoft consiglia di limitare tutti i gruppi incorporati che l'organizzazione non ha intenzione di utilizzare.
  
**Nota**: la configurazione di Gruppi con restrizioni, descritta in questa sezione, è molto semplice. Le versioni di Windows XP SP1 o successive, o di Windows Server 2003, supportano ulteriori progetti complessi. Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Aggiornamenti al comportamento Gruppi con restrizioni (Membro di) dei gruppi locali definiti dall'utente](http://support.microsoft.com/default.aspx?kbid=810076)" all'indirizzo http://support.microsoft.com/default.aspx?kbid=810076.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Servizi di sistema
  
Durante l'installazione di Windows XP Professional vengono creati servizi di sistema predefiniti, configurati per l'esecuzione all'avvio del sistema. L'esecuzione di molti di questi servizi non è richiesta per gli ambienti definiti in questo capitolo.
  
Con Windows XP Professional sono disponibili vari servizi opzionali, ad esempio IIS, che nell'installazione predefinita del sistema operativo non vengono installati. È possibile aggiungere questi servizi opzionali a un sistema esistente con Installazione applicazioni nel Pannello di controllo, oppure è possibile creare un'installazione automatica personalizzata di Windows XP Professional.
  
**Importante**: tenere presente che qualsiasi servizio o applicazione è un potenziale punto di attacco. Di conseguenza, è bene disattivare o rimuovere tutti i servizi o i file eseguibili non necessari.
  
È possibile configurare le impostazioni dei servizi di sistema nella seguente posizione nell'Editor criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Servizi sistema**
  
Un amministratore può impostare la modalità di avvio dei servizi e modificare le impostazioni di protezione per ciascuno di essi.
  
**Importante**: le versioni degli strumenti grafici che è possibile utilizzare per modificare i servizi contenuti nelle versioni precedenti a Windows 2003 del sistema operativo Windows, durante la configurazione di qualsiasi proprietà di un servizio, applicano in modo automatico le autorizzazioni a ciascun servizio. Strumenti quali l'Editore dell'oggetto Criteri di gruppo e lo snap-in Modelli di protezione di MMC per applicare tali autorizzazioni utilizzano il DLL dell'Editor di configurazione della protezione. Se le autorizzazioni predefinite sono modificate, molti servizi subiranno problemi di vario tipo. Microsoft consiglia di non modificare le autorizzazioni sui servizi inclusi in Windows XP o Windows Server 2003, perché le autorizzazioni predefinite sono già abbastanza restrittive.  
La versione di Windows Server 2003 del DLL di Editor di configurazione della protezione non obbliga a configurare le autorizzazioni quando le proprietà di un servizio vengono modificate. Per ulteriori informazioni vedere la guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159)*,* disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
Nella tabella seguente viene fornito un riepilogo delle impostazioni di servizi sistema consigliate per i client desktop e portatili nei due ambienti trattati nel presente capitolo—ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality). Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
**Tabella 3.20 Raccomandazioni di Impostazione di Protezione di Servizi di Sistema**
  
<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del servizio</th>
<th>Nome visualizzato</th>
<th>Desktop EC</th>
<th>Computer portatile EC</th>
<th>Desktop SSLF</th>
<th>Computer portatile SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ClipSrv</td>
<td style="border:1px solid black;">Cartella Appunti</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Browser</td>
<td style="border:1px solid black;">Browser di computer</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Fax</td>
<td style="border:1px solid black;">Fax</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSFtpsvr</td>
<td style="border:1px solid black;">Pubblicazione FTP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IISADMIN</td>
<td style="border:1px solid black;">Ammin. IIS</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">cisvc</td>
<td style="border:1px solid black;">Servizio di indicizzazione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Messenger</td>
<td style="border:1px solid black;">Messenger</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">mnmsrvc</td>
<td style="border:1px solid black;">Condivisione desktop remoto di NetMeeting</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RDSessMgr</td>
<td style="border:1px solid black;">Gestione sessione di assistenza mediante desktop remoto</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RemoteAccess</td>
<td style="border:1px solid black;">Routing e Accesso remoto</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SNMP</td>
<td style="border:1px solid black;">Servizio SNMP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SNMPTRAP</td>
<td style="border:1px solid black;">Servizio Trap SNMP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SSDPSrv</td>
<td style="border:1px solid black;">Servizio di rilevamento SSDP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Schedule</td>
<td style="border:1px solid black;">Utilità di pianificazione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TlntSvr</td>
<td style="border:1px solid black;">Telnet</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TermService</td>
<td style="border:1px solid black;">Servizi terminal</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Upnphost</td>
<td style="border:1px solid black;">Host di periferiche Plug and Play universali</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">W3SVC</td>
<td style="border:1px solid black;">Pubblicazione sul Web</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
#### Avvisi
  
Questo servizio notifica avvisi amministrativi agli utenti e ai computer selezionati. È possibile utilizzare il servizio per inviare messaggi di avviso agli utenti specificati connessi alla rete.
  
Il servizio **Avvisi** è configurato su **Disabilitato** per evitare che le informazioni vengano inviate in rete. Questa configurazione assicura una maggiore protezione per entrambi gli ambienti trattati nel presente capitolo.
  
**Nota**: se questo servizio viene disabilitato, la funzionalità dei sistemi di messaggi di avviso dei gruppi di continuità (UPS) potrebbe subire effetti negativi.
  
#### Cartella Appunti
  
Consente al Visualizzatore Cartella Appunti di creare e condividere "pagine" di dati visualizzabili da computer remoti. Questo servizio dipende dal servizio Network Dynamic Data Exchange (NetDDE) per la creazione delle condivisioni del file reale a cui gli altri computer possono connettersi; l'applicazione **Cartella Appunti** e il servizio consentono di creare le pagine di dati da condividere. Qualsiasi servizio che dipende esplicitamente da questo non sarà in grado di operare. Tuttavia, è possibile utilizzare Clipbrd.exe per visualizzare gli Appunti locali, in cui sono memorizzati i dati quando un utente seleziona il testo e successivamente fa clic su **Copia** del menu **Modifica** o preme CTRL+C.
  
Il servizio **Cartella Appunti** è configurato su **Disabilitato** per assicurare una maggiore protezione per entrambi gli ambienti trattati nel presente capitolo.
  
#### Browser di computer
  
Gestisce un elenco aggiornato dei computer in rete, che fornisce ai programmi che lo richiedono. Il servizio viene utilizzato dai computer basati su Windows per visualizzare risorse e domini di rete.
  
Per garantire una maggiore protezione, il servizio **Browser di Computer** è impostato su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
#### Fax
  
Servizio compatibile Telephony API (TAPI), fornisce funzionalità fax ai client. Questo servizio consente agli utenti di inviare e ricevere fax dalle applicazioni desktop, utilizzando una periferica fax locale o condivisa in rete.
  
Il servizio **Fax** è impostato su **Non definito** per i computer nell'ambiente EC. Nell'ambiente SSLF viene invece impostato su **Disabilitato** per garantire una maggiore protezione.
  
#### Pubblicazione FTP
  
Tramite lo snap-in IIS, questo servizio offre la connettività e la funzionalità di amministrazione. Microsoft consiglia di non installare questo servizio sui client Windows XP presenti nell'ambiente a meno che non sia un servizio necessario per l'organizzazione.
  
Il servizio **Pubblicazione FTP** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Ammin. IIS
  
Il servizio consente l'amministrazione dei componenti IIS, ad esempio FTP, pool di applicazioni, siti Web ed estensioni dei servizi Web. Disattivare questo servizio per impedire agli utenti di eseguire siti Web o FTP dai propri computer, poiché queste funzioni non sono necessarie nella maggior parte dei client con Windows XP.
  
Il servizio **Ammin. IIS** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Servizio di indicizzazione
  
Questo servizio indicizza contenuti e proprietà di file in computer locali e remoti e consente di accedere rapidamente ai file tramite un linguaggio di query flessibile. Il servizio consente inoltre di cercare rapidamente documenti in computer locali e remoti e mette a disposizione un indice di ricerca per contenuti condivisi sul Web.
  
Il servizio **Servizio di indicizzazione** è impostato su **Non definito** per i computer nell'ambiente EC. Nell'ambiente SSLF viene invece impostato su **Disabilitato** per garantire una maggiore protezione.
  
#### Messenger
  
Il servizio trasmette e invia messaggi del servizio **Avvisi** fra client e server. Questo servizio non è correlato con Windows Messenger o MSN Messenger e non è richiesto per i computer client con Windows XP.
  
Per questo motivo, il servizio **Messenger** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Condivisione desktop remoto di NetMeeting
  
Questo servizio consente a un utente autorizzato di accedere a un client da una postazione remota tramite Microsoft NetMeeting in una Intranet aziendale. Questo servizio deve essere esplicitamente abilitato in NetMeeting. È possibile disabilitare questo servizio in NetMeeting, interromperlo dall'icona nella barra delle applicazioni di Windows o disattivarlo in Criteri di gruppo configurando l'impostazione di disabilitazione della condivisione desktop remoto, definita nel Capitolo 4, "Modelli amministrativi per Windows XP". Microsoft consiglia di disattivare questo servizio per impedire l'accesso ai client da postazioni remote.
  
Il servizio **Condivisione desktop remoto di NetMeeting** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Gestione sessione di assistenza mediante desktop remoto
  
Questo servizio gestisce e controlla la funzionalità di assistenza remota disponibile nell’applicazione Guida in linea e supporto tecnico (helpctr.exe).
  
Il servizio **Gestione sessione di assistenza mediante desktop remoto** è configurato su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
#### Routing e Accesso remoto
  
Questo servizio assicura servizi di routing multiprotocollo LAN a LAN, LAN a WAN, VPN e NAT. Questo servizio include inoltre servizi di accesso basati su connessioni remote e VPN.
  
Il servizio **Routing e Accesso remoto** è configurato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Servizio SNMP
  
Il servizio consente alle richieste SNMP in ingresso di essere servite dal computer locale. **Il Servizio SNMP** include agenti che controllano l'attività nelle periferiche di rete e inviano rapporti alla workstation della console di rete.
  
Il **Servizio SNMP** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Servizio Trap SNMP
  
Questo servizio riceve messaggi trap generati da agenti SNMP locali o remoti e li inoltra ai programmi di gestione SNMP in esecuzione nel computer. Se viene configurato per un agente, **questo servizio** genera messaggi trap nel caso in cui si verifichino eventi specifici. Tali messaggi vengono inviati a una destinazione trap.
  
Il **Servizio Trap SNMP** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Servizio di rilevamento SSDP
  
Questo servizio offre l'Host Plug and Play universale e la possibilità di localizzare e identificare i dispositivi di rete UPnP. Se il **Servizio di rilevamento SSDP** viene disabilitato, al sistema sarà impedita la ricerca in rete dei dispositivi UPnP e l'Host Plug and Play universale non sarà in grado di trovare e interagire con i dispositivi UPnP.
  
Il **Servizio di rilevamento SSDP** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Utilità di pianificazione
  
Questo servizio consente di configurare e pianificare l’esecuzione di attività automatiche nel computer. Il servizio effettua il monitoraggio in base ai criteri specificati dall’utente e quando i criteri vengono soddisfatti esegue l'attività pertinente.
  
Il servizio **Utilità di pianificazione** è configurato su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
#### Telnet
  
Il servizio Telnet per Windows permette sessioni di terminale ASCII ai client Telnet. Il servizio supporta due tipi di autenticazione e i seguenti quattro tipi di terminale: ANSI, VT-100, VT-52 e VTNT. Non è necessario nella maggior parte dei client con Windows XP.
  
Il servizio **Telnet** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
#### Servizi terminal
  
Costituisce un ambiente multisessione che consente l'accesso dei client a una sessione virtuale del desktop di Windows e alle applicazioni Windows in esecuzione nel server. In Windows XP, questo servizio consente agli utenti remoti di connettersi in modo interattivo a un computer e visualizzare desktop e applicazioni di computer remoti.
  
Il servizio **Servizi terminal** è configurato su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
#### Host Plug and Play universale
  
Questo servizio supporta la funzionalità Plug and Play peer-to-peer per i dispositivi di rete. La specifica UPnP ha lo scopo di semplificare l'installazione e la gestione di dispositivi e servizi rete. UPnP esegue il rilevamento e il controllo del dispositivo e del servizio attraverso meccanismi di protocollo basati su standard e che non richiedono l'installazione di alcun driver. I dispositivi Plug and Play universali possono configurare automaticamente l'indirizzamento di rete, annunciare la loro presenza su una subnet di rete e consentire lo scambio delle descrizioni del dispositivo e del servizio. Un computer Windows XP può agire come punto di controllo UPnP per individuare e controllare i dispositivi attraverso l'interfaccia Web o dell'applicazione.
  
Il servizio **Plug and Play universale** è configurato su **Non definito** per l'ambiente EC e su **Disabilitato** per l'ambiente SSLF.
  
#### Pubblicazione sul Web
  
Tramite lo snap-in IIS MMC, questo servizio offre la connettività Web e la funzionalità di amministrazione. Il servizio offre servizi HTTP per applicazioni su piattaforma Windows e contiene una funzionalità di gestione dei processi e una funzionalità di gestione della configurazione. Non è necessario nella maggior parte dei client con Windows XP.
  
Il servizio **Pubblicazione sul Web** è impostato su **Disabilitato** per entrambi gli ambienti trattati nel presente capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Altre impostazioni del Registro di sistema
  
Per i file dei modelli di protezione di base sono state create voci per i valori del Registro di sistema che non sono definite nel file del modello amministrativo (.adm) di entrambi gli ambienti di protezione descritti in questo capitolo.
  
Queste impostazioni sono incorporate nei modelli di protezione (nella sezione "Opzioni di protezione") e consentono di automatizzarne l'implementazione. Se il criterio viene rimosso, queste impostazioni non vengono rimosse automaticamente insieme ad esso, ma devono essere modificate manualmente, utilizzando uno strumento di modifica del Registro di sistema, come Regedt32.exe.
  
In questa guida vengono trattate le impostazioni supplementari aggiunte all'Editor di configurazione della protezione (SCE) modificando il file sceregvl.inf (nella cartella **%windir%\\inf**) e registrando nuovamente il file scecli.dll. Le impostazioni di protezione originali e le impostazioni aggiuntive compaiono in **Criteri locali/Opzioni di protezione** negli snap-in e negli strumenti menzionati in precedenza nel presente capitolo. È necessario aggiornare il file sceregvl.inf e ripetere la registrazione del file scecli.dll, secondo quanto descritto nella sottosezione "Modifica dell'interfaccia utente dell'Editor di configurazione della protezione" riportata di seguito, in tutti i computer in cui si modificano i modelli di protezione e i criteri di gruppo forniti con questa Guida.
  
Nella tabella seguente viene fornito un riepilogo delle raccomandazioni sull'impostazione del registro per i client desktop e portatili nei due ambienti trattati nel presente capitolo, ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality).
  
Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione. Per informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata, fare riferimento alla guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
**Tabella 3.21 Altre impostazioni del Registro di sistema**

 
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
<th>Nome impostazione</th>
<th>Desktop<br />
EC</th>
<th>Computer portatile<br />
EC</th>
<th>Desktop<br />
SSLF</th>
<th>Computer portatile<br />
SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">MSS: (AutoAdminLogon) Enable Automatic Logon (not recommended)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (DisableIPSourceRouting) livello di protezione source routing IP (protezione contro lo spoofing dei pacchetti)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Massima protezione, il source routing è completamente disattivato.</td>
<td style="border:1px solid black;">Massima protezione, il source routing è completamente disattivato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (EnableDeadGWDetect) consente il rilevamento automatico di gateway di rete inattivi (potrebbe provocare DoS)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (EnableICMPRedirect) consente ai reindirizzamenti di ICMP di sostituire le route generate con OSPF</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (Hidden) Hide Computer From the Browse List (not recommended except for highly secure environments)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (KeepAliveTime) frequenza con la quale vengono inviati i pacchetti keep-alive in millisecondi</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">30000 o 5 minuti (consigliato)</td>
<td style="border:1px solid black;">30000 o 5 minuti (consigliato)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering (recommended)</td>
<td style="border:1px solid black;">Multicast, broadcast e ISAKMP sono esenti (suggerito per Windows XP)</td>
<td style="border:1px solid black;">Multicast, broadcast e ISAKMP sono esenti (suggerito per Windows XP)</td>
<td style="border:1px solid black;">Multicast, broadcast e ISAKMP sono esenti (suggerito per Windows XP)</td>
<td style="border:1px solid black;">Multicast, broadcast e ISAKMP sono esenti (suggerito per Windows XP)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (NoDriveTypeAutoRun) Disable Autorun for all drives (recommended)</td>
<td style="border:1px solid black;">255, disabilita esecuzione automatica per tutte le unità</td>
<td style="border:1px solid black;">255, disabilita esecuzione automatica per tutte le unità</td>
<td style="border:1px solid black;">255, disabilita esecuzione automatica per tutte le unità</td>
<td style="border:1px solid black;">255, disabilita esecuzione automatica per tutte le unità</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames (recommended)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (PerformRouterDiscovery) Allow IRDP to detect and configure Default Gateway addresses (could lead to DoS)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (SynAttackProtect) Syn attack protection level (protects against DoS)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Le connessioni raggiungono il timeout più velocemente se viene rilevato un attacco</td>
<td style="border:1px solid black;">Le connessioni raggiungono il timeout più velocemente se viene rilevato un attacco</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (TCPMaxConnectResponseRetransmissions) SYN-ACK retransmissions when a connection request is not acknowledged</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">3 e 6 secondi, connessioni parziali interrotte dopo 21 secondi</td>
<td style="border:1px solid black;">3 e 6 secondi, connessioni parziali interrotte dopo 21 secondi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (TCPMaxDataRetransmissions) How many times unacknowledged data is retransmitted (3 recommended, 5 is default)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">3</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">90</td>
<td style="border:1px solid black;">90</td>
</tr>
</tbody>
</table>
  
#### (AutoAdminLogon) Enable Automatic Logon
  
Al file del modello è stata aggiunta la voce **AutoAdminLogon** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\**. Questa voce è presente come **MSS: (AutoAdminLogon) Enable Automatic Logon (not recommended)** nell'interfaccia utente di SCE.
  
Questa impostazione è separata dalla funzionalità della schermata **Welcome** in Windows XP; se tale funzionalità è disabilitata, questa impostazione non è disabilitata. Se un computer è configurato in modo da effettuare l'accesso automatico, chiunque accede fisicamente al computer può inoltre avere accesso a tutti i dati memorizzati nel computer, comprese le reti a cui il computer è connesso. Inoltre, se l'accesso automatico viene attivato, la password non crittografata è memorizzata nel Registro di sistema e la chiave specifica del Registro di sistema che memorizza tale valore è leggibile in remoto dal gruppo **Authenticated Users**. Per questi motivi, l'impostazione è configurata su **Non definito** per l'ambiente EC e l'impostazione predefinita **Disabilitato** è applicata in modo esplicito per l'ambiente SSLF.
  
Per le ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Come attivare l'accesso automatico in Windows](http://support.microsoft.com/default.aspx?scid=315231)", disponibile online all'indirizzo http://support.microsoft.com/default.aspx?scid=315231.
  
#### (DisableIPSourceRouting) IP source routing protection level
  
Al file del modello è stata aggiunta la voce **DisableIPSourceRouting** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: IP source routing protection level (protects against packet spoofing)** nell'interfaccia utente di SCE.
  
Il source routing IP è un meccanismo che consente al mittente di determinare il routing IP che un datagramma deve seguire sulla rete. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Massima protezione, il source routing è completamente disattivato** per l'ambiente SSLF.
  
#### (EnableDeadGWDetect) Allow automatic detection of dead network gateways
  
Al file del modello è stata aggiunta la voce **EnableDeadGWDetect** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (EnableDeadGWDetect) Allow automatic detection of dead network gateways (could lead to DoS)** nell'interfaccia utente di SCE.
  
Quando si attiva il rilevamento dei gateway inattivi, se si evidenziano delle difficoltà per un certo numero di connessioni, l'IP potrebbe spostarsi su un gateway di backup. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Disattivato** per l'ambiente SSLF.
  
#### (EnableICMPRedirect) Allow ICMP redirects to override OSPF generated routes
  
Al file del modello è stata aggiunta la voce **EnableICMPRedirect** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (EnableICMPRedirect) Allow ICMP redirects to override OSPF generated routes** nell'interfaccia utente di SCE.
  
I reindirizzamenti del protocollo ICMP (Internet Control Message Protocol) provocano la canalizzazione delle route dell'host da parte dello stack. Tali route sostituiscono quelle generate da OSPF (Open Shortest Path First). Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Disattivato** per l'ambiente SSLF.
  
#### (Hidden) Hide the Computer from Network Neighborhood Browse Lists
  
Al file del modello è stata aggiunta la voce **Hidden** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Lanmanserver\\Parameters\\**. Questa voce è presente come **MSS: (Hidden) Hide Computer From the Browse List (not recommended except for highly secure environments)** nell'interfaccia utente di SCE.
  
È possibile configurare un computer in modo da non inviare annunci ai browser sul dominio. In questo modo il computer viene nascosto dall'elenco e quindi non annuncia più la propria presenza agli altri computer nella stessa rete. Un pirata informatico che conosce il nome di un computer può ottenere più facilmente maggiori informazioni sul sistema. È possibile attivare questa impostazione per rimuovere un metodo che un pirata informatico potrebbe utilizzare per raccogliere le informazioni sui computer nella rete. Inoltre, quando questa impostazione è abilitata, è possibile facilitare la riduzione del traffico di rete. Tuttavia, i vantaggi in termini di protezione di questa impostazione sono ridotti perché i pirati informatici possono utilizzare metodi alternativi per identificare e localizzare i potenziali obiettivi. Per questo motivo, Microsoft consiglia di attivare questa impostazione solo in ambienti con livello di protezione alto.
  
Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Attivato** per l'ambiente SSLF.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[COME A Nasconde un computer basato su Windows 2000 dall'Elenco browser](http://support.microsoft.com/default.aspx?scid=321710)", disponibile online all'indirizzo http://support.microsoft.com/default.aspx?scid=321710.
  
#### (KeepAliveTime) frequenza di invio dei pacchetti keep-alive espressa in millisecondi
  
Al file del modello è stata aggiunta la voce **KeepAliveTime** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (KeepAliveTime) How often keep-alive packets are sent in milliseconds (300,000 is recommended)** nell'interfaccia utente di SCE.
  
Con questo valore è possibile controllare la frequenza dei tentativi da parte del TCP di verificare se una connessione inattiva è ancora intatta, tramite l'invio di un pacchetto keep-alive. Se il computer remoto è ancora raggiungibile, il pacchetto keep-alive verrà riconosciuto. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **30000 o 5 minuti** per l'ambiente SSLF.
  
#### (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering
  
Al file del modello è stata aggiunta la voce **NoDefaultExempt** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\IPSEC\\**. Questa voce è presente come **MSS: (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering (recommended)** nell'interfaccia utente di SCE.
  
Le esenzioni predefinite ai filtri dei criteri IPsec sono descritte nella guida in linea di Microsoft Windows 2000 e Windows XP. Questi filtri consentono il funzionamento di IKE (Internet Key Exchange) e del protocollo di autenticazione Kerberos. I filtri consentono inoltre alla qualità del servizio (QoS) di rete di essere segnalata (RSVP) sia quando il traffico di dati è protetto da IPsec sia quando il traffico potrebbe non essere protetto da IPsec, come ad esempio il traffico multicast e broadcast.
  
L'utilizzo di IPsec è in aumento per il filtraggio di pacchetti host-firewall di base, specialmente negli scenari esposti a Internet e l'impatto di tali esenzioni predefinite non è stato completamente compreso. Di conseguenza, alcuni amministratori di IPsec possono creare i criteri IPsec che credono essere ad elevata protezione, ma che in realtà non lo sono contro gli attacchi informatici in ingresso che utilizzano le esenzioni predefinite. Microsoft consiglia di applicare l'impostazione predefinita in Windows  XP con SP 2, **Multicast, broadcast e ISAKMP sono esenti**, per entrambi gli ambienti trattati nel presente capitolo.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[È possibile utilizzare le esenzioni predefinite IPsec per eludere la protezione IPsec in alcuni scenari](http://support.microsoft.com/default.aspx?scid=811832)", disponibile online all'indirizzo http://support.microsoft.com/default.aspx?scid=811832.
  
#### (NoDriveTypeAutoRun) disabilita esecuzione automatica per tutte le unità
  
Al file del modello è stata aggiunta la voce **NoDriveTypeAutoRun** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\**  
**Policies\\Explorer**\\. Questa voce è presente come **MSS: (NoDriveTypeAutoRun) Disable Autorun for all drives (recommended)** nell'interfaccia utente di SCE.
  
La funzionalità di esecuzione automatica inizia a leggere in un’unità del computer non appena si inserisce un supporto in essa. Di conseguenza, il file di installazione dei programmi e l'audio su supporti audio vengono avviati immediatamente. Questa impostazione è configurata su **255, disabilita esecuzione automatica per tutte le unità** per entrambi gli ambienti trattati nel presente capitolo.
  
#### (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers
  
Al file del modello è stata aggiunta la voce **NoNameReleaseOnDemand** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Netbt\\Parameters\\**. Questa voce è presente come **MSS: (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers** nell'interfaccia utente di SCE.
  
TCP/IP è un protocollo di rete che, fra l’altro, consente di risolvere facilmente i nomi NetBIOS registrati in sistemi basati su Windows negli indirizzi IP configurati in tali sistemi. Questo valore determina se il computer deve rilasciare il suo nome NetBIOS quando riceve una richiesta di rilascio di nome. È impostato su **Non definito** per l'ambiente EC e su **Abilitato** per l'ambiente SSLF.
  
#### (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames
  
Al file del modello è stata aggiunta la voce **NtfsDisable8dot3NameCreation** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Control\\FileSystem\\**. Questa voce è presente come **MSS: (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames (recommended)** nell'interfaccia utente di SCE.
  
Windows Server 2003 supporta i nomi di file 8.3 per garantire la compatibilità con le applicazioni a 16 bit. Il formato di denominazione 8.3 consente di assegnare a un file un nome lungo al massimo otto caratteri. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Attivato** per l'ambiente SSLF.
  
#### (PerformRouterDiscovery) Allow IRDP to detect and configure Default Gateway addresses
  
Al file del modello è stata aggiunta la voce **PerformRouterDiscovery** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (PerformRouterDiscovery) Allow IRDP to detect and configure Default Gateway addresses (could lead to DoS)** nell'interfaccia utente di SCE.
  
Questa impostazione viene utilizzata per abilitare o disabilitare l'IRDP (Internet Router Discovery Protocol), che consente al sistema di rilevare e configurare automaticamente gli indirizzi di gateway predefiniti in base all'interfaccia secondo quanto descritto in RFC 1256. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Abilitato** per l'ambiente SSLF.
  
#### (SafeDllSearchMode) Abilitazione dell'ordine di ricerca Safe DLL
  
Al file del modello è stata aggiunta la voce **SafeDllSearchMode** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\ SYSTEM\\CurrentControlSet\\Control\\Session Manager\\**. Questa voce è presente come **MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended)** nell'interfaccia utente di SCE.
  
È possibile configurare la ricerca delle DLL richieste dai processi in esecuzione in due modi:
  
-   Prima eseguire la ricerca nelle cartelle specificate nel percorso di sistema, quindi eseguire la ricerca nella cartella di lavoro corrente.
  
-   Prima eseguire la ricerca nella cartella di lavoro corrente, quindi eseguire la ricerca nelle cartelle specificate nel percorso di sistema.
  
Quando abilitato, il valore del Registro di sistema è impostato su **1.** Se l’impostazione è **1**, il sistema ricerca dapprima le cartelle specificate nel percorso di sistema e successivamente la cartella di lavoro corrente. Quando è disabilitato, il valore del registro di sistema è impostato su **0** e il sistema ricerca dapprima la cartella di lavoro corrente e successivamente cartelle specificate nel percorso di sistema. Questa impostazione è configurata su **Abilitato** per entrambi gli ambienti descritti in questo capitolo.
  
#### (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires
  
Al file del modello è stata aggiunta la voce **ScreenSaverGracePeriod** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\SYSTEM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\**  
**Winlogon\\**. Questa voce è presente come **MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)** nell'interfaccia utente di SCE.
  
Se è impostato il blocco dello screen saver, tra l’avvio dello screen saver e il blocco effettivo della console intercorre un periodo di tempo. Questa impostazione è configurata su **0** secondi per entrambi gli ambienti descritti in questo capitolo.
  
#### (SynAttackProtect) Syn attack protection level
  
Al file del modello è stata aggiunta la voce **SynAttackProtect** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (SynAttackProtect) Syn attack protection level (protects against DoS)** nell'interfaccia utente di SCE.
  
Questa impostazione comporta l'adeguamento da parte del TCP della ritrasmissione di SYN-ACK. Quando si configura questo valore, il timeout di risposta della connessione è più rapido in caso di attacco di tipo richiesta di connessione (SYN). Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **Le connessioni raggiungono il timeout più velocemente se viene rilevato un attacco** per l'ambiente SSLF.
  
#### (TCPMaxConnectResponseRetransmissions) SYN-ACK retransmissions when a connection request is not acknowledged
  
Al file del modello è stata aggiunta la voce **TCPMaxConnectResponseRetransmissions** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (TcpMaxConnectResponseRetransmissions) SYN-ACK retransmissions when a connection request is not acknowledged** nell'interfaccia utente di SCE.
  
Questa impostazione determina il numero di volte che TCP ritrasmette un SYN prima di annullare il tentativo. Il timeout di ritrasmissione viene raddoppiato a ogni ritrasmissione successiva in una determinata connessione. Il valore iniziale di timeout è tre secondi. Questa impostazione è configurato su **Non definito** per l'ambiente EC e su **3 e 6 secondi, connessioni parziali interrotte dopo 21 secondi** per l'ambiente SSLF.
  
#### (TCPMaxDataRetransmissions) How many times unacknowledged data is retransmitted
  
Al file del modello è stata aggiunta la voce **TCPMaxDataRetransmissions** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**. Questa voce è presente come **MSS: (TcpMaxDataRetransmissions) How many times unacknowledged data is retransmitted (3 recommended, 5 is default)** nell'interfaccia utente di SCE.
  
Questa impostazione determina il numero di volte che TCP ritrasmette un singolo segmento di dati (non di connessione) prima di annullare la connessione. Il timeout di ritrasmissione viene raddoppiato a ogni ritrasmissione successiva in una determinata connessione. Viene reimpostato in caso di risposta. Il valore di timeout di base viene determinato dinamicamente dalla durata del percorso misurata nella connessione. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **3** per l'ambiente SSLF.
  
#### (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning
  
Al file del modello è stata aggiunta la voce **WarningLevel** nella chiave del Registro di sistema **HKEY\_LOCAL\_MACHINE\\ SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Security\\**. Questa voce è presente come **MSS: (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning** nell'interfaccia utente di SCE.
  
Questa impostazione è stata introdotta con la SP3 per Windows  2000 e consente di generare un controllo della protezione nel registro eventi di protezione quando il registro di protezione raggiunge la soglia definita dall’utente. Questa impostazione è configurata su **Non definito** per l'ambiente EC e su **90** per l'ambiente SSLF.
  
**Nota:** se per il registro è selezionata l’opzione **Sovrascrivi eventi se necessario** o **Sovrascrivi eventi anteriori a x giorni**, questo evento non viene generato.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Modifica dell'interfaccia utente dell'Editor di configurazione della protezione
  
Gli strumenti dell'interfaccia utente di SCE (Security Configuration Editor) vengono utilizzati per definire i modelli di protezione che possono essere applicati a singoli computer o a un numero non definito di computer attraverso i criteri di gruppo. I modelli di protezione possono contenere criteri password, criteri di blocco, criteri protocollo di autenticazione Kerberos, criteri di controllo, impostazioni del registro eventi, valori del Registro di sistema, modalità di avvio servizio, autorizzazioni per servizi, diritti utente, restrizioni per l'appartenenza ai gruppi, autorizzazioni del Registro di sistema e autorizzazioni del file system. L'interfaccia utente di SCE viene visualizzata in molti snap-in di MMC e in Strumenti di amministrazione. È utilizzato dallo snap-in Modelli di protezione e dallo snap-in Configurazione e analisi della protezione. Lo snap-in Editor oggetti Criteri di gruppo lo utilizza per la porzione di Impostazioni di protezione della struttura Configurazione computer ed è anche utilizzato per le Impostazioni protezione locale, per il Criterio di protezione del controller di dominio e per gli strumenti Criterio di protezione del dominio.
  
Questa guida contiene le impostazioni supplementari aggiunte allo SCE. Per aggiungere queste impostazioni, è necessario modificare il file sceregvl.inf, nella cartella **%systemroot%\\inf** e registrare nuovamente il file scecli.dll.
  
**Importante**: la versione personalizzata del file sceregvl.inf, creata dalle seguenti procedure, utilizza funzionalità disponibili esclusivamente in Windows XP Professional con SP 2 e Windows Server 2003. Non tentare di installare il file personalizzato in versioni precedenti di Windows.
  
Una volta modificato e registrato il file Sceregvl.inf, i valori personalizzati del Registro di sistema vengono visualizzati nelle interfacce utente di SCE del computer. Le nuove impostazioni vengono visualizzate in fondo all'elenco di elementi dell'interfaccia utente di SCE e sono precedute dal testo "MSS": MSS sta per "Microsoft Solutions for Security", che è il nome del gruppo che ha creato questa Guida. Sarà quindi possibile creare modelli o criteri di protezione per definire questi nuovi valori del Registro di sistema e che possono essere quindi applicati a qualsiasi computer a prescindere dal fatto che il file sceregvl.inf sia stato modificato sul computer di destinazione o meno. Nei successivi avvii dell'interfaccia utente di SCE vengono visualizzati i valori personalizzati del Registro di sistema.
  
Alcune delle nuove impostazioni che saranno presenti nello SCE non sono descritte nella presente guida, in quanto in genere non sono configurate per sistemi per utenti finali. Per le ulteriori informazioni su queste impostazioni vedere la guida correlata [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), disponibile per il download all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
Le istruzioni su come modificare l'interfaccia utente di SCE sono fornite nelle seguenti procedure. Se sono state già effettuate altre personalizzazioni allo SCE, è necessario seguire alcune istruzioni manuali. Uno script viene fornito per consentire di aggiungere impostazioni con una minima interazione da parte dell'utente e anche se al suo interno ha funzioni che permettono di rilevare e correggere l'errore, queste potrebbero non funzionare. Se vengono eseguite correttamente, è necessario stabilire la causa dell'errore e correggere il problema o seguire le istruzioni manuali. Un altro script è fornito per ripristinare l'interfaccia utente di SCE allo stato predefinito. Questo script rimuoverà tutte le impostazioni personalizzate e riporterà lo SCE alla visualizzazione dell'installazione predefinita di Windows XP con SP2 o Windows Server 2003 con SP1.
  
**Per aggiornare manualmente il file Sceregvl.inf**
  
1.  Per aprire il file **Values-sceregvl.txt** dalla cartella di **SCE Update** contenuta nel download di questa guida, utilizzare un editor di testi, come ad esempio Blocco note.
  
2.  Aprire un'altra finestra nell'editor di testi, quindi aprire il file **%systemroot%\\inf\\sceregvl.inf**.
  
3.  Passare nella parte inferiore della sezione \[Register Registry Values\] nel file **sceregvl.inf.** Copiare e incollare il testo dal file **values-sceregvl.txt**, senza interruzioni di pagina, in questa sezione del file **sceregvl.inf.**
  
4.  Chiudere il file **values-sceregvl.txt** e aprire il file **strings-sceregvl.txt** dalla cartella **SCE Update** del download.
  
5.  Passare nella parte inferiore della sezione \[Strings\] nel file **sceregvl.inf.** Copiare e incollare il testo dal file **strings-sceregvl.txt**, senza interruzioni di pagina, in questa sezione del file **sceregvl.inf.**
  
6.  Salvare il file **sceregvl.inf** e chiudere l'editor di testo.
  
7.  Aprire una finestra del prompt dei comandi e immettere il comando **regsvr32 scecli.dll** per registrare di nuovo la DLL.
  
Nei successivi avvii dell'interfaccia utente di SCE vengono visualizzati i valori personalizzati del Registro di sistema.
  
**Per aggiornare automaticamente il file sceregvl.inf**
  
1.  Per rendere effettivo il funzionamento dello script, i file **values-sceregvl.txt, strings-sceregvl.txt,** e **update\_SCE\_with\_MSS\_Regkeys.vbs** situati nella cartella di **SCE Update** contenuta nel download di questa guida, devono trovarsi tutti nella stessa posizione.
  
2.  Eseguire lo script **Update\_SCE\_with\_MSS\_Regkeys.vbs** sul computer da aggiornare.
  
3.  Seguire le istruzioni su schermo.
  
Questa procedura rimuoverà solamente le voci personalizzate realizzate con lo script descritto nella procedura precedente, **Update\_SCE\_with\_MSS\_Regkeys.vbs.**
  
**Per annullare le modifiche effettuate da Update\_SCE\_with\_MSS\_Regkeys.vbs lo script**
  
1.  Eseguire lo script **Rollback\_SCE\_for\_MSS\_Regkeys.vbs** sul computer da aggiornare.
  
2.  Seguire le istruzioni su schermo.
  
Questa procedura rimuoverà *qualsiasi* voce personalizzata aggiunta all'interfaccia utente di SCE, tra cui quelle della presente guida e tutte le altre voci che possono esser state fornite nelle versioni precedenti della presente guida o di altre guide per la protezione.
  
**Per ripristinare lo stato predefinito dello SCE per Windows XP con SP2 o Windows Server 2003 con SP1**
  
1.  Per rendere effettivo il funzionamento dello script, i file **sceregvl\_W2K3\_SP1.inf.txt, sceregvl\_XPSP2.inf.txt,** e **Restore\_SCE\_to\_Default.vbs** situati nella cartella di **SCE Update** contenuta nel download di questa guida, devono trovarsi tutti nella stessa posizione.
  
2.  Eseguire lo script **Restore\_SCE\_to\_Default.vbs** sul computer da aggiornare.
  
3.  Seguire le istruzioni su schermo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
La maggior parte delle misure adottate per potenziare la protezione dei sistemi client nei due ambienti definiti in questo capitolo sono state applicate tramite Criteri di gruppo. Vi sono, tuttavia, altre impostazioni che non è facile o possibile applicare con Criteri di gruppo. Per una descrizione dettagliate delle impostazioni trattate in questa sezione, vedere la guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://go.microsoft.com/fwlink/?linkid=15159), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
#### Procedure manuali per la protezione avanzata
  
In questa sezione verranno descritte in che modo le misure aggiuntive siano state implementate a mano per la protezione dei client Windows XP, per ciascuno degli ambienti definiti nella presente guida.
  
##### Disabilitazione di Dr. Watson: esecuzione automatica di disabilitazione del debugger di sistema del Dr. Watson
  
Alcune organizzazioni ritengono che i debugger di sistema come lo strumento Dr. Watson, contenuto in Windows, possano essere sfruttati da pirati informatici esperti. Per le istruzioni su come disattivare il debugger di sistema Dr. Watson, vedere l'articolo della Microsoft Knowledge Base [Disabilitazione di Dr. Watson per Windows](http://support.microsoft.com/default.aspx?scid=188296), disponibile online all'indirizzo http://support.microsoft.com/default.aspx?scid=188296.
  
##### Disabilitare SSDP/UPNP: Disabilitare SSDP/UPNP
  
Alcune organizzazioni ritengono che le funzionalità Plug and Play universali incluse nei sottocomponenti di Windows  XP dovrebbero essere completamente disabilitate. Anche se il servizio **Host Plug and Play universale** viene disabilitato in questa guida, per individuare gateway di rete o altri dispositivi di rete, applicazioni quale ad esempio Windows Messenger utilizzeranno il processo **del servizio di rilevamento SSDP (Simple Service Discovery Protocol)**. Per garantire che nessuna applicazione utilizzi le funzionalità SSDP e UPnP incluse in Windows XP, è sufficiente aggiungere un valore del Registro di sistema REG\_DWORD chiamato **UPnPMode** alla chiave del Registro di sistema di **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DirectPlayNATHelp\\DPNHUPnP\\** e impostare il suo valore su **2.**
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[L'invio di traffico dopo aver rilevato il servizio, Plug and Play universale e l'host di periferica di riproduzione](http://support.microsoft.com/default.aspx?scid=317843)", disponibile online all'indirizzo http://support.microsoft.com/default.aspx?scid=317843.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione del File System
  
Il file system NTFS è stato migliorato a ogni nuova versione di Microsoft Windows. Le autorizzazioni predefinite per NTFS sono adeguate per la maggior parte delle organizzazioni. Le impostazioni trattate in questa sezione sono destinate alle organizzazioni che utilizzano desktop e portatili nell'ambiente SSLF (Specialized Security – Limited Functionality) definito nella presente guida.
  
Le impostazioni per la protezione del file system possono essere modificate tramite i Criteri di gruppo. È possibile configurare le impostazioni del file system nella seguente posizione nell'Editor criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\File system**
  
**Nota**: qualsiasi modifica alle impostazioni di protezione del file system dovrebbe essere controllata attentamente in un ambiente di prova prima della distribuzione in una grande organizzazione. Si sono registrati casi in cui le autorizzazioni sui file sono state modificate a tal punto che si è dovuto provvedere alla completa ricostruzione dei computer interessati.
  
Le autorizzazioni predefinite sui file in Windows XP sono sufficienti per la maggior parte delle situazioni. Tuttavia, se non si sta per bloccare l'appartenenza al gruppo **Power Users** con la funzionalità Gruppi con restrizioni o si sta per attivare l'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi**, è possibile applicare le autorizzazioni opzionali descritte nel paragrafo riportato di seguito. Queste autorizzazioni opzionali sono molto specifiche e applicano ulteriori restrizioni ad alcuni degli strumenti eseguibili che un utente malintenzionato con un livello di privilegi elevato può utilizzare per compromettere ulteriormente il sistema o la rete.
  
Queste modifiche alle autorizzazioni non interessano le cartelle multiple o la directory principale del volume di sistema. Può essere molto rischioso utilizzare questo metodo per modificare le autorizzazioni, poiché spesso può provocare instabilità del sistema. Tutti i file sono collocati nella cartella **%SystemRoot%\\System32\\**, e riportano tutti le seguenti autorizzazioni: **Administrators: controllo completo, System: controllo completo**.
  
-   regedit.exe
  
-   arp.exe
  
-   a.exe
  
-   attrib.exe
  
-   cacls.exe
  
-   debug.exe
  
-   edlin.exe
  
-   eventcreate.exe
  
-   eventtriggers exe
  
-   ftp.exe
  
-   nbtstat.exe
  
-   net.exe
  
-   net1.exe
  
-   netsh.exe
  
-   netstat.exe
  
-   nslookup.exe
  
-   ntbackup.exe
  
-   rcp.exe
  
-   reg.exe
  
-   regedt32.exe
  
-   regini.exe
  
-   regsvr32.exe
  
-   rexec.exe
  
-   strada.exe
  
-   rsh.exe
  
-   sc.exe
  
-   secedit.exe
  
-   subst.exe.exe
  
-   systeminfo.exe
  
-   telnet.exe
  
-   tftp.exe
  
-   tlntsvr.exe
  
In base alle proprie esigenze, queste autorizzazioni opzionali sono già configurate nel modello di protezione chiamato Optional-File-Permissions.inf, incluso nella versione scaricabile di questa guida.
  
#### Autorizzazioni avanzate
  
È possibile accedere a molti più controlli di quelli disponibili nella finestra di dialogo **Autorizzazioni.** Per accedervi, fare clic sul pulsante **Avanzate.** La seguente tabella descrive le autorizzazioni avanzate.
  
**Tabella 3.22 Autorizzazioni file avanzate e descrizioni**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome dell'autorizzazione avanzata</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Visita cartelle/Esecuzione file</td>
<td style="border:1px solid black;">Accetta o respinge le richieste di un utente di esplorare le cartelle per giungere ad altre cartelle o file, anche se non ha l'autorizzazione di visitare le cartelle (si applica solo alle cartelle).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Visualizza contenuto cartelle/Lettura dati</td>
<td style="border:1px solid black;">Accetta o respinge le richieste di un utente di visualizzare il nome delle sottocartelle e dei file contenuti in una data cartella. Influisce solo sui contenuti di una data cartella, non sulla visualizzazione della cartella per la quale si sta impostando l'autorizzazione (si applica solo alle cartelle).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Lettura attributi</td>
<td style="border:1px solid black;">Consente o rifiuta la visualizzazione dei dati nei file (si applica solo ai file).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Lettura attributi estesi</td>
<td style="border:1px solid black;">Accetta o rifiuta le richieste di un utente di visualizzare gli attributi di un file o di una cartella, ad esempio sola lettura e nascosto. Gli attributi sono definiti da NTFS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione file/Scrittura dati</td>
<td style="border:1px solid black;">Creazione file accetta o rifiuta la creazione di file all'interno della cartella (si applica solo alle cartelle). Scrittura dati accetta o rifiuta la possibilità di apportare modifiche al file e di sovrascriverne il contenuto esistente (si applica solo ai file).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione cartelle/Aggiunta dati</td>
<td style="border:1px solid black;">Creazione cartelle accetta o rifiuta le richieste di un utente di creare cartelle all'interno di una cartella specifica (si applica solo alle cartelle) Aggiunta dati accetta o rifiuta la possibilità di apportare modifiche alla fine del file, ma non di modificare, cancellare o sovrascrivere il contenuto esistente (si applica solo ai file).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Scrittura attributi</td>
<td style="border:1px solid black;">Accetta o rifiuta le richieste di un utente di apportare modifiche alla fine del file, ma non di modificare, cancellare o sovrascrivere il contenuto esistente (si applica solo ai file).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Scrittura attributi estesi</td>
<td style="border:1px solid black;">Accetta o rifiuta le richieste di un utente di cambiare gli attributi di un file o di una cartella, ad esempio sola lettura e nascosto. Gli attributi sono definiti da NTFS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Eliminazione sottocartelle e file</td>
<td style="border:1px solid black;">Accetta o rifiuta la possibilità di eliminare sottocartelle e file, anche se non è stata concessa l'autorizzazione per la loro cancellazione (si applica alle cartelle).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Eliminazione</td>
<td style="border:1px solid black;">Accetta o rifiuta le richieste di un utente di eliminare sottocartelle e file, anche se non è stata concessa l'autorizzazione per la loro cancellazione (si applica alle cartelle).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autorizzazioni di lettura</td>
<td style="border:1px solid black;">Accettano o rifiutano le richieste di un utente di leggere le autorizzazioni di file o cartelle, ad esempio Controllo completo, Lettura e Scrittura.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Cambia autorizzazioni</td>
<td style="border:1px solid black;">Accetta o rifiuta le richieste di un utente di modificare le autorizzazioni di file o cartelle, ad esempio Controllo completo, Lettura e Scrittura.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Diventa proprietario</td>
<td style="border:1px solid black;">Accetta o rifiuta la possibilità di diventare proprietario di file o cartelle. Il proprietario di un file o di una cartella può sempre cambiare le autorizzazioni su di essi, indipendentemente dalle autorizzazioni esistenti che proteggono il file o la cartella.</td>
</tr>
</tbody>
</table>
  
I tre termini seguenti sono utilizzati per descrivere l'ereditarietà delle autorizzazioni applicate a file e cartelle:
  
-   **Propaga** si riferisce alla propagazione delle autorizzazioni ereditabili a tutte le sottocartelle e ai file. Qualsiasi oggetto figlio eredita le impostazioni di protezione dell'oggetto padre, a condizione che non sia protetto dall'accettare l'ereditarietà delle autorizzazioni. In caso di conflitto, le autorizzazioni esplicite sull'oggetto figlio prevarranno su quelle ereditate dall'oggetto padre.
  
-   **Sostituisci** si riferisce alla sostituzione delle autorizzazioni esistenti su tutte le sottocartelle e i file con autorizzazioni ereditabili. Le autorizzazioni dell'oggetto padre prevarranno su qualsiasi impostazione di protezione dell'oggetto figlio, indipendentemente dalle impostazioni di quest'ultimo. L'oggetto figlio avrà gli stessi controlli di accesso dell'oggetto padre.
  
-   **Ignora** non consente la sostituzione di autorizzazioni su file, cartella (o chiave). Utilizzare questa opzione se non si desidera configurare o analizzare la protezione per un dato oggetto o uno qualsiasi dei suoi oggetti figlio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo descrive in dettaglio le impostazioni di protezione primarie e le configurazioni consigliate per ogni impostazione, al fine di proteggere i computer che eseguono Windows  XP Professional con SP2 in entrambi gli ambienti descritti nel presente capitolo. Al momento di valutare i criteri di protezione per un'organizzazione, è consigliabile bilanciare le azioni di protezione con la produttività degli utenti. Sebbene sia necessario proteggere gli utenti da codice dannoso e pirati informatici, è anche necessario che gli utenti possano continuare a svolgere i loro compiti senza che criteri di protezione eccessivamente restrittivi influiscano negativamente sul loro operato.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni su argomenti relativi alla protezione di Windows XP Professional.
  
-   Per ulteriori informazioni su come garantire la protezione per Windows XP Professional, vedere lo strumento di assistenza e supporto incluso in Windows XP ed il sito Web di Microsoft [Windows XP Security and Privacy](http://technet.microsoft.com/en-us/library/bb457059.aspx) all'indirizzo www.microsoft.com/windowsxp/security/.
  
-   Per ulteriori informazioni sulle funzionalità di protezione in Windows XP SP2, vedere "[Security Information for Windows XP Service Pack 2](http://technet.microsoft.com/en-us/library/bb878160.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/maintain/xpsp2sec.mspx.
  
-   Per ulteriori informazioni sulle impostazioni di protezione disponibili in Windows  XP SP2, vedere l'articolo pubblicato su Microsoft TechNet dal titolo "[Security Setting Descriptions](http://technet.microsoft.com/en-us/library/cc739828.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/  
    windowsserver2003/library/ServerHelp/dd980ca3-f686-4ffc-a617-50c6240f5582.mspx.
  
-   Per ulteriori informazioni sulla protezione del sistema operativo Windows, vedere [Microsoft Windows Security Resource Kit](https://technet.microsoft.com/it-it/library/microsoft+windows+security+resource+kit(v=TechNet.10)) all'indirizzo www.microsoft.com/MSPress/books/6418.asp.
  
-   Per ulteriori informazioni sulla funzione di Crittografia file system di Windows  XP e Windows Server 2003, vedere "[Encrypting File System in Windows XP and Windows Server 2003](http://technet.microsoft.com/en-us/library/bb457065.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/deploy/cryptfs.mspx.
  
##### Download
  
[![](images/Cc163074.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
