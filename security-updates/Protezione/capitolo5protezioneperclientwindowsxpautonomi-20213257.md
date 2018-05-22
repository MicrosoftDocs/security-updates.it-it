---
TOCTitle: 'Capitolo 5: Protezione per client Windows XP autonomi'
Title: 'Capitolo 5: Protezione per client Windows XP autonomi'
ms:assetid: 'a134d1cb-2ad1-4549-99c8-2a5e0128f2dc'
ms:contentKeyID: 20213257
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163078(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Capitolo 5: Protezione per client Windows XP autonomi

##### In questa pagina

[](#eeaa)[Panoramica](#eeaa)  
[](#edaa)[Windows XP in un dominio di Windows NT 4.0](#edaa)  
[](#ecaa)[Impostazioni dell'oggetto Criteri di gruppo locale](#ecaa)  
[](#ebaa)[Importazione dei modelli di protezione in Windows XP](#ebaa)  
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

I computer dotati di Microsoft Windows XP Professional che non appartengono a un dominio del servizio Active Directory presentano alcuni problemi di gestione. In questo capitolo viene descritta la procedura per applicare e gestire in modo più efficiente le impostazioni consigliate nei capitoli precedenti della guida. Le impostazioni di criterio consigliate consentiranno di proteggere i computer desktop e portatili autonomi dell'organizzazione dotati di Windows XP Professional. Le impostazioni sono applicate mediante criteri locali e si riferiscono a tutti gli utenti che effettuano l'accesso al computer client, amministratore locale compreso.

Questo capitolo non fornisce indicazioni per tutte le impostazioni di criterio disponibili in Windows XP. Le impostazioni di criterio consigliate assicureranno tuttavia un ambiente operativo protetto dalla maggior parte dei pericoli correnti, consentendo agli utenti di continuare a utilizzare i relativi computer. È consigliabile utilizzare le impostazioni applicate in base agli obiettivi di protezione dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Windows XP in un dominio di Windows NT 4.0

Un esempio specifico di un client Windows XP nell'ambiente di un dominio non Active Directory potrebbe essere un computer Windows XP in un dominio di Microsoft Windows NT 4.0. In questo ambiente, i client Windows XP vengono considerati computer autonomi. In questo tipo di ambiente il sovraccarico di gestione è maggiore, in quanto non esiste una posizione centrale per la gestione delle impostazioni di criterio. Microsoft consiglia di installare i controller di dominio basati su Windows NT 4.0 con Service Pack 6a (SP6a) e gli aggiornamenti più recenti. Windows NT 4.0 SP6a contiene diversi aggiornamenti per l'autenticazione NTLM. Senza questi aggiornamenti, nei computer Windows XP in un dominio di Windows NT 4.0 potrebbero verificarsi problemi di comunicazione e di connettività alla rete o al dominio. È consigliabile che l'amministratore ricerchi spesso gli aggiornamenti.

Windows XP Professional offre ulteriori impostazioni di criterio rispetto alle versioni precedenti di Windows, consentendo di personalizzare in modo ottimale le impostazioni dell'utente e del computer. In Windows XP Professional sono disponibili centinaia di nuove impostazioni di criterio locali, oltre a quelle già esistenti in Windows 2000 Professional. I criteri locali rappresentano una potente funzionalità di gestione che consente di bloccare e ottimizzare i computer desktop in uso. Introduce inoltre la possibilità di ottenere diversi scenari personalizzati. Gli amministratori di dominio sono membri del gruppo **Amministratori** locale su tutti i computer client che fanno parte del dominio; quindi, i computer client Windows XP saranno protetti come il dominio di cui sono membri.

I computer client Windows XP di un ambiente precedente utilizzano una versione modificata dei modelli di protezione illustrata nel capitolo 3, "Impostazioni di protezione per client Windows XP", per assicurare la comunicazione con i controller di dominio di Windows NT 4.0. Queste impostazioni di criterio vengono applicate mediante gli script indicati alla fine del presente capitolo.

Per comunicare con un controller di dominio di Windows NT 4.0, le impostazioni seguenti vengono modificate nel percorso **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Opzioni di protezione:**

-   **Membro di dominio: richiesta chiave di sessione avanzata (Windows 2000 o versioni successive) - Disabilitato**

-   **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre) - Disabilitato**

Queste impostazioni di criterio sono preconfigurate nei file dei modelli di protezione di client precedenti contenuti nella presente guida.

[](#mainsection)[Inizio pagina](#mainsection)

### Impostazioni dell'oggetto Criteri di gruppo locale

In ogni sistema operativo Windows XP Professional è disponibile un oggetto Criteri di gruppo locale (LGPO). Le impostazioni vengono applicate manualmente all'oggetto LGPO tramite l'Editor oggetti Criteri di gruppo o mediante l'utilizzo di script. Gli oggetti LGPO contengono un minor numero di impostazioni di criterio rispetto ai GPO basati sul dominio, in particolare in Impostazioni protezione. Gli oggetti LGPO non supportano Reindirizzamento cartelle, Servizio di installazione remota o Installazione software di Criteri di gruppo quando vengono configurati come computer client autonomi, ma è possibile utilizzarli per offrire un ambiente operativo protetto su tali computer.

Nella tabella seguente vengono illustrate le estensioni dello snap-in Criteri di gruppo aperte nel caso di un LGPO.

**Tabella 5.1 Estensioni dello snap-in Criteri di gruppo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Estensione dello snap-in Criteri di gruppo</th>
<th style="border:1px solid black;" >Disponibile in LGPO</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Installazione software</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Script</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impostazioni di protezione</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modelli amministrativi</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Reindirizzamento cartelle</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Manutenzione di Internet Explorer</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio di installazione remota</td>
<td style="border:1px solid black;">No</td>
</tr>
</tbody>
</table>
  
#### Criteri di account
  
I criteri di account includono le impostazioni Criterio password, Criterio di blocco account e Criterio Kerberos. Il Criterio password consente di richiedere un certo livello di complessità e la modifica frequente delle password per proteggere la maggior parte degli ambienti. Il Criterio di blocco account consente di disattivare automaticamente un account dopo una serie di tentativi di accesso non riusciti. Le impostazioni Criterio Kerberos determinano gli attributi relativi a Kerberos di account utente di dominio, come ad esempio **Durata massima ticket utente** e **Imporre le restrizioni di accesso degli utenti**. Queste impostazioni di criterio non sono tuttavia utilizzate per computer client autonomi in quanto non partecipano a un dominio.
  
In genere, i criteri di account vengono impostati a livello di dominio e vengono pertanto configurati per i computer client del dominio. Per i computer client Windows XP autonomi, è necessario applicare localmente queste impostazioni in modo simile a quelle descritte nel Capitolo 2 della presente guida, "Configurazione dell'infrastruttura per il dominio di Active Directory".
  
#### Criteri locali
  
I criteri locali disponibili in **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione** verranno applicati al computer client tramite i modelli descritti nel Capitolo 3 della presente guida, "Impostazioni di protezione per client Windows XP". Viene utilizzata una combinazione di tali modelli e di quelli creati per i computer client autonomi; è possibile automatizzare l'applicazione dei modelli di protezione mediante script che si possono applicare a più computer presenti nell'ambiente. Nella sezione successiva viene descritto il processo di creazione e distribuzione dei criteri locali.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Importazione dei modelli di protezione in Windows XP
  
Esistono diversi modelli che è possibile utilizzare per configurare il computer client autonomo mediante uno script; è necessario utilizzare un modello che supporti i requisiti di protezione del client. La sezione precedente ha trattato le impostazioni Criterio locale e il modo in cui l'Editor oggetti Criteri di gruppo viene utilizzato per configurarle. Mediante i modelli forniti è possibile automatizzare il processo di configurazione di molti computer client in un ambiente di rete o autonomo. Nella sezione seguente verrà descritto il processo di automatizzazione della configurazione relativa ai criteri di protezione.
  
#### Configurazione
  
Un modello di protezione è un file che rappresenta una configurazione di protezione. Per applicare i modelli di protezione a un computer locale, è possibile importarli negli LGPO. I modelli creati nel capitolo 3, "Impostazioni di protezione per client Windows XP", saranno utilizzati per configurare i criteri locali. L'amministratore utilizzerà gli snap-in MMC (Microsoft Management Console) Analisi e configurazione della protezione e Modelli di protezione in aggiunta allo strumento Secedit.exe, per creare i criteri di account e unire entrambi i modelli di protezione nel computer autonomo.
  
##### Creazione di un database di protezione
  
Per automatizzare il processo di importazione delle impostazioni di protezione in un computer client autonomo, è necessario creare un database di riferimento in cui registrare i criteri di protezione locali. Il database di base è stato creato tramite lo snap-in MMC Analisi e configurazione della protezione. Il database XP Default Security.sdb è stato creato tramite la procedura indicata di seguito. Nel database è stato utilizzato il modello del file Setup security.inf per stabilire le impostazioni predefinite per il computer client autonomo.
  
**Per creare un nuovo database di protezione predefinito**
  
1.  Nel menu **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, scegliere **Nuovo** per creare una nuova console.
  
3.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**. Fare quindi clic sulla scheda **Autonomo** nella finestra di dialogo delle **proprietà** **Aggiungi/Rimuovi snap-in** e fare clic su **Aggiungi**.
  
4.  Selezionare **Analisi e configurazione della protezione**, fare clic su **Aggiungi**, quindi su **Chiudi** e infine su **OK**.
  
5.  Fare clic con il pulsante destro del mouse sull'elemento dell'ambito **Analisi e configurazione della protezione**, quindi fare clic su **Apri database**.
  
6.  Digitare il nome di un nuovo database (XP Default Security), quindi fare clic su **Apri**.
  
7.  Selezionare un modello di protezione da importare (**setup security.inf**), quindi fare clic su **Apri**.
  
8.  Fare clic con il pulsante destro del mouse sull'elemento dell'ambito **Analisi e configurazione della protezione**, quindi scegliere **Configura il sistema ora**.
  
9.  Nella finestra di dialogo **Configurazione sistema** digitare il nome del file di registro che si desidera utilizzare, quindi fare clic su **OK**.
  
Questa procedura consente di creare un file del database con le impostazioni di protezione predefinite che verranno utilizzate nel processo di automatizzazione. Copiare il database di protezione nella stessa cartella in cui sono stati copiati gli script e i file di informazioni. Gli script personalizzati saranno utilizzati per configurare il database, che a sua volta configurerà i criteri di protezione locali. L'amministratore può utilizzare una procedura analoga per creare un database personalizzato anziché quello fornito con la guida.
  
##### Creazione di modelli personalizzati
  
È possibile utilizzare lo snap-in MMC Modelli di protezione per definire le impostazioni dei criteri di protezione nei modelli, che è poi possibile applicare al computer locale. La procedura indicata di seguito è stata eseguita per creare i modelli Standalone-EC-Account.inf e Standalone-SSLF-Account.inf in base alle impostazioni di criterio delle tabelle Criteri di account contenute nel Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory".
  
**Per creare un modello personalizzato**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi fare clic su **OK**.
  
2.  Nel menu **File**, scegliere **Nuovo** per creare una nuova console.
  
3.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**. Fare quindi clic sulla scheda **Autonomo** nella finestra di dialogo delle **proprietà** **Aggiungi/Rimuovi snap-in** e fare clic su **Aggiungi**.
  
4.  Scegliere **Modelli di protezione**, fare clic su **Aggiungi**, quindi su **Chiudi**, infine su **OK**.
  
5.  Aprire **Modelli di protezione**.
  
6.  Selezionare la cartella predefinita per archiviare il nuovo modello, quindi fare clic su **Nuovo modello**.
  
7.  Nella casella di testo **Nome modello**, digitare il nome del nuovo modello di protezione.
  
8.  Nella casella di testo **Descrizione**, digitare una descrizione del nuovo modello di protezione, quindi fare clic su **OK**.
  
9.  Nella struttura della console, fare doppio clic sul nuovo modello di protezione per visualizzare le aree di protezione e passare all'impostazione del criterio che si desidera configurare nel riquadro dei dettagli.
  
10. Nel riquadro dei dettagli, fare clic con il pulsante destro del mouse sull'impostazione di criterio che si desidera configurare, quindi scegliere **Proprietà**.
  
11. Nella finestra di dialogo **Proprietà**, selezionare la casella di controllo **Definisci questa impostazione nel modello**, modificare le impostazioni, quindi fare clic su **OK**.
  
Dopo aver creato i file, è possibile ritrovarli in **%windir%\\security\\templates.** Copiare i modelli di protezione nella stessa cartella in cui è stato creato il database di protezione per eseguire gli script. Questi file verranno utilizzati nella fase successiva per automatizzare l'importazione dei modelli.
  
#### Applicazione dei criteri
  
Lo strumento Secedit.exe risulta utile nel caso in cui sia necessario configurare la protezione in più computer. Se si richiama lo strumento Secedit.exe da un prompt dei comandi, da un file batch o da un'utilità di pianificazione automatica, sarà possibile creare e applicare automaticamente i modelli. È inoltre possibile eseguirlo in modo dinamico da un prompt dei comandi. Gli script forniti con la guida utilizzano lo strumento Secedit.exe per unire e applicare i criteri locali ai computer client.
  
##### Applicazione manuale dei criteri locali
  
Per applicare tutte le impostazioni di criterio incluse nel file .inf del modello di protezione autonomo incluso in questa guida, è necessario utilizzare lo snap-in MMC Analisi e configurazione della protezione anziché lo snap-in Criteri del computer locale. Non è possibile importare il modello di protezione utilizzando lo snap-in Criteri del computer locale poiché non consente di applicare le impostazioni di criterio di protezione per i servizi di sistema.
  
Per importare e applicare il modello di protezione, utilizzare lo snap-in Analisi e configurazione della protezione, in modo da completare le fasi delle procedure seguenti.
  
**Per importare un modello di protezione**
  
1.  Avviare lo snap-in MMC Analisi e configurazione della protezione.
  
2.  Fare clic con il pulsante destro del mouse sull'elemento dell'ambito **Analisi e configurazione della protezione**.
  
3.  Scegliere **Apri database**.
  
4.  Digitare il nome di un nuovo database, quindi fare clic su **Apri**.
  
5.  Selezionare un modello di protezione da importare (file .inf), quindi fare clic su **Apri**.
  
Tutte le impostazioni di criterio nel modello verranno importate e a questo punto sarà possibile revisionarle o applicarle.
  
**Per applicare le impostazioni di criterio**
  
1.  Fare clic con il pulsante destro del mouse sull'elemento dell'ambito **Analisi e configurazione della protezione**.
  
2.  Selezionare **Configura il sistema ora**.
  
3.  Nella finestra di dialogo **Configura il sistema ora** digitare il nome del file di registro che si desidera utilizzare, quindi fare clic su **OK**.
  
Sarà necessario importare entrambi i modelli per ogni ambiente. Tutte le impostazioni di criterio del modello di protezione pertinenti verranno applicate ai criteri locali del computer client. Nelle sezioni seguenti vengono descritte le impostazioni di criterio applicate attraverso i criteri locali.
  
##### Secedit
  
Questo strumento configura e analizza la protezione del sistema confrontando la configurazione corrente almeno con un modello. Di seguito viene riportata la sintassi di utilizzo dello strumento Secedit.exe:
  
**secedit /configure /db** *&lt;NomeFile&gt;* \[**/cfg** *&lt;NomeFile&gt;*\] \[**/overwrite**\]\[**/areas** *&lt;Area1&gt; &lt;Area2&gt;* ...\]  
\[**/log** *&lt;NomeFile&gt;*\] \[**/quiet**\]
  
L'elenco seguente illustra i parametri dello strumento Secedit.exe.
  
-   **/db** *&lt;NomeFile&gt;.* Specifica il database utilizzato per eseguire la configurazione della protezione.
  
-   **/cfg** *&lt;NomeFile&gt;.* Specifica un modello di protezione da importare nel database prima di configurare il computer. I modelli di protezione vengono creati tramite lo snap-in Modelli di protezione.
  
-   **/overwrite**. Specifica che il database deve essere svuotato prima di importare il modello di protezione. Se questo parametro non viene specificato, le impostazioni di criterio nel modello di protezione vengono accumulate nel database. Se il parametro non viene specificato e le impostazioni di criterio del modello che si desidera importare sono in conflitto con le impostazioni di criterio esistenti nel database, vengono applicate le impostazioni del modello.
  
-   **/areas** *&lt;Area1&gt;* *&lt;Area2&gt;*. Specifica le aree di protezione da applicare al sistema. Se il parametro non viene specificato, tutte le impostazioni di criterio di protezione definite nel database vengono applicate al sistema. Per configurare più aree, separarle tramite uno spazio. Nella tabella seguente vengono illustrate le aree di protezione supportate.
  
**Tabella 5.2 Aree di protezione**

<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome dell'area</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SECURITYPOLICY</td>
<td style="border:1px solid black;">Include Criteri account, Criteri controllo, Impostazioni del registro eventi e Opzioni di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GROUP_MGMT</td>
<td style="border:1px solid black;">Include le impostazioni Gruppi con restrizioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">USER_RIGHTS</td>
<td style="border:1px solid black;">Include le impostazioni di assegnazione dei diritti utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">REGKEYS</td>
<td style="border:1px solid black;">Include le autorizzazioni del Registro di sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">FILESTORE</td>
<td style="border:1px solid black;">Include le autorizzazioni del file system.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SERVICES</td>
<td style="border:1px solid black;">Include le impostazioni dei servizi di sistema.</td>
</tr>
</tbody>
</table>
  
-   **/log** *&lt;NomeFile&gt;*. Specifica un file in cui registrare lo stato del processo di configurazione. Se non si specifica questo parametro, i dati di configurazione vengono registrati nel file scesrv.log che si trova nella directory **%windir%\\security\\logs**.
  
-   **/quiet**. Specifica che il processo di configurazione verrà eseguito senza richiedere la conferma dell'utente.
  
##### Script automatici
  
L'utilizzo degli script rappresenta sempre il metodo più semplice per applicare impostazioni di criterio identiche a più computer client. Tramite lo strumento Secedit.exe descritto in precedenza in questo capitolo, il processo può essere automatizzato al fine di applicare i criteri locali utilizzando un semplice script. Copiare lo script e i tutti i file associati in una sottodirectory del disco rigido locale, quindi eseguire lo script dalla sottodirectory.
  
Il seguente script può essere utilizzato per importare i modelli di protezione negli LGPO, al fine di garantire la protezione dei computer client Windows XP autonomi nell'ambiente specifico.
  
**Importante:** verificare che il file del database di protezione **XP Default Security.sdb** non sia di sola lettura. Perché lo script funzioni correttamente, deve essere in grado di modificare il file.

```
REM (c) Microsoft Corporation 1997-2005

REM Script for Securing Stand-Alone Windows XP Client Computers
REM
REM Name:        Standalone-EC-Desktop.cmd
REM Version:     2.0

REM This CMD file provides the proper secedit.exe syntax for importing
REM the security policy for a secure stand-alone Windows XP desktop 
REM client computer. Please read the entire guide before using this 
REM CMD file.

REM Resets the Policy to Default Values
secedit.exe /configure /cfg %windir%\repair\secsetup.inf 
/db secsetup.sdb /verbose

REM Sets the Account Settings
secedit.exe /configure /db "XP Default Security.sdb" 
/cfg "Standalone-EC-Account.inf" /overwrite /quiet

REM Sets the Security Settings
secedit.exe /configure /db "XP Default Security.sdb" 
/cfg "EC-Desktop.inf"

REM Deletes the Shared Folder
reg delete "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\
MyComputer\NameSpace\DelegateFolders\
{59031a47-3f72-44a7-89c5-5595fe6b30ee}" /f

REM Updates the Local Policy
gpupdate.exe /force


```  
Nelle tabelle seguenti è incluso un elenco degli script e dei file associati forniti con la presente guida. Per ciascun ambiente esistono file per computer client desktop e portatili.
  
**Tabella 5.3 Script e file autonomi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nomi del file e dello script</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Standalone-EC-Desktop.cmd</td>
<td style="border:1px solid black;">Script autonomo utilizzato per impostare il criterio Enterprise Client nei computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Standalone-EC-Laptop.cmd</td>
<td style="border:1px solid black;">Script autonomo utilizzato per impostare il criterio Enterprise Client nei computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Standalone-SSLF-Desktop.cmd</td>
<td style="border:1px solid black;">Script autonomo utilizzato per impostare il criterio Specialized Security – Limited Functionality nei computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Standalone-SSLF-Laptop.cmd</td>
<td style="border:1px solid black;">Script autonomo utilizzato per impostare il criterio Specialized Security – Limited Functionality nei computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Standalone-EC-Account.inf</td>
<td style="border:1px solid black;">Modello del criterio di account Enterprise Client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Standalone-SSLF-Account.inf</td>
<td style="border:1px solid black;">Modello del criterio di account Specialized Security – Limited Functionality.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">EC-Desktop.inf</td>
<td style="border:1px solid black;">Modello di protezione Enterprise Client per i computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">EC-Laptop.inf</td>
<td style="border:1px solid black;">Modello di protezione Enterprise Client per i computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SSLF-Desktop.inf</td>
<td style="border:1px solid black;">Modello Specialized Security – Limited Functionality per computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SSLF-Laptop.inf</td>
<td style="border:1px solid black;">Modello Specialized Security – Limited Functionality per computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">XP Default Security.sdb</td>
<td style="border:1px solid black;">Database dei criteri predefiniti.</td>
</tr>
</tbody>
</table>
  
**Tabella 5.4 Script e file precedenti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nomi del file e dello script</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Legacy-EC-Desktop.cmd</td>
<td style="border:1px solid black;">Script precedente utilizzato per impostare il criterio Enterprise Client nei computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Legacy-EC-Laptop.cmd</td>
<td style="border:1px solid black;">Script precedente utilizzato per impostare il criterio Enterprise Client nei computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Legacy-SSLF-Desktop.cmd</td>
<td style="border:1px solid black;">Script precedente utilizzato per impostare il criterio Specialized Security – Limited Functionality nei computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Legacy-SSLF-Laptop.cmd</td>
<td style="border:1px solid black;">Script precedente utilizzato per impostare il criterio Specialized Security – Limited Functionality nei computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Legacy-EC-Account.inf</td>
<td style="border:1px solid black;">Modello precedente del criterio di account Client di organizzazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Legacy-SSLF-Account.inf</td>
<td style="border:1px solid black;">Modello precedente del criterio di account Specialized Security – Limited Functionality.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Legacy-EC-Desktop.inf</td>
<td style="border:1px solid black;">Modello precedente di protezione Enterprise Client per i computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Legacy-EC-Laptop.inf</td>
<td style="border:1px solid black;">Modello precedente di protezione Enterprise Client per i computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Legacy-SSLF-Desktop.inf</td>
<td style="border:1px solid black;">Modello precedente Specialized Security – Limited Functionality per computer client desktop.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Legacy-SSLF-Laptop.inf</td>
<td style="border:1px solid black;">Modello precedente Specialized Security – Limited Functionality per computer client portatili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">XP Default Security.sdb</td>
<td style="border:1px solid black;">Database dei criteri predefiniti.<br />
<strong>Nota</strong>: verificare che il database disponga dei privilegi di scrittura. Non è possibile impostarlo sulla modalità di sola lettura.</td>
</tr>
</tbody>
</table>
 

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

I criteri locali di Windows XP rappresentano un metodo estremamente utile per configurare impostazioni di criterio di protezione coerenti sui sistemi Windows XP che non appartengono a un dominio Active Directory. Per distribuire i criteri locali in modo efficiente, verificare la modalità di applicazione consentita, assicurarsi che tutti i computer client siano configurati con le impostazioni appropriate e che sia stata definita la protezione adatta per ogni computer dell'ambiente.

#### Ulteriori informazioni

I seguenti collegamenti forniscono ulteriori informazioni su argomenti relativi alla protezione di Windows XP Professional.

-   Per ulteriori informazioni sulla [gestione della configurazione della protezione](http://technet.microsoft.com/en-us/library/cc758219.aspx), vedere il sito www.microsoft.com/technet/prodtechnol/windowsserver2003/library/ServerHelp/
    74d8fed6-cf2f-4ba4-94f3-fc95bad914b0.mspx (in inglese).

-   Per ulteriori informazioni sui [Criteri di gruppo per Windows Server 2003](http://technet.microsoft.com/en-us/library/cc758751.aspx) vedere il sito www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/
    featured/gp/default.mspx (in inglese).

-   Per informazioni sulla risoluzione dei problemi dei Criteri di gruppo in Windows Server, consultare il white paper "[Troubleshooting Group Policy in Microsoft Windows Server](http://www.microsoft.com/downloads/details.aspx?familyid=b24bf2d5-0d7a-4fc5-a14d-e91d211c21b2&displaylang=en)" all'indirizzo
    www.microsoft.com/downloads/details.aspx?FamilyId=B24BF2D5-0D7A-4FC5-A14D-E91D211C21B2 (in inglese).

-   Per ulteriori informazioni sulla [risoluzione dei problemi relativi all'applicazione dei criteri di gruppo](http://support.microsoft.com/kb/250842.), vedere l'articolo 250842 della Knowledge Base all'indirizzo http://support.microsoft.com/default.aspx?scid=250842.

-   Per ulteriori informazioni sugli [Strumenti per la protezione](http://www.microsoft.com/technet/security/tools/) e sugli elenchi di controllo, vedere il sito www.microsoft.com/technet/security/tools/ (in inglese).

-   Per informazioni sull'[identificazione degli oggetti Criteri di gruppo in Active Directory e SYSVOL](http://support.microsoft.com/kb/216359.), vedere l'articolo della Knowledge Base 216359, all'indirizzo http://support.microsoft.com/default.aspx?scid=216359.

##### Download

[![](images/Cc163078.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)

[](#mainsection)[Inizio pagina](#mainsection)
