---
TOCTitle: 'Creazione dell''autorità di certificazione della rete'
Title: 'Creazione dell''autorità di certificazione della rete'
ms:assetid: '2eb2b7cd-b18b-47fd-9cc7-6c83ec52524b'
ms:contentKeyID: 20200832
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536233(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 4: Creazione dell'autorità di certificazione della rete

Aggiornato: 3 aprile 2004

##### In questa pagina

[](#ehaa)[Cenni preliminari](#ehaa)
[](#egaa)[Prima di iniziare](#egaa)
[](#efaa)[Operazioni preliminari per l'implementazione](#efaa)
[](#eeaa)[Controllo dell'ambiente prima dell'installazione](#eeaa)
[](#edaa)[Installazione di Servizi certificati](#edaa)
[](#ecaa)[Configurazione della CA](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Cenni preliminari

In questo capitolo viene descritta la procedura di installazione e configurazione di Servizi certificati di Microsoft® Windows Server™ 2003. Tali servizi rappresentano un componente facoltativo di Windows Server 2003 e non vengono installati per impostazione predefinita.

Un'installazione di Servizi certificati viene denominata "autorità di certificazione" (CA). Per la soluzione *Protezione delle reti LAN senza fili con PEAP e password* è necessaria una singola CA. Questa CA verrà utilizzata per il rilascio dei certificati relativi ai server del Servizio di autenticazione Internet (IAS), illustrati nei capitoli successivi.

L'obiettivo di questo capitolo è offrire una CA estremamente semplice per scopi speciali. A differenza della maggior parte delle CA, verrà utilizzata per il rilascio di un solo tipo di certificati, ovvero i certificati server per i server IAS impiegati nella soluzione. Per questo motivo, è stata progettata in modo che l'installazione, la configurazione e la gestione risultino estremamente semplici. È importante tenere presente che, se l'organizzazione intende utilizzare i certificati per altri scopi, ad esempio per la futura implementazione di IPSec o di una rete VPN, Microsoft consiglia un'infrastruttura a chiave pubblica (PKI) più affidabile per l'ambiente specifico. Per ulteriori informazioni, vedere il materiale di riferimento indicato nel capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili".

Le informazioni riportate in questo capitolo si riferiscono solo alle istruzioni di implementazione della CA. Nel capitolo non vengono illustrati né i concetti generali dell'infrastruttura PKI né i dettagli relativi all'implementazione di Servizi certificati Microsoft, ad eccezione di quelli necessari per completare l'installazione. Non viene trattato neanche l'utilizzo di questa CA per il rilascio di tipi di certificati diversi dai certificati di autenticazione server per IAS.

Questo capitolo si basa sul presupposto che nell'organizzazione non esista attualmente un'infrastruttura PKI. Se ne esiste una,è possibile rilasciare i certificati per i server IAS da tale infrastruttura anziché installare la CA descritta in questo capitolo. La istruzioni relative all'esecuzione di tale operazione o all'installazione della CA nell'infrastruttura PKI esistente esulano tuttavia dagli argomenti trattati in questa guida.

Anziché installare una CA interna, è possibile ottenere i certificati da una CA commerciale quale VeriSign o Thawte. Per la descrizione dei relativi vantaggi dell'installazione di una CA interna rispetto all'acquisto di certificati da un'autorità di certificazione esterna, vedere la sezione "Come ottenere i certificati per i server IAS" nel capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili". Questo capitolo non include nessuna indicazione su come ottenere e utilizzare i certificati di una CA commerciale. Alla fine del capitolo, tuttavia, sono disponibili i riferimenti a un documento Microsoft che descrive tale processo.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

Oltre ai prerequisiti elencati nel capitolo 3 "Predisposizione dell'ambiente", è consigliabile acquisire familiarità con i concetti relativi a Servizi certificati e all'infrastruttura PKI, anche se non è richiesta una conoscenza approfondita.

Prima di implementare le istruzioni riportate in questo capitolo, è necessario leggere e implementare le linee guida contenute nel capitolo 3 "Predisposizione dell'ambiente". È consigliabile leggere anche le informazioni relative alla progettazione e alla pianificazione contenute nel capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili", nonché acquisire una conoscenza approfondita dell'architettura e della progettazione della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Operazioni preliminari per l'implementazione

#### Autorizzazioni necessarie

Per eseguire le procedure di questo capitolo, è necessario accedere con un account membro dei seguenti gruppi:

-   Il gruppo **Domain Admins** per il dominio in cui viene installata la CA

-   Il gruppo **Enterprise Admins** dell'insieme di strutture del servizio Microsoft Active Directory®.

Per impostazione predefinita, l'account Administrator predefinito del dominio principale dell'insieme di strutture (il primo dominio creato nell'insieme di strutture) è membro di entrambi i gruppi, ma è possibile utilizzare qualsiasi altro account con le stesse appartenenze ai gruppi.

**Nota:** se non si installa la CA nel dominio principale di un insieme di strutture del servizio Active Directory di Windows 2000 o di un insieme di strutture aggiornato da tale servizio, l'account utilizzato per l'installazione dovrà essere membro anche del dominio principale dell'insieme di strutture.

#### Strumenti necessari

Per eseguire le procedure di questo capitolo sono necessari gli strumenti indicati di seguito.

**Tabella 4.1: Strumenti necessari per creare e installare una CA**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Strumento</th>
<th style="border:1px solid black;" >Descrizione</th>
<th style="border:1px solid black;" >Origine</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">MSS WLAN Tools</td>
<td style="border:1px solid black;">Set di script e strumenti fornito con questa soluzione.</td>
<td style="border:1px solid black;">La procedura di installazione è descritta nel capitolo 3.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Console Gestione Criteri di gruppo (GPMC, Group Policy Management Console)</td>
<td style="border:1px solid black;">Strumento di gestione avanzata per l'importazione e l'esportazione degli oggetti Criteri di gruppo (GPO).</td>
<td style="border:1px solid black;">La procedura di installazione è descritta nel capitolo 3.<br />
Può essere scaricata dal sito Microsoft.com.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CAPICOM</td>
<td style="border:1px solid black;">Libreria di sistema che consente lo scripting di operazioni relative ai certificati e alla protezione.</td>
<td style="border:1px solid black;">La procedura di installazione è descritta nel capitolo 3.<br />
Può essere scaricata dal sito Microsoft.com.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DSACLs.exe</td>
<td style="border:1px solid black;">Strumento della riga di comando che consente l'impostazione delle autorizzazioni per gli oggetti di Active Directory.</td>
<td style="border:1px solid black;">La procedura di installazione è descritta nel capitolo 3.<br />
Disponibile nel CD di installazione di Windows Server 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Utenti e computer di Active Directory</td>
<td style="border:1px solid black;">Strumento MMC (Microsoft Management Console) utilizzato per la gestione di utenti, gruppi, computer e altri oggetti di Active Directory.</td>
<td style="border:1px solid black;">Installato con Windows Server 2003.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Strumento di amministrazione Autorità di certificazione</td>
<td style="border:1px solid black;">Strumento MMC utilizzato per la gestione della CA.</td>
<td style="border:1px solid black;">Installato con Servizi certificati in Windows Server 2003.</td>
</tr>
</tbody>
</table>
  
#### Parametri relativi all'autorità di certificazione
  
Nella tabella seguente sono elencati i parametri utilizzati per l'installazione e la configurazione della CA in questa soluzione. Tutti questi parametri vengono impostati nel file di script PKIparams.vbs e, se necessario, è possibile modificarli.
  
**Tabella 4.2: Impostazioni della CA utilizzate nella soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Parametro di configurazione della CA</th>
<th style="border:1px solid black;" >Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Unità e percorso dei file di richieste di Servizi certificati</td>
<td style="border:1px solid black;">C:\CAConfig</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Lunghezza della chiave della CA</td>
<td style="border:1px solid black;">2048 bit</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di validità del certificato della CA</td>
<td style="border:1px solid black;">25 anni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo massimo di validità dei certificati rilasciati dalla CA</td>
<td style="border:1px solid black;">2 anni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Intervallo di pubblicazione dei CRL per la CA</td>
<td style="border:1px solid black;">7 giorni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo di sovrapposizione dei CRL (tempo che intercorre tra la pubblicazione di un nuovo CRL e la scadenza del vecchio CRL)</td>
<td style="border:1px solid black;">4 giorni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pubblicazione di Delta-CRL disattivata</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modelli di certificato disponibili nella CA</td>
<td style="border:1px solid black;">Computer</td>
</tr>
</tbody>
</table>
  
**Nota:** il periodo di validità della CA è impostato su un valore elevato per evitare il sovraccarico amministrativo dovuto al rinnovo periodico del certificato della CA. A differenza dei certificati rilasciati per computer e utenti, i certificati della CA non possono essere rinnovati automaticamente e, se non vengono rinnovati prima della scadenza, tutti i certificati rilasciati dalla CA genereranno errori.
  
**Importante:** le impostazioni elencate nella tabella precedente sono state utilizzate per il testing interno di questa soluzione e funzionano esattamente come documentato. Molti di questi valori possono essere modificati ma è consigliabile eseguire tale operazione solo se si conoscono esattamente lo scopo di una determinata impostazione e le implicazioni della relativa modifica.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Controllo dell'ambiente prima dell'installazione
  
Prima di installare Servizi certificati nel server, è necessario verificare che il dominio sia contattabile e che gli strumenti necessari siano stati installati.
  
**Per controllare il server prima dell'installazione della CA**
  
1.  Accedere al server in cui si intende installare la CA e la prima istanza del server IAS utilizzando un account con le autorizzazioni amministrative appropriate.
  
2.  Fare clic sul collegamento **MSS WLAN Tools** per aprire una shell dei comandi, quindi digitare al prompt dei comandi:
  
    *MSSsetup CheckCAenvironment*
  
    Il nome del dominio in cui viene installata la CA viene visualizzato come nome distinto (DN) (ad esempio dc=Treyresearch, dc=net) equivalente al formato DNS (Treyresearch.net).
  
3.  Se il nome del dominio è corretto, fare clic su **OK**. In caso contrario, fare clic su **Cancel**, accedere al dominio corretto, quindi ripetere i passaggi 1 e 2.
  
Lo script verifica quanto segue:
  
-   Se è possibile contattare il controller di dominio di Active Directory.
  
-   Se CAPICOM è installato.
  
-   Se la console Gestione Criteri di gruppo è installata.
  
-   Se DSACLs.exe è installato e accessibile.
  
Nel caso in cui vengano rilevati eventuali problemi, viene visualizzata una notifica di errore nella finestra della console dello script. Prima di continuare, è necessario individuare e correggere l'errore.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione di Servizi certificati
  
In questa sezione viene descritta la procedura di installazione di Servizi certificati per la creazione di una CA. La CA viene installata come CA principale dell'organizzazione.
  
#### Installazione dei componenti software di Servizi certificati
  
È necessario installare i componenti software della CA mediante lo script fornito. Questo script utilizza Gestione componenti facoltativi di Windows per installare la CA, creando tutti i file di configurazione necessari durante l'esecuzione. Per eseguire l'installazione, utilizzare il CD di installazione di Windows Server 2003 o il percorso di rete di un'origine di installazione di Windows.
  
**Avviso:** se in precedenza è stata installata una CA o si sta tentando di reinstallarla, è necessario rimuovere prima l'installazione esistente. Prima di rimuovere la CA, verificare che non venga utilizzata da altre applicazioni.
  
Rimuovere Servizi certificati mediante **Installazione componenti di Windows** dell'applet **Installazione applicazioni** nel **Pannello di controllo**.
  
**Per installare Servizi certificati**
  
1.  Utilizzare il collegamento **MSS WLANTools** per aprire una shell dei comandi.
  
2.  Al prompt dei comandi, digitare quanto segue per installare i componenti software di Servizi certificati:
  
    *MSSsetup InstallCA*. Premere **INVIO**.
  
3.  Quando viene richiesto, digitare il nome della CA.
  
    Utilizzare un nome descrittivo e univoco per l'organizzazione, ad esempio CA di rete Trey Research.
  
4.  Per confermare il nome, fare clic su **OK**.
  
    Per modificare il nome, fare clic su **No**.
  
    Per interrompere l'installazione, fare clic su **Cancel**.
  
    Lo script crea i file dei parametri dell'installazione. Al termine dell'operazione, viene richiesto se si desidera continuare l'installazione.
  
5.  Fare clic su **OK** per continuare o su **Cancel** per interrompere l'installazione.
  
    **Nota:** se si annulla l'installazione in questa fase, il file di configurazione CAPolicy.inf e il file dei parametri dei componenti facoltativi OC\_CertSrv.txt verranno lasciati rispettivamente nella cartella di Windows e nella cartella di lavoro corrente. Se non si desidera accettare le impostazioni predefinite della soluzione, è possibile modificare questi file e utilizzarli in un'installazione personalizzata.
  
6.  Dopo la visualizzazione di un messaggio di conferma in cui si informa l'utente che l'installazione è completata, fare clic su **OK**.
  
#### Verifica dell'installazione della CA
  
Mediante la seguente procedura è possibile verificare se l'installazione di Servizi certificati è stata completata correttamente.
  
**Per verificare la corretta installazione della CA**
  
1.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell dei comandi.
  
2.  Al prompt dei comandi, digitare:
  
    *MSSsetup VerifyCAInstall*. Premere **INVIO**.
  
    Il visualizzatore dei certificati mostra il certificato della CA.
  
3.  Fare clic sulla scheda **Generale** del certificato, quindi verificare che i valori visualizzati corrispondano a quelli riportati nella tabella seguente.
  
    **Tabella 4.3 Proprietà del certificato della CA**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Attributo del certificato</th>
    <th style="border:1px solid black;" >Impostazione necessaria</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Rilasciato a</td>
    <td style="border:1px solid black;">Nome della CA specificato durante l'installazione.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Rilasciato da</td>
    <td style="border:1px solid black;">Nome della CA specificato durante l'installazione.</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Valido da...a...</td>
    <td style="border:1px solid black;">L'intervallo specificato dovrebbe corrispondere a 25 anni.</td>
    </tr>
    </tbody>
    </table>
  
4.  Fare clic sulla scheda **Percorso certificazione** e verificare che nel campo relativo al percorso di certificazione venga visualizzato solo un singolo certificato. Per lo stato del certificato viene visualizzato il messaggio **The Certificate is OK**.
  
5.  Fare clic su **OK** per chiudere il visualizzatore dei certificati.
  
Se uno dei valori precedenti non è quello previsto, riavviare l'installazione di Servizi certificati.
  
**Nota:** per eseguire nuovamente l'installazione della CA, è necessario rimuovere prima l'istanza di Servizi certificati installata come descritto in precedenza.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione della CA
  
Dopo l'installazione della CA, è necessario eseguire script aggiuntivi per configurare alcuni dei restanti parametri della CA.
  
#### Configurazione delle proprietà della CA
  
Questa procedura consente di impostare vari parametri della CA, che ne regolano il relativo funzionamento. Alcuni di questi parametri vengono impostati durante l'installazione della CA, mentre altri devono essere impostati dopo l'installazione. I valori dei parametri sono stati specificati in precedenza nella sezione "Parametri relativi all'autorità di certificazione" di questo capitolo. Lo script utilizzato in questa procedura configura le proprietà della CA elencate nella tabella seguente.
  
**Tabella 4.4: Proprietà di configurazione della CA**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Proprietà della CA</th>
<th style="border:1px solid black;" >Descrizione dell'impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">URL dei punti di distribuzione CRL (CDP)</td>
<td style="border:1px solid black;">Specifica le posizioni da cui è possibile ottenere un elenco di revoche di certificati (CRL) corrente. In questa soluzione viene utilizzato solo un URL LDAP (Lightweight Directory Access Protocol), che contiene il percorso LDAP dell'elenco CRL pubblicato in Active Directory.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">URL di accesso alle informazioni dell'autorità (AIA)</td>
<td style="border:1px solid black;">Indica la posizione da cui è possibile ottenere un certificato della CA. Come nel caso del CDP, viene utilizzato solo l'URL LDAP che punta ad Active Directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di validità</td>
<td style="border:1px solid black;">Indica il periodo di validità massimo per i certificati rilasciati, che è diverso dal periodo di validità del certificato stesso della CA, impostato durante l'installazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo CRL</td>
<td style="border:1px solid black;">Indica la frequenza di pubblicazione dell'elenco CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tempo di sovrapposizione CRL</td>
<td style="border:1px solid black;">Indica il tempo di sovrapposizione tra il rilascio di un nuovo CRL e la scadenza del CRL precedente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo Delta - CRL</td>
<td style="border:1px solid black;">Indica la frequenza di pubblicazione dell'elenco Delta-CRL. In questa CA, gli elenchi Delta-CRL sono disattivati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllo CA</td>
<td style="border:1px solid black;">Indica le impostazioni di controllo della CA. Tutti i controlli sono attivati per impostazione predefinita.</td>
</tr>
</tbody>
</table>
  
**Nota:** molti di questi parametri influiscono sulla configurazione del CRL della CA. Un CRL è un elenco di certificati rilasciati dalla CA ma successivamente annullati o revocati dall'amministratore. Anche se è improbabile che vengano revocati certificati durante la gestione di questa soluzione, molte applicazioni devono leggere un CRL per controllare lo stato di revoca di un certificato, persino nel caso in cui il CRL sia vuoto. Se l'applicazione non riesce a trovare un CRL, potrebbe rifiutare il certificato.
  
**Per configurare le proprietà della CA**
  
1.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell dei comandi.
  
2.  Al prompt dei comandi, digitare quanto segue per configurare i componenti della CA:
  
    *MSSsetup ConfigureCA*. Premere **INVIO**.
  
    Durante la configurazione, lo script si interrompe per 20 secondi in attesa del completamento di un'attività sulla CA. Non è necessario rispondere al messaggio popup che informa di tale ritardo.
  
3.  Fare clic su **OK** per eliminare il messaggio.
  
Se nello script viene segnalato un errore, individuarne la causa analizzando il file di registro (%systemroot%\\debug\\MSSWLAN-Setup.log) ed eseguire nuovamente lo script di configurazione dopo aver risolto il problema.
  
**Nota:** è possibile eseguire nuovamente questo script di configurazione per il numero di volte necessario.
  
#### Importazione dell'oggetto Criteri di gruppo Richiesta automatica certificati
  
Questa procedura consente di importare l'oggetto Criteri di gruppo Criterio registrazione automatica certificati IAS, preconfigurato in modo da consentire il rilascio automatico dei certificati per i server IAS del dominio. Viene utilizzata una funzionalità denominata servizio Richiesta automatica certificati (ACRS).
  
ACRS non deve essere confuso con le funzionalità di registrazione automatica di Windows Server 2003, Enterprise Edition, anche se entrambi svolgono funzioni analoghe. Si tratta di un servizio con maggiori limitazioni rispetto alla registrazione automatica, introdotto per la prima volta in Windows 2000. Consente infatti di registrare solo i certificati del *computer* (non dell'utente) e funziona esclusivamente con i modelli di certificato versione 1. Tuttavia, ACRS è adatto per l'attività di certificazione limitata di questa soluzione e il relativo utilizzo consente l'installazione della CA in Windows Server 2003, Standard Edition, che risulta l'edizione dai costi inferiori.
  
**Importante:** se nell'insieme di strutture di Active Directory sono presenti più domini, è necessario ripetere la procedura per ogni dominio in cui è installato un server IAS.
  
Lo script utilizzato nella procedura seguente importa un oggetto Criteri di gruppo preconfigurato con un criterio per la registrazione automatica dei certificati. L'oggetto Criteri di gruppo specifica il tipo di certificato "Computer" predefinito come tipo di certificato da registrare. In seguito, lo script applica autorizzazioni di protezione all'oggetto Criteri di gruppo in modo che l'effetto sia limitato solo ai membri del gruppo Server RAS e IAS (l'impostazione predefinita prevede l'applicazione degli oggetti Criteri di gruppo a tutti gli utenti e i computer autenticati).
  
**Nota:** in alcuni contesti, il modello di certificato Computer potrebbe essere indicato come modello Machine. "Machine" è il nome interno del modello, mentre "Computer" è il nome visualizzato.
  
**Per installare l'oggetto Criteri di gruppo Richiesta automatica certificati nel dominio**
  
1.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell dei comandi.
  
2.  Al prompt dei comandi, digitare quanto segue per importare l'oggetto Criteri di gruppo Criterio registrazione automatica certificati IAS nel dominio:
  
    *MSSsetup ImportAutoenrollGPO*. Premere **INVIO**.
  
Successivamente, è necessario collegare questo oggetto Criteri di gruppo al dominio in modo che le relative impostazioni vengano applicate ai server IAS. Si tratta di una procedura manuale proprio per consentire il controllo diretto del processo di collegamento dell'oggetto Criteri di gruppo L'automatizzazione di questa operazione comporta infatti il rischio di sovrascrittura delle impostazioni di collegamento esistenti dell'oggetto Criteri di gruppo nel dominio.
  
**Per applicare l'oggetto Criteri di gruppo Richiesta automatica certificati**
  
1.  Fare clic su **Start**¸ scegliere **Tutti i programmi**, quindi **Strumenti di amministrazione** e infine **Gestione Criteri di gruppo** per avviare la **console Gestione Criteri di gruppo**.
  
2.  Nel riquadro sinistro della **console Gestione Criteri di gruppo**, selezionare l'oggetto dominio corrispondente al proprio dominio.
  
    L'oggetto dominio si trova nel contenitore **Domains** principale e il relativo nome è uguale al nome DNS del dominio.
  
3.  Fare clic con il pulsante destro del mouse sull'oggetto dominio, quindi selezionare **Collega oggetto Criteri di gruppo esistente...**.
  
4.  Dall'elenco degli oggetti Criteri di gruppo, selezionare **Criterio registrazione automatica certificati IAS**.
  
5.  Fare clic su **OK** per tornare alla finestra principale della **console Gestione Criteri di gruppo**.
  
6.  Nel riquadro destro, fare clic sulla scheda **Oggetti Criteri di gruppo collegati**, quindi selezionare l'oggetto Criteri di gruppo **Criterio registrazione automatica certificati IAS**.
  
7.  Chiudere la **console Gestione Criteri di gruppo**.
  
    Le impostazioni della richiesta automatica di certificati verranno applicate ai server solo dopo l'aggiunta di questi ultimi come membri del gruppo Server RAS e IAS. La relativa procedura è descritta nel capitolo successivo.
  
    **Importante:** se il dominio si trova in modalità mista e si installa IAS nei server membri anziché nei controller di dominio, il gruppo locale Server RAS e IAS non sarà visibile nei server membri. Tale fattore impedirà l'applicazione dell'oggetto Criteri di gruppo ACRS a questi server e quindi anche la registrazione del relativo certificato. Per evitare tale problema, creare un gruppo globale di dominio, aggiungere gli account dei server membri IAS a questo gruppo e aggiungere il gruppo all'elenco di controllo di accesso (ACL) dell'oggetto Criteri di gruppo, concedendo le autorizzazioni di **applicazione** e **lettura**.
  
#### Verifica della configurazione della CA
  
La procedura seguente consente di verificare che la CA sia stata configurata correttamente. Lo script verifica quanto segue:
  
-   Se il periodo di validità per il rilascio di certificati della CA è corretto.
  
-   Se il periodo di pubblicazione del CRL è corretto.
  
-   Se alla CA è stato assegnato il modello di certificati Computer.
  
-   Se l'oggetto Criteri di gruppo Richiesta automatica certificati (Registrazione automatica) è stato importato correttamente nel dominio.
  
Questi valori vengono controllati in base alle impostazioni archiviate nel file PKIParams.vbs. Lo script non controlla i valori assoluti ma verifica solo se impostazioni sono state configurate correttamente nella CA.
  
**Per verificare la configurazione della CA**
  
1.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell dei comandi.
  
2.  Al prompt dei comandi, digitare quanto segue per configurare i componenti della CA:
  
    *MSSsetup VerifyCAConfig*. Premere **INVIO**.
  
Se l'output dello script mostra eventuali errori, è consigliabile ripetere le operazioni illustrate in questo capitolo e risolvere i problemi segnalati.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo sono contenute le linee guida relative al processo di installazione di una CA per scopi speciali, al fine di rilasciare i certificati per i server IAS. La configurazione della CA utilizzata è stata definita in modo da richiedere operazioni di gestione minime anche in futuro. In caso di necessità, tuttavia, le informazioni relative al funzionamento e al supporto tecnico sono incluse nel capitolo 8, "Gestione della soluzione per reti LAN senza fili protette".
  
A questo punto si è pronti per installare i server IAS. La relativa procedura è illustrata nel capitolo 5, "Creazione dell'infrastruttura di protezione per reti LAN senza fili".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riferimenti
  
Questa sezione contiene rimandi a informazioni supplementari importanti e ad altro materiale di riferimento attinente al contenuto di questo capitolo.
  
-   Per un'introduzione all'infrastruttura PKI e alle funzionalità di Servizi certificati di Windows 2000, vedere il documento "An Introduction to the Windows 2000 Public-Key Infrastructure" (in inglese) disponibile al seguente indirizzo:
  
    <http://technet.microsoft.com/en-us/library/cc768063.aspx>
  
-   Per la documentazione di riferimento del prodotto relativa ai concetti fondamentali e alle attività di amministrazione, vedere la sezione "Certificate Services" (in inglese) nella documentazione di Windows Server 2003 disponibile al seguente indirizzo:
  
    <http://technet.microsoft.com/en-us/library/cc783511.aspx>
  
-   Per informazioni su come ottenere e utilizzare i certificati di una CA commerciale, vedere l'articolo "Obtaining and Installing a VeriSign WLAN Server Certificate for PEAP-MS-CHAP v2 Wireless Authentication" (in inglese) disponibile al seguente indirizzo:
  
    [http://www.microsoft.com/downloads/details.aspx?familyid=1971d43c-d2d9-408d-bd97-139afc60996b&displaylang=en](http://download.microsoft.com/download/9/f/d/9fd73f17-2fdf-4409-b2d2-31437c7f29f3/wlancertenroll.doc)
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
