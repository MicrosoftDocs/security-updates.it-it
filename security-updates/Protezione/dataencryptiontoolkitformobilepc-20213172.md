---
TOCTitle: Data Encryption Toolkit for Mobile PC
Title: Data Encryption Toolkit for Mobile PC
ms:assetid: 'a69e5f04-8f25-43a6-86b9-e8279021d108'
ms:contentKeyID: 20213172
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162812(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione
======================================================================================

### Capitolo 2: Attività di configurazione e distribuzione

Prima di iniziare a distribuire Crittografia unità Microsoft BitLocker (BitLocker) ed EFS (Encrypting File System), è necessario effettuare una serie di attività di configurazione preliminari per preparare l'ambiente. Le attività descritte in questo capitolo facilitano la preparazione della rete e del servizio Active Directory nonché la distribuzione di BitLocker ed EFS sui computer client.

Sia EFS che BitLocker possono usufruire di Active Directory per applicare impostazioni di configurazione coerenti su più computer. Le impostazioni disponibili per ogni tecnologia presentano qualche differenza. Tuttavia, poiché entrambe le tecnologie possono essere controllate dagli oggetti Criteri di gruppo (GPO) di Active Directory, considerare il modo in cui la progettazione di Active Directory può essere sfruttata per applicare la protezione appropriata ai computer, in base alla loro posizione, allo scopo per cui vengono utilizzati e a chi li utilizza.

In questo capitolo vengono descritte le seguenti attività:

-   Scelta di una configurazione BitLocker per proteggere i dati riservati.

-   Utilizzo dei controlli di Criteri di gruppo di Active Directory per verificare il funzionamento del backup della chiave BitLocker, l'impostazione, la crittografia del disco e l'interazione con TPM (Trusted Platform Module).

-   Utilizzo di Active Directory per controllare la crittografia EFS e la gestione dei certificati.

-   Preparazione dei computer client all'utilizzo di BitLocker con la configurazione selezionata.

-   Abilitazione di BitLocker sui computer client

-   Configurazione di Microsoft Encrypting File System Assistant (EFS Assistant) per l'utilizzo con EFS su computer aggiunti al dominio.

-   Importazione dei modelli amministrativi per la personalizzazione degli strumenti di amministrazione disponibili per EFS.

-   Configurazione degli agenti di recupero dati per EFS.

##### In questa pagina

[](#edaa)[Attività di preparazione dell'infrastruttura](#edaa)
[](#ecaa)[Attività di configurazione per computer](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### Attività di preparazione dell'infrastruttura

Sia BitLocker che EFS richiedono una preparazione dell'infrastruttura prima di poter essere distribuiti nell'ambiente. Le attività descritte in questa sezione, in genere, devono essere eseguite una sola volta prima della distribuzione e, solitamente, non devono essere ripetute.

#### Preparazione dell'infrastruttura per BitLocker

La preparazione dell'infrastruttura a BitLocker consta di due operazioni:

-   Configurazione delle opzioni BitLocker attraverso i Criteri di gruppo di Active Directory

-   Preparazione dell'infrastruttura di Active Directory per consentire l'archiviazione delle chiavi di ripristino di BitLocker

##### Configurazione delle opzioni BitLocker con Criteri di gruppo

Windows Vista offre una serie di impostazioni di controllo di BitLocker che è possibile utilizzare per controllare la disponibilità e il funzionamento di BitLocker sui computer client. È possibile controllare queste impostazioni creando i GPO di Active Directory tramite il set di strumenti di gestione standard GPO di Windows Server e i modelli amministrativi di Windows Vista. Per ulteriori informazioni su questi strumenti, consultare la guida online di Windows Server 2003.

Poiché i GPO possono essere applicati a singoli computer o a siti, domini e unità organizzative (OU) di Active Directory, è possibile adottare una certa flessibilità nel decidere come assegnare le impostazioni di BitLocker ai computer dell'organizzazione. È possibile:

-   Assegnare le impostazioni a singoli computer modificando il GPO del computer locale.

-   Raggruppare i computer con funzionalità simili in una OU, quindi assegnare impostazioni di BitLocker univoche esclusivamente a questa OU. Ad esempio, è possibile creare una OU separata per tutti i PC portatili oppure esclusivamente per quelli che appartengono a collaboratori che fanno parte di determinati reparti aziendali o che ricoprono determinati ruoli lavorativi.

-   Applicare i criteri di BitLocker a tutti i computer in un dominio o in una foresta. Questo approccio fornisce una semplice implementazione della crittografia a livello aziendale su computer con Windows Vista. I computer su cui sono in esecuzione altre versioni di Windows ignoreranno le impostazioni specifiche di BitLocker.

##### Preparazione per l'archiviazione della chiave di Active Directory

Per attivare l'archiviazione delle password del proprietario del TPM e i dati di ripristino del volume di BitLocker in Active Directory, è necessario effettuare le seguenti operazioni. Queste operazioni richiedono che su tutti i controller di dominio accessibili ai client BitLocker sia in esecuzione Windows Server 2003 Service Pack 1 (SP1) o versione successiva.

1.  Estendere lo schema Active Directory.

2.  Impostare le autorizzazioni sugli oggetti dello schema delle informazioni di ripristino di BitLocker e TPM.

3.  Configurare un GPO affinché attivi il backup Active Directory delle informazioni chiave di BitLocker.

4.  Configurare un GPO affinché attivi il backup Active Directory delle informazioni sulla password del proprietario del TPM.

Le procedure dettagliate per effettuare queste operazioni vengono descritte nella guida [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information](http://go.microsoft.com/fwlink/?linkid=67438) (in inglese).

Dopo aver completato le operazioni precedentemente descritte, è possibile delegare l'accesso di ripristino ad altre persone nell'organizzazione.

**Per delegare l'accesso di ripristino**

1.  Creare o identificare un gruppo di protezione di Active Directory che contenga gli account utente a cui si desidera delegare l'accesso.

2.  Aggiungere una voce di controllo di accesso (ACE) all'elenco di controllo di accesso discrezionale (ACL) per il dominio o l'unità organizzativa (OU) che contiene i computer a cui si desidera delegare l'accesso. L'ACE deve concedere le autorizzazioni per il controllo dell'accesso e per la proprietà di lettura all'oggetto del computer, il pacchetto di chiavi e l'oggetto delle informazioni di ripristino di BitLocker.

3.  Per attivare il ripristino delle informazioni del TPM, è possibile adottare lo stesso metodo utilizzato per concedere le autorizzazioni per il controllo dell'accesso e per la proprietà di lettura all'oggetto delle informazioni del proprietario del TPM.

Durante questo processo, è possibile concedere l'accesso alle informazioni di ripristino di BitLocker e TPM a due gruppi di utenti separati. Questo approccio consente di mantenere la separazione dei compiti per l'accesso alle informazioni di ripristino.

#### Preparazione dell'infrastruttura per EFS

Per utilizzare efficacemente EFS, è necessario completare le seguenti attività di preparazione dell'infrastruttura:

1.  Preparare Active Directory e creare gli oggetti di Criteri di gruppo

2.  Gestire e configurare gli agenti di recupero dati

3.  Gestire e configurare gli agenti di recupero chiavi

##### Preparare Active Directory e creare gli oggetti di Criteri di gruppo

In questa sezione della guida vengono descritte le attività di configurazione necessarie alla preparazione dell'ambiente Active Directory per supportare EFS. Se queste attività non vengono eseguite, i singoli computer client su cui è in esecuzione Windows XP o Windows Vista potranno utilizzare EFS, ma non sarà possibile gestire e controllare centralmente la funzionalità di EFS.

###### Controllare le impostazioni di crittografia EFS

Windows Vista e Windows XP offrono una serie di impostazioni che è possibile utilizzare per controllare la disponibilità e il funzionamento di EFS sui computer client. Per controllare queste impostazioni, creare i GPO di Active Directory tramite il set di strumenti di gestione standard GPO di Windows Server. Per ulteriori informazioni su questi strumenti, consultare la guida online di Windows Server 2003.

Poiché i GPO possono essere applicati a singoli computer o a siti, domini e unità organizzative (OU) di Active Directory, è possibile adottare una certa flessibilità nel decidere come assegnare le impostazioni di EFS ai computer dell'organizzazione. È possibile:

-   Assegnare le impostazioni a singoli computer modificando il GPO del computer locale.

-   Raggruppare i computer con funzioni simili in una OU, quindi assegnare impostazioni EFS univoche esclusivamente a questa OU. Ad esempio, è possibile creare una OU separata per tutti i PC portatili oppure solo per quelli che appartengono a collaboratori che fanno parte di determinati reparti aziendali o che ricoprono determinati ruoli lavorativi.

-   Applicare i criteri di EFS a tutti i computer in un dominio o in una foresta. Questo approccio può essere utilizzato insieme a EFS Assistant per fornire una semplice implementazione della crittografia a livello aziendale sia su computer con Windows XP che con Windows Vista.

###### Impostazioni di EFS comuni a Windows Vista e Windows XP

Il modello di GPO di Active Directory consente di controllare diverse impostazioni relative a EFS, elencate e descritte nella seguente tabella. Per ulteriori informazioni, consultare le guide alla protezione di Windows XP e Windows Vista.

**Tabella 2.1. Impostazioni di EFS del modello di GPO di Active Directory**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome impostazione</th>
<th style="border:1px solid black;" >Disponibilità</th>
<th style="border:1px solid black;" >Valore predefinito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Abilitazione EFS</td>
<td style="border:1px solid black;">Windows XP,Windows Vista</td>
<td style="border:1px solid black;">Consentito</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia documenti</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">Disattivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Richiedi smart card</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">Disattivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crea da smart card una chiave utente in grado di memorizzare nella cache</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">Disattivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Abilita crittografia del file di paging</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">Disattivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Registrazione automatica dei certificati</td>
<td style="border:1px solid black;">Windows XP,Windows Vista</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Dimensioni della chiave per i certificati autofirmati</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">2048 bit</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modello EFS per le richieste automatiche di certificati</td>
<td style="border:1px solid black;">Windows Vista</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
</tbody>
</table>
  
**Attivazione e disattivazione di EFS**
  
A causa del serio rischio di perdere le chiavi (e quindi di perdere l'accesso ai file crittografati) che si corre disponendo solo di EFS, alcune organizzazioni decidono di disattivare EFS fino a quando non sia possibile implementare un'autorità di certificazione globale (enterprise) ed EFS basato su dominio. È possibile disattivare o attivare l'utilizzo di EFS modificando lo stato della casella di controllo **Consenti agli utenti di crittografare i file utilizzando Crittografia file system (EFS)** nelle proprietà dell'oggetto EFS in un GPO. L'oggetto EFS si trova nel seguente percorso: **Configurazione computer\\Impostazioni Windows\\Impostazioni protezione\\Criteri chiave pubblica**.
  
Se l'organizzazione aveva precedentemente disattivato EFS tramite un GPO, è necessario modificare il GPO per attivare EFS. Se EFS è stato disattivato tramite i criteri locali o le modifiche al Registro di sistema, è necessario rimuovere i criteri locali o utilizzare l'editor del Registro di sistema per attivare EFS. Per attivare EFS utilizzando il Registro di sistema, cercare un valore DWORD denominato **EfsConfiguration** nel Registro di sistema, nella chiave **HKLM\\SOFTWARE\\Microsoft\\WindowsNT\\CurrentVersion\\EFS**. Per disattivare EFS, modificare il valore in 1. Per attivarlo, modificare il valore in 0. Tenere presente che questa modifica viene applicata esclusivamente al computer locale e non agli altri computer nel dominio.
  
**Supporto di algoritmi di crittografia aggiuntivi**
  
Se, durante la fase di pianificazione, è stato determinato che la distribuzione di EFS deve essere conforme agli standard statunitensi Federal Information Processing Standards (FIPS) 140-1, è necessario attivare FIPS modificando l'opzione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma** in Criterio locale o Criteri di gruppo in Active Directory. Questa opzione si trova nel seguente percorso: **Configurazione computer\\Impostazioni Windows\\Impostazioni protezione\\Criteri locali\\Opzioni di protezione**.
  
Se deve essere utilizzato un altro algoritmo di crittografia (per ragioni diverse dalla compatibilità con i FIPS), dovrebbero essere utilizzati i Criteri di gruppo per modificare **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS** sui computer client per cui è richiesto.
  
###### Opzioni EFS specifiche di Windows Vista
  
Windows Vista contiene numerose nuove opzioni di Criteri di gruppo che consentono agli amministratori di definire e implementare i criteri organizzativi di EFS. Tali opzioni includono la possibilità di richiedere smart card per EFS, applicare la crittografia del file di paging, stabilire le lunghezze minime delle chiavi per EFS e applicare la crittografia della cartella Documenti dell'utente. Per accedere a queste opzioni, modificare l'oggetto EFS in un GPO (il percorso dell'oggetto è il seguente: **Configurazione computer\\Impostazioni Windows\\Impostazioni protezione\\Criteri chiave pubblica**.)
  
![](images/Cc162812.1a71105c-d527-4302-a6e6-db91d08078a4(it-it,TechNet.10).gif)
  
**Figura 2.1. Opzioni delle proprietà di crittografia del file system di Windows Vista**
  
###### Controllare la registrazione automatica dei certificati
  
Windows XP Professional e Windows Vista abilitano gli utenti alla registrazione automatica dei certificati dell'utente all'accesso. La registrazione automatica dei certificati dell'utente è rapida e semplice e attiva le applicazioni dell'infrastruttura a chiave pubblica (accesso con smart card, EFS, SSL, S/MIME e altre) in un ambiente Active Directory. La registrazione automatica dell'utente riduce al minimo i costi elevati delle tipiche distribuzioni dell'infrastruttura a chiave pubblica (PKI). Per attivare la registrazione automatica dei certificati, è necessario creare un modello di certificato appropriato in Active Directory. Utilizzare lo snap-in Microsoft Management Console (MMC) dei modelli di certificato per aggiungere un modello di certificato appropriato. Per ulteriori informazioni, fare riferimento all'articolo "[Certificate Autoenrollment in Windows XP](http://technet.microsoft.com/en-us/library/bb456981.aspx)" (in inglese).
  
##### Gestire e configurare gli agenti di recupero dati
  
Microsoft consiglia alle organizzazioni di definire almeno un agente di recupero dati (DRA) da utilizzare con EFS. I DRA possono essere account amministrativi di rete regolari, ma Microsoft suggerisce di utilizzare account dedicati utilizzati esclusivamente per le attività di ripristino. I criteri dell'organizzazione o i requisiti legali possono specificare ulteriori requisiti, inclusi il controllo e la separazione degli accessi. Il rispetto di questi requisiti può comportare la definizione di DRA separati per diversi gruppi, organizzazioni, funzioni lavorative o altre suddivisioni della rete dell'organizzazione.
  
La gestione del DRA comprende le seguenti attività, dettagliatamente descritte nelle sottosezioni che seguono:
  
-   Creare gli account utente di DRA
  
-   Creare e popolare i gruppi di protezione per i DRA
  
-   Configurare la CA per emettere i certificati DRA
  
-   Richiedere i certificati DRA
  
-   Approvare le richieste di certificati DRA di EFS
  
-   Definire un criterio di recupero dati (operazione di pianificazione descritta nel Capitolo 1)
  
-   Esportare il certificato per l'assegnazione di un criterio
  
-   Definire un agente di recupero dati
  
###### Creare account utente di DRA
  
La procedura migliore per la gestione degli account utente di DRA consiste nel creare account utente separati utilizzati esclusivamente per il recupero dati, poiché questo approccio consente di ridurre il rischio che un utente privilegiato recuperi dati in modo errato. Gli account utente di DRA dedicati sono account ordinari a cui vengono concessi privilegi di recupero.
  
**Per creare account utente di DRA**
  
1.  Aprire Utenti e computer di Active Directory.
  
2.  Nell'albero della console, fare clic con il pulsante destro del mouse sulla cartella in cui si desidera aggiungere un account utente. (Utenti e computer di Active Directory/nodo del dominio/cartella)
  
3.  Selezionare **Nuovo**, quindi scegliere **Utente**.
  
4.  Assegnare un nome all'account. Anziché utilizzare un nome utente individuale, è opportuno identificare l'account per ruolo (ad esempio, HR DRA o Engineering DRA).
  
5.  In **Nome accesso utente**, immettere il nome di accesso utente, fare clic sul suffisso UPN nell'elenco a discesa e scegliere **Avanti**.
  
6.  In **Password e Conferma password**, digitare la password dell'utente e selezionare le opzioni appropriate per la password.
  
7.  Scegliere **OK**.
  
8.  Ripetere le operazioni da 3 a 7 per ogni ulteriore DRA che si desidera creare.
  
###### Creazione di gruppi di protezione per i DRA
  
Microsoft suggerisce di creare un gruppo di protezione di Active Directory per ogni gruppo di DRA da utilizzare. Questo approccio consente di controllare efficacemente quali utenti hanno accesso al recupero dati dai vari settori dell'organizzazione.
  
**Per creare gruppi di protezione per i DRA**
  
1.  Aprire Utenti e computer di Active Directory.
  
2.  Fare clic con il pulsante destro del mouse su **Utenti**, scegliere **Nuovo**, selezionare **Gruppo**, digitare **Agenti di recupero dati del dominio** (o un altro nome appropriato), quindi scegliere **OK**.
  
3.  Per aggiungere utenti a questo gruppo, fare clic con il pulsante destro del mouse su **Agenti di recupero dati del dominio** sotto la OU **Utenti**, selezionare **Proprietà** e scegliere la scheda **Membri**. Selezionare gli utenti che si desidera aggiungere a questo gruppo, quindi scegliere **OK**.
  
4.  Ripetere i passaggi 2 e 3 per ogni gruppo di DRA aggiuntivo.
  
###### Configurazione della CA per emettere i certificati DRA
  
È necessario configurare la CA per emettere i certificati utilizzando un modello che comprenda indicatori di utilizzo della chiave per il ripristino EFS. I passaggi riportati di seguito descrivono come configurare i Servizi certificati Microsoft per emettere i certificati digitali DRA di EFS. È possibile utilizzare altre CA compatibili per l'emissione dei certificati DRA di EFS, ma in questa guida non vengono fornite istruzioni per i servizi di CA di terze parti.
  
**Per configurare i Servizi certificati per l'emissione dei certificati di ripristino di EFS**
  
1.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.
  
2.  Aprire la console di CA cercando un server autorizzato dei Servizi certificati. A tal fine, fare clic su **Start**, selezionare **Tutti i programmi**, scegliere **Strumenti di amministrazione**, quindi selezionare **Autorità di certificazione**.
  
3.  Espandere l'oggetto server di Autorità di certificazione per visualizzarne i componenti.
  
4.  Fare clic con il pulsante destro del mouse sul nodo **Modelli di certificati** e selezionare **Gestisci** per aprire la console Modelli di certificato, come mostrato nella figura che segue.
  
    ![](images/Cc162812.5d9e236e-785e-454c-983f-216b50dcce52(it-it,TechNet.10).gif)
  
    **Figura 2.2. Modelli di certificati nella console Autorità di certificazione**
  
5.  Il certificato digitale utilizzato per emettere i certificati per l'agente di recupero EFS non consente che venga modificata la dimensione della chiave predefinita di 1024 bit. È necessario effettuare una copia del modello integrato e configurare in modo appropriato la copia risultante del certificato per l'agente di recupero EFS.
  
    Fare clic con il pulsante destro del mouse sul modello di certificato **Agente di recupero dati EFS** e selezionare **Duplica modello**.
  
6.  Assegnare un nuovo nome al nuovo modello di certificato (ad esempio, **Agente di recupero dati di EFS aggiornato**) per differenziarlo dal modello standard.
  
7.  Fare clic sulla scheda **Gestione richiesta** e configurare l'opzione corrispondente alla lunghezza della chiave desiderata in modo che sia 2048 bit o maggiore.
  
8.  Fare clic sulla scheda **Protezione** e assicurarsi che gli account utente che si desidera rendere agenti di recupero dati di EFS dispongano delle autorizzazioni **Lettura** e **Registrazione**.
  
9.  Scegliere **OK**.
  
10. Aprire la finestra di dialogo delle proprietà del modello di certificato per l'agente di recupero di EFS, scegliere la scheda **Protezione** e impostare l'autorizzazione **Nega-Registrazione** per tutti gli utenti. Scegliere **OK**.
  
11. Passare alla console di Autorità di certificazione e fare clic con il pulsante destro del mouse sull'oggetto **Modelli di certificati**, selezionare **Nuovo**, quindi **Modello di certificato da emettere**.
  
12. Selezionare il nuovo certificato, più valido, per l'agente di recupero dati di EFS e scegliere **OK**.
  
13. Chiudere la console di Autorità di certificazione.
  
14. Fare in modo che tutti gli agenti di recupero dati di EFS esistenti richiedano nuovi certificati digitali utilizzando i nuovi, più validi modelli di certificati per l'agente di recupero di EFS.
  
15. Approvare ed emettere i nuovi certificati per l'agente di recupero dati di EFS.
  
16. Accertarsi che le nuove chiavi private per l'agente di recupero dati di EFS (i file che hanno estensioni .PFX) siano archiviate o ne venga effettuato il backup in due o più posti separati e sicuri, quindi eliminarle dal computer locale fino a quando non saranno necessarie per il recupero.
  
**Nota**   Tutti i certificati KRA e DRA di EFS devono essere emessi dal certificato appena configurato o avranno l'impostazione originale di lunghezza della chiave.
  
Per le organizzazioni che hanno precedentemente distribuito EFS e gli agenti di recupero dati di EFS che utilizzano il modello standard, i file già crittografati con l'agente di recupero dati di EFS più debole devono essere crittografati con il nuovo certificato per l'agente di recupero dati di EFS più potente. Questo processo avverrà automaticamente, su base file per file, quando i singoli file vengono modificati.
  
È possibile configurare EFS in modo che aggiorni tutti i file crittografati sulle unità locali contemporaneamente aprendo il prompt dei comandi, digitando **Cipher.exe /U** e premendo INVIO.
  
Una volta ricrittografati tutti i file crittografati con il nuovo certificato per l'agente di recupero dati di EFS e dopo essersi assicurati di disporre di copie di backup della chiave per l'agente di recupero dati originale di EFS più debole in due o più posti separati e protetti, è possibile eliminare la chiave di recupero dati originale nell'oggetto Modelli di certificati, nella console Autorità di certificazione.
  
###### Richiesta di certificati DRA per singoli utenti
  
Nei casi in cui sono necessari molteplici agenti di recupero dati per il dominio o in cui l'agente di recupero dati deve essere diverso dall'amministratore del dominio per ragioni legali o per criteri organizzativi, potrebbe essere necessario identificare alcuni utenti come agenti di recupero dati. A tali utenti devono essere emessi certificati di recupero dati del file.
  
L'emissione di questi certificati richiede quanto segue:
  
-   Disponibilità di una CA aziendale.
  
-   Il criterio sulla CA aziendale deve consentire agli agenti/utenti designati di richiedere e ottenere un certificato di recupero dati del file.
  
-   Ogni utente deve richiedere un certificato di recupero dati del file.
  
Questo processo può essere automatizzato attivando la registrazione automatica dei certificati o può essere eseguito manualmente completando le operazioni della procedura seguente:
  
**Per creare un certificato per l'agente di recupero dati di EFS**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi scegliere **OK**.
  
2.  Nel menu **File**, selezionare **Aggiungi/Rimuovi snap-in**, quindi scegliere **Aggiungi**.
  
3.  Fare doppio clic su **Certificati**, selezionare **Account dell'utente**, quindi scegliere **Fine**. Scegliere **Chiudi**, quindi **OK**.
  
4.  Fare clic sul segno di addizione (**+**) vicino a **Certificati - Utente corrente** per espandere la cartella.
  
5.  Fare clic con il pulsante destro del mouse su **Personale** nel riquadro di sinistra, scegliere **Tutte le attività** e selezionare **Richiedi nuovo certificato** per avviare la procedura guidata di richiesta del certificato.
  
6.  La prima pagina della procedura guidata contiene informazioni. Fare clic su **Avanti** per continuare.
  
7.  Viene visualizzato un elenco di modelli di certificati. Selezionare **Agente di recupero dati di EFS**, quindi scegliere **Avanti**.
  
8.  Digitare un nome semplice per distinguere questo certificato dagli altri e, se si desidera, aggiungere una descrizione. Fare clic su **Avanti**, quindi scegliere **Fine** per richiedere il certificato.
  
9.  Selezionare **OK** per confermare la correttezza della richiesta di certificato.
  
Per creare un criterio di ripristino EFS a livello del dominio, il certificato per l'agente di recupero dati di EFS creato precedentemente deve essere esportato in formato .CER.
  
###### Approvazione delle richieste di certificati DRA di EFS
  
In genere, le richieste di certificati DRA di EFS devono essere approvate manualmente in Servizi certificati.
  
**Per esaminare e approvare le richieste DRA inviate al server di Servizi certificati Microsoft**
  
1.  Accedere a Windows con un account utente a cui è consentito approvare le richieste di certificati digitali in Servizi certificati.
  
2.  Aprire la console di CA cercando un server autorizzato dei Servizi certificati. A tal fine, fare clic su **Start**, selezionare **Tutti i programmi**, scegliere **Strumenti di amministrazione**, quindi selezionare **Autorità di certificazione**.
  
3.  Espandere il server di Autorità di certificazione per visualizzarne i componenti.
  
4.  Scegliere **Richieste in sospeso**. Nel riquadro di destra verrà visualizzato un elenco delle richieste di certificati in sospeso, in attesa di approvazione.
  
5.  Individuare le richieste di certificati per l'agente di recupero dati di EFS appropriate, fare clic con il pulsante destro del mouse su di esse e selezionare **Emetti**. Dopo aver terminato l'operazione, chiudere la console di Autorità di certificazione.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
Se si utilizza un modello di certificato che necessita dell'approvazione del responsabile e si richiede manualmente un certificato utilizzando tale modello, la richiesta potrebbe non andare a buon fine. In questo caso, è necessario modificare il modello per rimuovere il requisito di approvazione del responsabile o creare una nuova richiesta utilizzando un modello diverso.
  
###### Esportazione dei certificati per l'assegnazione a un criterio
  
Dopo aver assegnato un certificato DRA a un singolo utente, è necessario esportare tale certificato affinché possa essere allegato a un oggetto Criteri di gruppo per l'assegnazione come un criterio di ripristino.
  
**Per esportare un certificato per l'assegnazione a un GPO**
  
1.  Nella console Certificati, espandere la cartella **Personale**.
  
2.  Nel riquadro di destra, fare clic con il pulsante destro del mouse sul certificato appena creato, selezionare **Tutte le attività**, quindi scegliere **Esporta**. Fare clic su **Avanti** per avviare il processo di esportazione.
  
3.  Seleziona la casella di controllo **Non esportare la chiave privata**, quindi scegliere **Avanti**.
  
4.  Lasciare il formato del file .cer predefinito e scegliere **Avanti**.
  
5.  Fornire un percorso e un nome per il file, quindi scegliere **Avanti**.
  
6.  Per eseguire l'esportazione, scegliere **Fine**, quindi **OK**.
  
7.  Chiudere la console Certificati.
  
###### Definizione di un agente di recupero dati
  
I DRA vengono definiti modificando l'oggetto Criteri chiave pubblica in un oggetto Criteri di gruppo, aggiungendo un DRA e collegando il certificato dei DRA al DRA. A tal fine, il certificato del DRA deve essere in formato .CER.
  
**Per definire un DRA**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **mmc**, quindi scegliere **OK**.
  
2.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**.
  
3.  Scegliere **Aggiungi**, scorrere verso il basso e quindi fare doppio clic su **Criteri** **di gruppo**.
  
4.  Selezionare l'oggetto Criteri di gruppo che si sta utilizzando per applicare il criterio DRA ai computer interessati, quindi scegliere **OK**.
  
5.  Selezionare il segno di addizione (**+**) vicino al GPO di destinazione per espandere l'albero. Espandere **Configurazione computer**, **Impostazioni Windows**, **Impostazioni protezione** e **Criteri chiave pubblica**. Selezionare **Encrypting File System**.
  
6.  Fare clic con il pulsante destro del mouse su **Encrypting File System** e scegliere **Aggiungi agente recupero dati**.
  
7.  Nella schermata dell**'Aggiunta guidata agente recupero dati**, scegliere **Avanti**, **Sfoglia cartelle** e andare alla cartella **Documents and Settings**. Fare doppio clic sul file **DRA.CER**, quindi selezionare **Avanti** e scegliere **Fine**.
  
##### Gestire e configurare gli agenti di recupero chiavi
  
L'attività di implementazione successiva richiesta per la distribuzione di EFS consiste nell'impostare gli account per l'agente di recupero chiavi (KRA) e l'infrastruttura.
  
###### Configurazione di Servizi certificati per l'archiviazione delle chiavi
  
Se si utilizza la soluzione Servizi certificati di Windows Server 2003, è possibile configurare la CA affinché fornisca l'archiviazione automatica delle chiavi. Solo Windows Server 2003 e le edizioni di server successive consentono l'archiviazione automatica delle chiavi. Per configurare l'archiviazione automatica delle chiavi, è necessario completare le seguenti attività, descritte dettagliatamente nelle sottosezioni che seguono:
  
-   Abilitare i certificati per l'agente di recupero chiavi
  
-   Richiedere ed emettere certificati per l'agente di recupero chiavi
  
-   Approvare le richieste di certificati
  
-   Configurare gli agenti di recupero chiavi in Servizi certificati
  
-   Configurare il modello di certificato digitale in modo che includa un indicatore di capacità di archiviazione affinché i nuovi certificati emessi possano essere archiviati.
  
**Abilitazione dei certificati per l'agente di recupero chiavi**
  
Per rendere possibili le richieste di certificati per l'agente di recupero chiavi, è necessario abilitarle prima in Servizi certificati.
  
**Per rendere possibili le richieste di certificati KRA**
  
1.  Scegliere uno o più account utente che diventeranno agenti di recupero chiavi.
  
2.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.
  
3.  Aprire la console di Autorità di certificazione (**Start**, **Tutti i programmi**, **Strumenti di amministrazione**, **Autorità di certificazione**) e creare un collegamento a un server Servizi certificati autorizzato.
  
4.  Espandere il nodo **Autorità di certificazione**, quindi fare clic con il pulsante destro del mouse sull'oggetto **Modelli di certificati** e selezionare **Gestisci** per aprire la console di Modelli di certificati.
  
5.  Fare clic con il pulsante destro del mouse sul modello di certificato **Agente di recupero chiavi** e selezionare **Proprietà**.
  
6.  Scegliere la scheda **Protezione** e assicurarsi che gli account utente che si desidera designare come KRA (quelli scelti nel passaggio 1) abbiano le autorizzazioni **Lettura** e **Registrazione**.
  
7.  Nella scheda **Gestione richiesta**, assicurarsi che **Dimensioni minime chiave** sia impostato su 2048 bit o su un valore più grande.
  
    ![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
    Microsoft consiglia che tutte le chiavi di ripristino DRA e KRA siano impostate su 2048 bit o su un valore più grande.
  
8.  Scegliere **OK** .
  
9.  Se vengono ancora generate e utilizzate chiavi da 1024 bit o valore inferiore, è necessario creare chiavi più lunghe per sostituire quelle più deboli. Fare clic con il pulsante destro del mouse sul modello di certificato **Agente di recupero chiavi** e selezionare l'opzione **Registra nuovamente tutti i possessori di certificati**.
  
10. Passare alla console di Autorità di certificazione e fare clic con il pulsante destro del mouse sull'oggetto **Modelli di certificati**, selezionare **Nuovo**, quindi **Modello di certificato da emettere**.
  
11. Selezionare **Certificato per l'agente di recupero chiavi** e scegliere **OK**.
  
12. Chiudere le console di Modelli di certificati e Autorità di certificazione.
  
**Richiesta ed emissione dei certificati per l'agente di recupero chiavi**
  
Dopo aver abilitato account specifici all'utilizzo come KRA, è necessario emettere certificati abilitati a KRA per questi utenti.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
Esistono diversi modi per richiedere certificati per l'agente di recupero chiavi, ad esempio tramite la console Certificati, la registrazione su Web (se abilitata) o l'utilizzo di file di richiesta certificati manuali. In questa guida viene descritto il metodo della console Certificati.
  
**Per emettere certificati abilitati a KRA**
  
1.  Accedere a Windows utilizzando l'accesso e la password dell'account utente KRA.
  
2.  Fare clic su **Start**, **Esegui**, digitare **MMC.EXE** e premere INVIO. Selezionare **Continua** se richiesto dal Controllo dell'account utente.
  
3.  Fare clic sull'opzione del menu **File** e scegliere **Aggiungi/Rimuovi snap-in**.
  
4.  Selezionare lo snap-in **certificati** e scegliere **Aggiungi**.
  
5.  Quando viene richiesto, scegliere **Account dell'utente**, **Fine**, quindi **OK**.
  
6.  Espandere l'oggetto **Certificati - Utente corrente** e scegliere l'oggetto **Personale**.
  
7.  Fare clic con il pulsante destro del mouse su **Personale**, selezionare **Tutte le attività**, quindi **Richiedi nuovo certificato**.
  
8.  Scegliere **Avanti** nella schermata della procedura guidata di richiesta certificati.
  
9.  Selezionare **Agente di recupero chiavi** nella finestra di dialogo **Tipo certificato** e scegliere **Avanti**.
  
10. Immettere un nome semplice (ad esempio, **Certificato per l'agente di recupero chiavi**) e una descrizione, scegliere **Avanti**, quindi **Fine**.
  
11. Una volta terminate le operazioni, chiudere la console Certificati.
  
12. Uscire da Windows.
  
Ripetere le operazioni da 1 a 12 per tutti gli utenti autorizzati a ricevere un certificato per l'agente di recupero chiavi.
  
**Approvazione delle richieste di certificati**
  
In genere, i certificati KRA devono essere approvati manualmente in Servizi certificati.
  
**Per approvare le richieste di certificati KRA**
  
1.  Accedere a Windows con un account utente a cui è consentito approvare le richieste di certificati digitali in Servizi certificati.
  
2.  Aprire la console di Autorità di certificazione e creare un collegamento a un server di Servizi certificati autorizzato.
  
3.  Espandere il nodo **Autorità di certificazione**, quindi scegliere **Richieste in sospeso**. Nel riquadro di destra verranno visualizzate le richieste di certificati in sospeso, in attesa di approvazione.
  
4.  Selezionare le richieste di certificati KRA che si desidera approvare.
  
5.  Fare clic con il pulsante destro del mouse su ogni richiesta di KRA e selezionare **Emetti**.
  
6.  Chiudere la console di Autorità di certificazione.
  
**Configurazione degli agenti di recupero chiavi in Servizi certificati**
  
Ogni agente di recupero chiavi deve essere aggiunto a Servizi certificati.
  
**Per aggiungere KRA a Servizi certificati**
  
1.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.
  
2.  Aprire la console di Autorità di certificazione e creare un collegamento a un server di Servizi certificati autorizzato.
  
3.  Fare clic con il pulsante destro del mouse sull'oggetto server e selezionare **Proprietà**.
  
4.  Scegliere la scheda **Agenti di recupero** (mostrata nella seguente schermata).
  
    ![](images/Cc162812.57b5ad90-e987-4a94-b282-f8ebe8ff066d(it-it,TechNet.10).gif)
  
    **Figura 2.3. La scheda Agenti di recupero per un oggetto server nella console di Autorità di certificazione**
  
5.  Nella casella **Numero di agenti di recupero dati da utilizzare**, digitare il numero di agenti di recupero chiavi che verranno utilizzati per crittografare la chiave archiviata. Questo valore deve essere di almeno 1. Tuttavia, se supera il numero di certificati per l'agente di recupero dati con stato "Valido", le nuove richieste di registrazione che necessitano dell'archiviazione della chiave avranno esito negativo.
  
6.  Scegliere **Aggiungi** per aggiungere almeno uno dei KRA precedentemente approvati. Quindi, scegliere **OK**.
  
7.  Selezionare **Sì** quando richiesto, per arrestare e riavviare Servizi certificati. I nuovi agenti di recupero chiavi non verranno caricati fino a quando Servizi certificati non verrà arrestato e avviato.
  
8.  Una volta terminate le operazioni, chiudere la console di Autorità di certificazione.
  
**Creazione del nuovo modello di certificati EFS per consentire l'archiviazione delle chiavi**
  
Il certificato digitale utilizzato per emettere i certificati digitali EFS agli utenti deve essere configurato in modo da archiviare automaticamente le chiavi. Non è possibile attivare questa opzione sul modello di certificato EFS di base integrato. Sarà necessario copiare il modello integrato, quindi attivare la copia del modello di certificato EFS per automatizzare l'archiviazione delle chiavi.
  
**Per configurare un certificato digitale in modo che archivi automaticamente le chiavi**
  
1.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.
  
2.  Aprire la console di Autorità di certificazione e creare un collegamento a un server di Servizi certificati autorizzato.
  
3.  Espandere il nodo **Autorità di certificazione**, quindi fare clic con il pulsante destro del mouse sul nodo **Modelli di** **certificati** e selezionare **Gestisci** per aprire la console di Modelli di certificati.
  
4.  Fare clic con il pulsante destro del mouse sul modello di certificato **EFS di base** e selezionare **Duplica modello**.
  
5.  Assegnare un nome al nuovo modello di certificato (ad esempio, EFS di base aggiornato) per differenziarlo dal modello standard.
  
6.  Scegliere la scheda **Gestione richiesta** e selezionare la casella di controllo **Archivia chiave privata di crittografia del soggetto**, come mostrato nella schermata che segue.
  
    ![](images/Cc162812.c10c48ea-8cdd-4057-8b41-760fa2df9665(it-it,TechNet.10).gif)
  
    **Figura 2.4. Finestra di dialogo Proprietà del nuovo modello nella console di Autorità di certificazione**
  
7.  Impostare la lunghezza della chiave desiderata (ad esempio, 2048 bit).
  
8.  Scegliere la scheda **Protezione** e assicurarsi che gli account utente desiderati partecipino a EFS dispongano delle autorizzazioni **Lettura** e **Registrazione**.
  
9.  Impostare le altre opzioni del modello di certificato, come la registrazione automatica, il periodo di vita utile, ecc., come desiderato.
  
10. Nel modello di **certificato EFS di base** originale, scegliere la scheda **Protezione** e creare una nuova voce di controllo accessi che assegni l'azione **Nega** al diritto di **autorizzazione Registrazione**.
  
    ![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
    Tutti i certificati EFS devono essere stati emessi dal certificato appena configurato altrimenti le chiavi non verranno archiviate automaticamente.
  
11. Scegliere **OK** e chiudere la console di Autorità di certificazione.
  
##### Creazione e utilizzo dell'agente di recupero dati offline
  
Microsoft suggerisce che i KRA e i DRA siano configurati per l'utilizzo offline e abilitati esclusivamente quando necessari per gli scenari di ripristino. Le operazioni necessarie per creare un agente di recupero dati offline sono quattro:
  
1.  Creare un nuovo account utente da utilizzare esclusivamente per gli eventi di recupero dati.
  
2.  Richiedere, generare e assegnare un certificato digitale DRA o KRA al nuovo account.
  
3.  Esportare il certificato e la chiave privata, rimuoverli dalla rete e archiviarli in modo sicuro.
  
4.  Disattivare l'account utente di recupero dati affinché non possa essere utilizzato fino a quando non sarà necessario.
  
I passaggi 1 e 2 vengono trattati in questa guida mentre il passaggio 4 consiste in un'attività di manutenzione standard dell'account Windows. Il passaggio 3, invece, richiede un'ulteriore spiegazione.
  
###### Esportazione e rimozione dei certificati di recupero dati
  
Per esportare e rimuovere un certificato di recupero dati per l'utilizzo offline, completare le seguenti operazioni.
  
**Per esportare e rimuovere un certificato di recupero dati**
  
1.  Accedere a Windows utilizzando l'account utente di recupero dati per cui si desidera esportare le chiavi.
  
2.  Fare clic su **Start**, **Esegui**, digitare **MMC.EXE** e premere INVIO. Se richiesto da Controllo dell'account utente, scegliere **Continua**.
  
3.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**.
  
4.  Selezionare lo snap-in **Certificati** e scegliere **Aggiungi**.
  
5.  Quando richiesto, selezionare il pulsante di opzione **Account dell'utente**, scegliere **Fine**, quindi **OK**.
  
6.  Espandere l'oggetto **Certificati - Utente corrente**, **Personale**, quindi scegliere **Certificati**.
  
7.  Individuare il certificato digitale di recupero dati corrente. In caso di dubbio sul certificato da utilizzare, cercare i certificati digitali con **Ripristino file** o **Recupero chiave** nel campo **Scopo designato**.
  
8.  Fare clic con il pulsante destro del mouse sul certificato digitale di recupero dati, scegliere **Tutte le attività**, quindi **Esporta** per avviare l'esportazione guidata certificati.
  
9.  Scegliere **Avanti**.
  
10. Selezionare la casella di controllo **Esporta la chiave privata**, quindi scegliere **Avanti**.
  
11. Selezionare la casella di controllo **Elimina la chiave privata se l'esportazione ha esito positivo**, quindi scegliere **Avanti**.
  
    ![](images/Cc162812.98313b0b-0b11-4d33-aaf6-0a5ac35dce84(it-it,TechNet.10).gif)
  
    **Figura 2.5. Richiesta del formato del file di esportazione nell'esportazione guidata certificati**
  
12. Digitare due volte una password protettiva e scegliere **Avanti**.
  
13. Scegliere **Sfoglia**, quindi l'ubicazione in cui si desidera archiviare il certificato di recupero dati esportato.
  
14. Immettere un nome file per il certificato e le chiavi di recupero dati per cui è stato eseguito il backup. Lasciare l'estensione del file .PFX per facilitare la reimportazione della chiave.
  
15. Scegliere **Salva**, **Avanti**, **Fine**, quindi **OK**.
  
16. Copiare il file di backup risultante in un'altra ubicazione ed eliminarlo dall'ubicazione corrente, se non è più necessario. Accertarsi di svuotare il cestino dopo aver eliminato i certificati digitali EFS o i file.
  
17. Archiviare le chiavi e il certificato digitale di backup in due o più ubicazioni separate e protette.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
Quando viene esportata la chiave privata del certificato di recupero dati, la chiave pubblica di recupero dati (utilizzata per crittografare la FEK) dovrebbe essere lasciata sul computer. Se viene eliminata, l'agente di recupero dati potrebbe non essere abilitato alla crittografia o al ripristino delle chiavi o dei file protetti da EFS.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività di configurazione per computer
  
Oltre alle attività di configurazione dell'infrastruttura precedentemente descritte, sarà necessario eseguire attività di configurazione sui singoli computer.
  
#### Attività di configurazione per computer per BitLocker
  
Per configurare BitLocker su un computer, è necessario:
  
-   Accertarsi che sul computer sia possibile eseguire BitLocker
  
-   Abilitare e inizializzare il TPM, se presente
  
-   Abilitare BitLocker
  
##### Aggiornare il BIOS per il supporto TPM
  
Durante la fase di pianificazione, è stato determinato quali computer sarebbero stati utilizzati con BitLocker e quali di questi computer contengono hardware TPM v1.2 (o successiva) e un BIOS compatibile. Il primo passaggio delle attività di configurazione per computer per BitLocker consiste nell'aggiornare il BIOS sui computer che lo necessitano.
  
Le operazioni specifiche, necessarie per aggiornare il BIOS di un singolo computer, variano in base al produttore. Gli aggiornamenti firmware BIOS vengono spesso forniti su supporti insieme ai nuovi computer e, in genere, sono disponibili sull'OEM o sul sito Web dei fornitori della scheda madre. Solitamente, per i computer portatili, è necessario creare un disco USB o CD di avvio con l'immagine del BIOS fornito dal produttore e quindi utilizzarlo per avviare il computer quando è collegato a una presa elettrica. Per effettuare questo processo è necessario accedere fisicamente a ogni computer da aggiornare. Seguire le istruzioni del fornitore per l'aggiornamento del firmware BIOS e successivamente riavviare il computer.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
È importante che tutti i computer partecipanti dispongano degli ultimi aggiornamenti firmware BIOS per molte altre ragioni, tra cui aggiornamenti software e miglioramento delle prestazioni. Prima di abilitare il TPM o BitLocker in Windows Vista, accertarsi che sia installata l'ultima versione firmware.
  
##### Confermare un percorso di avvio stabile
  
BitLocker e TPM assicurano l'integrità del percorso di avvio del computer tramite la procedura di avvio di Windows Vista, eseguendo una serie di controlli noti come *Profilo di convalida della piattaforma* (PVP) TPM. Se la procedura di avvio cambia significativamente dopo l'installazione di BitLocker, i risultati della PVP saranno diversi e potrebbe verificarsi una modifica dell'integrità. In questo caso, BitLocker potrebbe rifiutarsi di sbloccare il volume del sistema operativo a meno che non venga utilizzato un metodo di ripristino aggiuntivo.
  
Per questo motivo, prima di attivare BitLocker, accertarsi che il percorso di avvio software e hardware sia completamente configurato e stabile. In particolare, ogni computer su cui si desidera abilitare BitLocker dovrebbe disporre di quanto segue:
  
-   Una configurazione BIOS che rispecchi il dispositivo di avvio corretto
  
-   Tutti i dispositivi facoltativi che si avvalgono di firmware ROM installato
  
-   Eventi di attivazione LAN
  
-   Dati configurazione di avvio (BCD) Windows configurati
  
È possibile utilizzare i criteri del computer locale e i Criteri di gruppo di Active Directory per configurare quali componenti di avvio (denominati *registri di configurazione di piattaforma* o PCR) vengono presi in considerazione dal TPM durante il processo di avvio. Per la maggior parte delle applicazioni, l'impostazione predefinita dei PCR fornisce una protezione adeguata e Microsoft suggerisce di non modificarla.
  
Dopo aver installato BitLocker, la modifica di qualsiasi componente che disponga di un PCR corrispondente provocherà la richiesta da parte di BitLocker di una password di ripristino. Esempi di modifiche al PCR comprendono l'aggiornamento del BIOS, l'aggiunta di un dispositivo di avvio abilitato a ROM, la modifica del record di avvio principale (MBR), la tabella delle partizioni, i dati del settore di avvio di basso livello, i dati di configurazione di avvio o boot manager o l'installazione di un altro sistema operativo in un nuovo scenario ad avvio doppio.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
Il record di avvio principale (MBR), il codice di settore di avvio e il boot manager di Windows Vista forniscono una valida protezione dell'integrità per BitLocker. Microsoft raccomanda di non utilizzare programmi di caricamento di avvio di terze parti. L'aggiunta di un nuovo programma di caricamento di avvio dopo l'attivazione di BitLocker avvierà il ripristino; il cambio dei programmi di caricamento di avvio prima dell'attivazione di BitLocker impedirà a BitLocker di mantenere un ambiente di avvio protetto.
  
##### Abilitare il TPM
  
Se si intende distribuire BitLocker con il TPM, è necessario abilitare il TPM su ogni computer client. I computer certificati come compatibili con Windows Vista dovrebbero contenere una versione BIOS che consenta a BitLocker di abilitare il TPM durante il processo di impostazione di BitLocker. Altrimenti, l'abilitazione del TPM richiede, in genere, l'utilizzo del programma di configurazione e impostazione del BIOS del computer, richiamato premendo una specifica combinazione di tasti durante il processo di avvio hardware del computer. Sebbene non esista un'ubicazione standard per l'opzione TPM, solitamente questa si trova in **Opzioni avanzate** o in **Configurazione periferica**, nelle schermate di configurazione. Se l'opzione è disabilitata, selezionare **Abilita**, salvare le nuove impostazioni del BIOS, uscire e riavviare il computer, se necessario. Dopo il riavvio, la maggior parte dei computer con TPM visualizzerà una schermata come quella mostrata nella seguente immagine, che richiede di confermare l'abilitazione del TPM.
  
![](images/Cc162812.e6903e71-09fe-424c-87de-d344db8d8e05(it-it,TechNet.10).gif)
  
**Figura 2.6. Esempio di finestra di dialogo di conferma TPM**
  
##### Inizializzare il TPM con Windows Vista
  
Se un TPM verrà utilizzato con BitLocker, il chip TPM deve essere inizializzato consentendo a Windows Vista di acquisire la proprietà del TPM. Le informazioni sulla proprietà del TPM possono essere esaminate attraverso lo snap-in MMC del TPM (tpm.msc).
  
Il TPM deve essere inizializzato una sola volta per ogni computer. BitLocker deve essere abilitato una sola volta per ogni sistema operativo (se il computer è configurato per l'avvio a più sistemi operativi). In altre parole, se si dispone di un singolo computer che ha diverse installazioni di avvio di Windows Vista, sarà necessario abilitare BitLocker per ciascuna installazione.
  
In genere, l'impostazione guidata di BitLocker automatizza il processo di inizializzazione del TPM. Tuttavia, è possibile inizializzare anche manualmente il TPM, se necessario.
  
**Per inizializzare il TPM da Windows Vista**
  
1.  Verificare che il chip TPM sia stato abilitato nel BIOS.
  
2.  Verificare che sia disponibile il dispositivo della stampante o di archiviazione appropriato per la password di gestione del TPM.
  
3.  Accedere a Windows Vista utilizzando un account che disponga di privilegi di amministratore sul computer.
  
4.  Avviare lo snap-in di MMC del TPM. A tal fine, digitare **TPM.MSC** nella casella **Cerca** e premere INVIO.
  
5.  Se richiesto dal Controllo dell'account utente, scegliere **Continua** e verrà visualizzata una console del TPM.
  
6.  Se Windows Vista non riconosce il chip TPM, sarà necessario risolvere il problema, abilitarlo correttamente, quindi iniziare di nuovo questa procedura.
  
7.  Nel riquadro **Azioni**, scegliere l'opzione **Inizializza TPM**.
  
8.  Nella finestra di dialogo **Crea la password del proprietario del TPM**, verrà richiesto di creare una password del proprietario del TPM. Questa password è necessaria solo per le attività di gestione del TPM fuori dall'ambito di azione di BitLocker.
  
    È possibile lasciare che la procedura crei automaticamente la password (azione consigliata) o crearla manualmente. Nel secondo caso, sarà necessario creare una password composta da almeno 8 caratteri. È possibile modificare la password del proprietario del TPM in qualsiasi momento dopo averla impostata (sebbene sia necessario conoscere la password corrente per modificarla).
  
9.  È possibile salvare la password su supporti rimovibili o in qualsiasi altro percorso di archiviazione valido, incluso un dispositivo di memoria flash USB, un percorso file, il desktop o un percorso di rete. Se si preferisce, è possibile stampare la password con una stampante di rete o locale collegata. Se si archivia la password del TPM, Windows Vista la salva come file in formato XML con estensione file .TPM. Per impostazione predefinita, il file viene denominato con lo stesso nome del computer. Sarebbe opportuno salvare o stampare la password del proprietario del TPM in due o più ubicazioni separate e protette.
  
10. Una volta immessa e salvata o stampata la password, viene avviata l'inizializzazione del TPM. Windows Vista visualizza una finestra di dialogo di stato che indica lo stato dell'inizializzazione del TPM.
  
11. Terminata l'inizializzazione, Windows Vista visualizza una finestra di dialogo di completamento. Scegliere **Chiudi** per terminare il processo di inizializzazione.
  
È possibile anche inizializzare e acquisire la proprietà del TPM da Windows Vista utilizzando lo script **manage-bde.wsf** nel prompt dei comandi, come riportato di seguito:
  
**cscript manage-bde.wsf -tpm -takeownership -***&lt;password&gt;*
  
Eseguendo questo comando si acquisisce la proprietà del TPM e si può impostare la password del proprietario del TPM sul valore specificato.
  
Facoltativamente, è possibile scrivere uno script che utilizzi le interfacce WMI fornite per controllare il TPM.
  
##### Abilitare BitLocker
  
BitLocker può essere abilitato in due modi: manualmente, tramite le operazioni descritte nella procedura seguente, oppure utilizzando la Distribuzione guidata Windows. Per ulteriori informazioni sull'utilizzo della Distribuzione guidata Windows per abilitare BitLocker, consultare [Running the Windows Deployment Wizard](http://go.microsoft.com/fwlink/?linkid=78820) (in inglese) nella sezione "Lite Touch Installation Guide" del toolkit Business Desktop Deployment.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
È possibile utilizzare le impostazioni di Criteri di gruppo per controllare quali funzionalità di BitLocker possano essere configurate dagli utenti; in base a questo l'interfaccia delle seguenti schermate può variare.
  
**Per abilitare BitLocker manualmente**
  
1.  Aprire Pannello di controllo e fare doppio clic su **Protezione**.
  
2.  Fare doppio clic su **Crittografia unità BitLocker**. Se richiesto da Controllo di accesso utente, scegliere **Continua**.
  
    ![](images/Cc162812.d98ec788-93f5-4dc5-813d-55a9f67c70ba(it-it,TechNet.10).gif)
  
    **Figura 2.7. Schermata Crittografia unità BitLocker in Pannello di controllo**
  
3.  Scegliere **Attiva BitLocker**.
  
4.  Come mostrato nella figura che segue, potrebbe essere richiesto di scegliere un'ubicazione per salvare o stampare la password di ripristino di BitLocker. Se si sceglie di salvare la password di ripristino di BitLocker di 48 caratteri, questa verrà salvata in un file di testo denominato come l'ID password di BitLocker. Se si salva la password di ripristino su un'unità di memoria flash USB, una chiave di ripristino a 256 bit verrà archiviata come file nascosto (con un'estensione .BEK). È possibile scegliere qualsiasi percorso per l'archiviazione del file o qualsiasi unità di memoria flash USB oppure è possibile stampare la password di ripristino. Nella seguente schermata viene illustrata l'archiviazione della password di ripristino in una cartella su un'unità di memoria flash USB.
  
    ![](images/Cc162812.f0c09b3f-eeee-479e-8aa3-12214ccb7249(it-it,TechNet.10).gif)
  
    **Figura 2.8. Opzioni relative alla password di ripristino di BitLocker**
  
5.  Sarebbe opportuno salvare la password di ripristino in una o più ubicazioni separate e protette. Se si perde la chiave di ripristino di BitLocker, è possibile che non si abbia l'accesso ai dati. Non è possibile continuare l'abilitazione di BitLocker fino a quando la password di ripristino di BitLocker non viene salvata correttamente.
  
    **Nota**
  
    La password di ripristino viene scritta in testo non crittografato nel file di testo, quindi deve essere protetta da accessi non autorizzati.
  
    Dopo aver salvato la password di ripristino di BitLocker una o più volte, scegliere **Avanti**.
  
6.  Nella finestra di dialogo **Crittografare il volume**, selezionare l'opzione **Esegui controllo sistema BitLocker** per verificare che il percorso di avvio sia attendibile e che la protezione di BitLocker possa essere applicata prima di iniziare la crittografia. Questa operazione è facoltativa, ma vivamente consigliata. Nel caso si verifichi un errore, Windows Vista visualizza un avviso e la crittografia di BitLocker non viene applicata automaticamente.
  
7.  Scegliere **Continua**. Se si decide di non eseguire un controllo del sistema, è possibile selezionare **Crittografa** per iniziare la crittografia del volume.
  
8.  In caso contrario, verrà richiesto di verificare che il supporto di memoria flash USB sia inserito (nel caso sia stato scelto per l'archiviazione della password di ripristino di BitLocker) e quindi di riavviare il computer.
  
9.  Durante il riavvio, Windows Vista ricerca e verifica la password di ripristino di BitLocker archiviata sulla chiave USB e visualizza un messaggio in una finestra di testo precedente all'avvio che indica la riuscita dell'operazione.
  
10. Quando Windows Vista viene riavviato, BitLocker inizia la crittografia del volume di avvio e visualizza un messaggio di stato che indica la percentuale di completamento dell'operazione, come mostrato nella schermata riportata di seguito.
  
    ![](images/Cc162812.bdf7dbb8-4613-45fb-af4a-6c0180e4702b(it-it,TechNet.10).gif)
  
    **Figura 2.9. Messaggio di stato della crittografia BitLocker**
  
La prima crittografia attiva del volume del sistema operativo provocherà un lieve ritardo nelle prestazioni. Durante l'operazione di crittografia, gli utenti possono continuare a lavorare sul computer.
  
##### Convalida dell'installazione e della configurazione di BitLocker
  
Una volta completata la crittografia del volume del sistema operativo da parte di BitLocker, è possibile confermarne lo stato utilizzando la console Gestione disco, mostrata nella schermata che segue. Il volume crittografato contiene le parole BitLocker Encrypted.
  
![](images/Cc162812.7985cd63-82be-41ae-bf22-ef5b57f7f667(it-it,TechNet.10).gif)
  
**Figura 2.10. Console Gestione disco**
  
Se si utilizza Active Directory per l'archiviazione della chiave di ripristino, è opportuno verificare che le informazioni di ripristino siano archiviate correttamente in Active Directory. A tal fine, è possibile scaricare BitLocker Recovery Password Viewer (disponibile nell'articolo 928202 della Knowledge Base Microsoft, "[Come utilizzare lo strumento BitLocker Recovery Password Viewer per Utenti e computer di Active Directory per visualizzare le password di ripristino per Windows Vista](http://support.microsoft.com/kb/928202)"), installarlo e utilizzarlo per verificare che le informazioni di ripristino siano disponibili per uno o più computer di test. BitLocker Recovery Password Viewer semplifica anche il processo grazie al quale si consente al supporto tecnico autorizzato o al personale di supporto di recuperare le informazioni di ripristino, quando necessario. Per ulteriori informazioni sui problemi relativi ai criteri sul ripristino della password, consultare la guida [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information](http://go.microsoft.com/fwlink/?linkid=67438) (in inglese).
  
#### Attività di configurazione per computer per EFS
  
EFS richiede un numero relativamente ridotto di attività di configurazione per computer. Alla prima distribuzione di EFS, l'unica attività da eseguire è la crittografia dei file o delle cartelle che desideri proteggere sul computer prescelto.
  
##### Crittografia dei file e delle cartelle
  
Dopo l'abilitazione di EFS sui computer selezionati, gli utenti dell'organizzazione possono iniziare a crittografare i file e le cartelle sui computer. Lo strumento EFS Assistant fornito con questo toolkit può essere utilizzato per creare criteri di crittografia oppure è possibile fornire informazioni agli utenti sull'utilizzo di una delle due interfacce fornite con Windows per abilitare la crittografia EFS.
  
###### Con Esplora risorse
  
**Per modificare lo stato della crittografia di un file o una cartella con Esplora risorse**
  
1.  Fare clic con il pulsante destro del mouse sul file o la cartella e scegliere **Proprietà**.
  
2.  Nella scheda **Generale**, scegliere **Avanzate**, quindi selezionare la casella di controllo **Crittografa contenuto per la protezione dei dati**
  
3.  Fare clic due volte su **OK** per confermare la crittografia del file.
  
![](images/Cc162812.5c7c1e31-6246-4f2a-bdd2-dd1691effa61(it-it,TechNet.10).gif)
  
**Figura 2.11. Finestra di dialogo Attributi avanzati in Esplora risorse**
  
Quando si esegue per la prima volta la crittografia di un singolo file in una cartella, Windows richiede di specificare se si desidera crittografare solo il file o l'intera cartella che lo contiene, quindi abilitare EFS per l'intera cartella e tutti i file e cartelle in essa contenuti.
  
![](images/Cc162812.1adbaf44-740f-4eef-82d9-b9bbd0750f41(it-it,TechNet.10).gif)
  
**Figura 2.12. Finestra di dialogo Avvisi sulla crittografia in Esplora risorse**
  
###### Con Cipher.exe
  
Per crittografare file e cartelle, è anche possibile utilizzare lo strumento da riga di comando **Cipher.exe**. A tal fine, al prompt dei comandi, selezionare la directory che contiene i file o le cartelle da crittografare. Per crittografare l'intera directory e tutti i file e le cartelle in essa contenuti, digitare **Cipher.exe /e** e premere INVIO. In alternativa, è possibile specificare un elenco dei file o delle cartelle che si desidera crittografare includendo i nomi dopo lo switch **/e**.
  
###### Crittografia dei file condivisi
  
**Per aggiungere utenti a un file condiviso**
  
1.  Fare clic con il pulsante destro del mouse sul file o la cartella e scegliere **Proprietà**.
  
2.  Nella scheda **Generale**, scegliere **Avanzate**, quindi **Dettagli**.
  
    Windows visualizzerà gli altri utenti disponibili con certificati digitali EFS.
  
3.  Scegliere uno o più utenti aggiuntivi, quindi **OK**.
  
4.  Una volta terminata l'operazione, scegliere due volte **OK** per tornare a Esplora risorse.
  
![](images/Cc162812.note(it-it,TechNet.10).gif)**Nota:**
  
In Windows Vista, è possibile utilizzare anche il comando **Cipher.exe** con il parametro **/adduser** per aggiungere ulteriori utenti ai file protetti con EFS.
  
###### Verifica dello stato di crittografia di un file o una cartella
  
In caso di dubbio sulla crittografia di un particolare file o una cartella, è possibile utilizzare diversi metodi per determinarne lo stato. Due di questi metodi consistono nell'osservare i suggerimenti visivi in Esplora risorse e nell'utilizzare **Cipher.exe**.
  
**Esplora risorse**
  
In Esplora risorse, i file e le cartelle crittografati con EFS sono evidenziati con caratteri verdi (come mostrato nella schermata che segue) o mostrano una E negli attributi del file.
  
![](images/Cc162812.87097207-c6cf-446a-be68-c00201db89ee(it-it,TechNet.10).gif)
  
**Figura 2.13. File crittografati con EFS in Esplora risorse**
  
L'evidenziazione verde è una caratteristica attivata per impostazione predefinita in Windows XP Professional e nelle versioni successive di Windows. Per attivare o disattivare questa funzionalità in Windows XP, scegliere **Opzioni cartella** e selezionare o deselezionare la casella di controllo dell'attributo **Visualizza i file NTFS compressi o crittografati con un colore diverso**.
  
Per accedere a questa impostazione in Windows Vista, aprire Esplora risorse e, nel menu **Organizza**, scegliere **Opzioni cartella e ricerca**, scegliere la scheda **Visualizzazione** e selezionare o deselezionare la casella di controllo **Visualizza i file NTFS compressi o crittografati con un colore diverso**.
  
Per accedere a questa opzione in Windows XP Professional, aprire Esplora risorse e, nel menu **Strumenti**, scegliere **Opzioni cartella**. Quindi, scegliere la scheda **Visualizzazione**.
  
In alcune versioni di Windows, gli attributi del file o della cartella potrebbero non essere immediatamente visibili in Esplora risorse. Assicurarsi di utilizzare la vista **Dettagli** per visualizzare i file. Se gli attributi del file o della cartella continuano a non essere visibili, è necessario aggiungerli alla vista **Dettagli**. A tal fine, fare clic con il pulsante destro del mouse su una qualsiasi intestazione di colonna nella vista **Dettagli**, scegliere **Altro**, quindi selezionare **Attributi**.
  
**Cipher.exe**
  
È anche possibile utilizzare l'utilità della riga di comando **Cipher.exe** per visualizzare, crittografare e decrittografare i file protetti con EFS (tra le altre opzioni). Per verificare lo stato di EFS sui file, aprire un prompt dei comandi in Windows, andare al percorso del file o della cartella, digitare **Cipher.exe** senza alcun parametro della riga di comando e premere INVIO. L'utilità Cipher mostrerà una **U** vicino ai file o alle cartelle non crittografati e una **E** accanto ai file o alle cartelle crittografati.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
-   [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information (in inglese)](http://go.microsoft.com/fwlink/?linkid=67438)
  
-   [Certificate Autoenrollment in Windows XP (in inglese)](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/certenrl.mspx)
  
-   [Running the Windows Deployment Wizard (in inglese)](http://go.microsoft.com/fwlink/?linkid=78820)
  
-   [Come utilizzare lo strumento BitLocker Recovery Password Viewer per Utenti e computer di Active Directory per visualizzare le password di ripristino per Windows Vista](http://support.microsoft.com/kb/928202)
  
**Download**
  
[Download di Data Encryption Toolkit for Mobile PC (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)
  
**Notifiche di aggiornamento**
  
[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti**
  
[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=data%20encryption%20toolkit%20for%20mobile%20pc,%20guida%20alla%20pianificazione%20e%20all'implementazione%20di%20data%20encryption%20toolkit)
  
[](#mainsection)[Inizio pagina](#mainsection)
