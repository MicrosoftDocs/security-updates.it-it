---
TOCTitle: Guida alla creazione del laboratorio
Title: Guida alla creazione del laboratorio
ms:assetid: '298c6e85-7b2c-4477-b2f4-df26b9411a35'
ms:contentKeyID: 20200802
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536202(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Appendice C: Guida alla creazione del laboratorio

Aggiornato: 16 febbraio 2005

Questa appendice fornisce indicazioni per la creazione dell'infrastruttura necessaria al supporto dei gruppi di isolamento che utilizzano IPsec. Le indicazioni riguardano l'installazione e la configurazione di Microsoft® Windows Server™ 2003, la preparazione del servizio di directory Active Directory® e la configurazione dei criteri IPsec.

Questa appendice fornisce inoltre le istruzioni di implementazione utilizzate per distribuire i criteri IPsec di base per lo scenario della Woodgrove Bank, descritto precedentemente in questa guida.

Utilizzare l'appendice insieme agli altri capitoli della guida che illustrano il processo di progettazione e la logica alla base delle decisioni di implementazione a cui si fa riferimento in questa appendice. Il documento descrive inoltre le attività e i processi necessari per creare e implementare un'efficace infrastruttura di base dei criteri IPsec. Prima di procedere alla lettura della presente appendice, è consigliabile consultare i capitoli precedenti della guida. *Prima* di implementare le indicazioni fornite con questa appendice, si consiglia inoltre di leggere e comprendere a fondo le implicazioni dei requisiti di supporto illustrati nel capitolo 6, "Gestione di un ambiente di isolamento del server e del dominio".

##### In questa pagina

[](#enaa)[Prerequisiti](#enaa)
[](#emaa)[Distribuzione dei criteri di base](#emaa)
[](#elaa)[Implementazione dei criteri IPSec](#elaa)
[](#ekaa)[Utilizzo del metodo graduale per abilitare i criteri IPsec di base](#ekaa)
[](#ejaa)[Strumenti e script per i test funzionali](#ejaa)
[](#eiaa)[Abilitazione dell'elenco filtri delle subnet protette dell'organizzazione sui restanti criteri](#eiaa)
[](#ehaa)[Abilitazione della configurazione del gruppo di accesso alla rete](#ehaa)
[](#egaa)[Abilitazione del dominio di isolamento](#egaa)
[](#efaa)[Abilitazione del gruppo di isolamento Nessun fallback](#efaa)
[](#eeaa)[Abilitazione del gruppo di isolamento Crittografia](#eeaa)
[](#edaa)[Abilitazione del gruppo di isolamento Limite](#edaa)
[](#ecaa)[Configurazione del dominio di isolamento come gruppo di isolamento predefinito](#ecaa)
[](#ebaa)[Test funzionali finali - Tutti i gruppi di isolamento abilitati](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prerequisiti

Questa sezione contiene informazioni utili per valutare l'idoneità dell'organizzazione all'implementazione della soluzione IPsec.

#### Prima di iniziare

È necessario conoscere i concetti di protocollo IPsec, di rete e di architettura di rete. È inoltre necessaria la conoscenza delle seguenti aree di Windows Server 2003:

-   Installazione del sistema operativo.

-   Concetti relativi ad Active Directory tra cui la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   La protezione dei sistemi Windows, inclusi concetti quali utenti, gruppi, controllo, elenchi di controllo dell'accesso (ACL, Access Control List), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

Prima di leggere la presente appendice, è necessario inoltre aver preso visione delle istruzioni di pianificazione fornite in questa guida e conoscere a fondo l'architettura e la progettazione della soluzione.

#### Prerequisiti organizzativi

È necessario consultarsi con altre persone dell'organizzazione che potrebbero essere coinvolte nell'implementazione della soluzione, fra le quali:

-   Finanziatori.

-   Personale addetto alla protezione e al controllo.

-   Personale addetto alla progettazione, amministrazione e gestione di Active Directory

-   Personale addetto alla progettazione, amministrazione e gestione di DNS (Domain Name System), server Web e della rete.

    **Nota:** a seconda della struttura dell'organizzazione IT, questi ruoli possono essere ricoperti da più persone oppure un numero ristretto di addetti può ricoprire più ruoli.

#### Prerequisiti per l'infrastruttura IT

Il contenuto dell'appendice presuppone inoltre l'esistenza della seguente infrastruttura IT:

-   Un dominio Windows Server 2003 con servizio Active Directory in modalità nativa o mista. Questa soluzione utilizza gruppi universali per l'applicazione dell'oggetto Criteri di gruppo (GPO, Group Policy Object). Se l'organizzazione non utilizza la modalità nativa o mista, è comunque possibile applicare l'oggetto Criteri di gruppo tramite l'uso di configurazioni di gruppo standard globali e locali. Tuttavia, poiché questa opzione è più complessa da gestire, la presente soluzione non la utilizza.

    **Nota**: Windows Server 2003 include numerosi miglioramenti relativi ai criteri IPsec. Nessun aspetto specifico di Windows Server 2003 impedisce l'utilizzo di questa soluzione con Windows 2000. Tuttavia, la soluzione è stata testata solo su un sistema Windows Server 2003 con servizio Active Directory. Per ulteriori informazioni sui miglioramenti apportati a IPsec in Windows Server 2003, consultare la pagina [New features for IPsec](http://technet.microsoft.com/en-us/library/cc739580.aspx) sul sito Web Microsoft all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/
    2003/standard/proddocs/en-us/ipsec\_whatsnew.asp.

-   Hardware del server in grado di supportare l'esecuzione di Windows Server 2003.

-   Licenze, supporti di installazione e codici "Product Key" di Windows Server 2003 Standard Edition e Enterprise Edition.

#### Prerequisiti per l'implementazione di base

Prima di eseguire le attività descritte nella presente appendice, è necessario verificare la presenza di determinati elementi, fondamentali per la riuscita dell'implementazione.

##### Requisiti hardware

Prima di distribuire l'infrastruttura IPsec di base, accertarsi che l'infrastruttura corrente sia fisicamente in grado di supportare l'implementazione di IPsec. La procedura di verifica di tale capacità è descritta nel capitolo 3 della presente guida, "Determinazione dello stato corrente dell'infrastruttura IT".

##### Strumenti

Per la configurazione dei criteri IPsec e la loro attivazione tramite gli oggetti Criteri di gruppo di Active Directory, sono disponibili quattro strumenti principali, ovvero:

-   **Netsh**. Strumento di riga di comando incluso in Windows Server 2003. Consente la configurazione dei criteri locali su sistema Windows Server 2003 e dei criteri di dominio. Questa soluzione utilizza gli script Netsh per configurare i criteri di dominio.

-   **Console di gestione Criteri di gruppo** (GPMC, Group Policy Management Console). Componente aggiuntivo dello strumento di gestione oggetti Criteri di gruppo che semplifica l'amministrazione dei criteri di gruppo all'interno dell'azienda. Lo strumento è disponibile per il download alla pagina [Group Policy Management Console with Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0a6d4c24-8cbd-4b35-9272-dd3cbfc81887&displaylang=en) nell'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?
    FamilyId=0A6D4C24-8CBD-4B35-9272-DD3CBFC81887&displaylang=en (in lingua inglese).

-   **Console di gestione criteri di protezione IP**. Strumento che consente all'amministratore di creare, visualizzare o modificare criteri IPsec, operazioni filtro ed elenchi filtri. Benché sia uno snap-in di Microsoft Management Console (MMC), non compare nell'elenco predefinito del menu Strumenti di amministrazione del computer. Per poterlo utilizzare, eseguire **mmc.exe** al prompt dei comandi e aggiungerlo manualmente.

-   **Console di gestione Monitor di protezione IP**. Strumento che consente all'amministratore di visualizzare le diverse regole applicate al computer, oltre alle associazioni di protezione (SA, Security Associations) in modalità principale e rapida ad esso associate. Analogamente alla Console di gestione criteri di protezione IP, questo strumento non compare nel menu Strumenti di amministrazione predefinito ed è pertanto necessario caricarlo manualmente mediante il programma **mmc.exe**.

Si raccomanda di installare tali strumenti sulle workstation del team di implementazione in modo che i membri del team abbiano il tempo di approfondire il funzionamento di ciascuno strumento prima dell'avvio dell'implementazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Distribuzione dei criteri di base

La Woodgrove Bank ha scelto di implementare la distribuzione spostando tutti i computer nel gruppo di isolamento Limite secondo un metodo graduale. In questo modo, gli amministratori hanno potuto agire con cautela e risolvere i problemi principali senza che ciò influisse in modo significativo sulla comunicazione tra computer. La distribuzione dei criteri senza il ricorso a subnet protette ha consentito al team amministrativo di individuare tutti i computer a cui era stato assegnato un criterio IPsec locale e di tenere conto di tale informazione. Con l'aggiunta delle subnet al criterio, gli eventuali conflitti individuati sono stati prontamente risolti.

Una volta impostato il funzionamento dei computer nell'ambito del criterio del gruppo di isolamento Limite, il team è quindi passato all'implementazione dei gruppi di isolamento standard, modalità non crittografata consentita in uscita e crittografia. Tali gruppi di isolamento sono stati distribuiti mediante il metodo di "distribuzione per gruppi" illustrato nel capitolo 4 della presente guida, "Progettazione e pianificazione dei gruppi di isolamento". Un insieme di computer è stato selezionato per il progetto pilota e aggiunto ai rispettivi gruppi di controllo dei nuovi criteri. Sono stati infine risolti eventuali problemi e aggiunti ulteriori computer fino al completamento di tutti i gruppi di isolamento.

[](#mainsection)[Inizio pagina](#mainsection)

### Implementazione dei criteri IPSec

Nelle organizzazioni di grandi dimensioni, il processo di assegnazione del criterio IPsec corretto a ciascun computer previsto può risultare piuttosto complesso. Il meccanismo dei criteri disponibile con il servizio Active Directory consente di semplificarlo in modo significativo. Le sezione seguente dell'appendice contiene informazioni utili per l'implementazione dei criteri IPsec.

#### Copia degli script di configurazione

Per configurare i criteri IPsec, è necessario innanzitutto copiare gli script di configurazione richiesti nel controller di dominio utilizzato per la loro memorizzazione. Per configurare il laboratorio della Woodgrove Bank, sono stati utilizzati gli script di configurazione disponibili con la soluzione. Nello scenario della Woodgrove Bank, è stata seguita le seguente procedura:

**Per copiare gli script di configurazione**

1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.

2.  Creare la cartella **C:\\IPsec Scripts**.

3.  Copiare i file degli script dalla cartella **Strumenti e modelli** della presente soluzione nella cartella **C:\\IPsec Scripts**.

#### Installazione della Console di gestione Criteri di gruppo

La Console di gestione Criteri di gruppo consente di installare e configurare gli oggetti Criteri di gruppo utilizzati dalla soluzione. L'installazione della Console di gestione Criteri di gruppo è necessaria solo su IPS-CH-DC-01, mentre è facoltativa su eventuali altri server.

**Nota:** l'installazione della GPMC modifica lievemente l'interfaccia utente di MMC Utenti e computer di Active Directory del computer su cui è installata. Per ulteriori informazioni sull'utilizzo della GPMC e per scaricare il file di installazione, consultare la pagina [Group Policy Management Console with Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0a6d4c24-8cbd-4b35-9272-dd3cbfc81887&displaylang=en) nell'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?
familyid=0a6d4c24-8cbd-4b35-9272-dd3cbfc81887&displaylang=en (in lingua inglese).

**Per installare la Console di gestione Criteri di gruppo**

1.  Scaricare il file di installazione **Gpmc.ms**i dall’area di download del sito Web Microsoft.

2.  Accertarsi di aver eseguito l’accesso a IPS-CH-DC-01 come membro del gruppo degli amministratori di dominio.

3.  In **Esplora risorse,** fare doppio clic sul file di installazione **Gpmc.msi**.

4.  Per installare la GPMC, seguire le istruzioni della procedura di installazione guidata e accettare tutte le impostazioni predefinite.

    **Importante:** è necessario installare la GPMC nella cartella Programmi di qualsiasi unità. È necessario inoltre utilizzare la cartella di installazione predefinita (GPMC) contenuta all'interno della cartella Programmi. Se si modifica il nome della cartella, sarà necessario aggiornarIo nel file **Constants.txt**. Nelle procedure che seguono vengono utilizzati alcuni strumenti installati dalla GPMC e, se la console viene installata in una posizione diversa, tali strumenti non potranno essere individuati, a meno che il file non venga aggiornato.

#### Implementazione di Elenchi filtri e Operazioni filtro IPsec

È possibile creare gli elenchi filtri e le operazioni filtro IPsec utilizzando lo strumento Netsh o lo snap-in MMC Gestione criteri di protezione IP.

Benché lo snap-in MMC Gestione criteri di protezione IP disponga di un'interfaccia grafica per IPsec, spesso gli amministratori preferiscono gestire e aggiornare gli script mediante lo strumento di riga di comando Netsh, che semplifica inoltre il trasferimento degli script da e verso insiemi di strutture o domini. In questa soluzione, per implementare gli elenchi filtri e le operazioni filtro IPsec sono stati utilizzati script Ntesh.

**Nota:** eseguire il test degli script in base agli archivi dei criteri locali su un computer con sistema operativo Windows Server 2003 impostando gli archivi su locale. Dopo aver eseguito il debugging degli script, modificare la configurazione dell'archivio impostando come attivo il dominio per l'importazione finale.

**Per creare gli elenchi filtri e le operazioni filtro IPsec**

1.  Connettersi al dominio IPS-CH-DC-01 come amministratore del dominio Americhe.

2.  Aprire un prompt dei comandi e digitare
    **netsh –f "c:\\IPsec Scripts\\PacketFilters.txt"**, quindi premere INVIO.

    **Nota:** se utilizzando lo script vengono creati elenchi filtri vuoti, nella riga di comando viene visualizzato il seguente messaggio di errore: **ERR IPsec \[05022\]: No filters in FilterList with name "&lt;Nome elenco filtri&gt;**.**"**, che può essere tranquillamente ignorato.

3.  Avviare lo snap-in MMC Gestione criteri di protezione IP e confermare l'avvenuta creazione degli elenchi e delle operazioni filtro in Active Directory.

    **Nota:** per effettuare i test in base al criterio locale, assicurarsi che lo script eseguito al punto 2 sia configurato come segue: **set store location=local**. Al punto 3, controllare che lo snap-in MMC sia impostato sul computer locale e non sul dominio.

#### Implementazione dei criteri IPSec

Una volta creati gli elenchi filtri e le operazioni filtro, è possibile eseguire i criteri IPsec.

**Nota:** i criteri creati dagli script sono configurati con un intervallo di polling di cinque minuti per consentire l'esecuzione di test.

Nella tabella riportata di seguito sono elencati il nome del criterio e il file di script mediante il quale il criterio viene creato. Il nome del file di script verrà utilizzato al punto 2 della seguente procedura.

**Tabella C.1. Associazione dei criteri IPsec ai file di script**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome del criterio IPsec</th>
<th style="border:1px solid black;" >Nome del file di script</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPSEC -  Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)</td>
<td style="border:1px solid black;">BoundaryIGPolicy.txt</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio IPsec gruppo di isolamento Nessun fallback (1.0.041001.1600)</td>
<td style="border:1px solid black;">NoFallbackIGPolicy.txt</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio IPsec dominio di isolamento (1.0.041001.1600)</td>
<td style="border:1px solid black;">IsolationDomainPolicy.txt</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)</td>
<td style="border:1px solid black;">EncryptionIGPolicy.txt</td>
</tr>
</tbody>
</table>
  
**Per creare i criteri IPsec**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Aprire un prompt dei comandi. Per ciascun criterio, digitare
  
    <codesnippet language displaylanguage containsmarkup="false">netsh –f "c:\\IPsec Scripts\\&lt;Script Filename&gt;" and then press ENTER.  
```
  
    **Nota:** se un elenco filtri rimane vuoto, Netsh visualizza un messaggio di errore che inizia con "ERR IPsec \[05022\]..." e che può essere tranquillamente ignorato.
  
3.  Avviare lo snap-in MMC Gestione criteri di protezione IP e confermare l'avvenuta creazione dei criteri IPSec in Active Directory.
  
    **Nota:** per effettuare i test in base al criterio locale, assicurarsi che lo script eseguito al punto 2 sia configurato come segue: **set store location=local**. Al punto 3, controllare che lo snap-in MMC sia impostato sul computer locale e non sul dominio.
  
#### Creazione degli oggetti GPO per i criteri IPsec
  
La Woodgrove Bank ha creato quattro oggetti GPO per recapitare i criteri IPsec. A ogni oggetto GPO è stato dato il nome del criterio IPsec a cui è assegnato. Finché i criteri rimarranno collegati all'interno di Active Directory, gli oggetti GPO non recapiteranno al dominio alcun criterio IPsec.
  
Nella tabella riportata di seguito, sono elencati i nomi degli oggetti GPO e il nome del criterio IPsec recapitato dal rispettivo oggetto GPO.
  
**Tabella C.2. Associazione degli oggetti GPO della Woodgrove Bank ai criteri IPsec**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome GPO</th>
<th style="border:1px solid black;" >Nome del criterio IPsec</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Limite</td>
<td style="border:1px solid black;">IPSEC -  Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Nessun fallback</td>
<td style="border:1px solid black;">IPSEC - Criterio IPsec gruppo di isolamento Nessun fallback (1.0.041001.1600)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio dominio di isolamento</td>
<td style="border:1px solid black;">IPSEC - Criterio IPsec dominio di isolamento (1.0.041001.1600)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Crittografia</td>
<td style="border:1px solid black;">IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)</td>
</tr>
</tbody>
</table>
  
**Per creare gli oggetti GPO dei criteri IPsec**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare la console di gestione Criteri di gruppo.
  
3.  Espandere **Insieme di strutture: corp.woodgrovebank.com**, il dominio e infine **americas.corp.woodgrovebank.com**.
  
4.  Fare clic con il pulsante destro del mouse su **Oggetti criteri di gruppo**, quindi fare clic su **Nuovo**.
  
5.  Nella casella di testo **Nome**, digitare *&lt;Nome GPO&gt;*, quindi fare clic su **OK**.
  
6.  Fare clic con il pulsante destro del mouse su ***&lt;Nome GPO&gt;,*** quindi scegliere **Modifica**.
  
7.  Espandere **Configurazione computer**, **Impostazioni di Windows** e **Impostazioni protezione**, infine scegliere **Criteri di protezione IP su Active Directory (corp.woodgrovebank.com)**.
  
8.  Nel riquadro a destra, fare clic con il pulsante destro del mouse su ***&lt;Nome criterio IPsec&gt;***, quindi scegliere **Assegna**.
  
9.  Verificare l'assegnazione del *&lt;nome criterio IPsec&gt;*, quindi chiudere l'Editor oggetti Criteri di gruppo.
  
10. Ripetere i punti da 4 a 9 per ciascuna coppia composta da *&lt;Nome GPO&gt;* e *&lt;Nome criterio IPsec&gt;* presente nella tabella precedente.
  
#### Impostazione della protezione per i criteri di gruppo IPsec
  
Per controllare l'applicazione dei criteri, la Woodgrove Bank ha utilizzato gli elenchi di controllo dell'accesso di protezione sull'oggetto GPO contenente i criteri IPsec. Il vantaggio principale è costituito dalla possibilità di collegare i criteri a livello di dominio, piuttosto che attraverso più unità organizzative (OU, Organizational Units), semplificando la gestione dell'applicazione dei criteri. Inoltre, è stata implementata una distribuzione in più fasi, che ha consentito di evitare lo spostamento degli account di computer su unità organizzative specifiche. Gli account dei computer coinvolti nel progetto pilota sono infatti stati aggiunti ai rispettivi gruppi. Perché questo metodo risulti attuabile, è però necessario che l'organizzazione disponga di strumenti di gestione dei gruppi efficaci.
  
##### Creazione dei gruppi
  
È stato creato un insieme di gruppi per controllare le modalità di applicazione del criterio all'interno dell'organizzazione della Woodgrove Bank. Poiché l'insieme di strutture della Woodgrove Bank era in modalità nativa, per controllare i criteri in tutti i domini sono stati utilizzati gruppi universali.
  
**Tabella C.3. Gruppi universali della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome gruppo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CG_NoIPsec_computers</td>
<td style="border:1px solid black;">Gruppo universale costituito da account di computer che non rientrano nell'ambiente IPsec, tipicamente gli account dei computer infrastrutturali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CG_BoundaryIG_computers</td>
<td style="border:1px solid black;">Gruppo universale costituito da account di computer autorizzati a comunicare con computer non attendibili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CG_ EncryptionIG_computers</td>
<td style="border:1px solid black;">Gruppo universale costituito da account di computer facenti parte del gruppo di isolamento Crittografia.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CG_ IsolationDomain_computers</td>
<td style="border:1px solid black;">Gruppo universale costituito da account di computer facenti parte del dominio di isolamento.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CG_NoFallbackIG_computers</td>
<td style="border:1px solid black;">Gruppo universale costituito da account di computer facenti parte del gruppo di isolamento Nessun fallback.</td>
</tr>
</tbody>
</table>
  
**Per creare i gruppi universali della Woodgrove Bank**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01.
  
2.  Fare clic con il pulsante destro del mouse sul contenitore **Utenti**, scegliere **Nuovo**, quindi **Gruppo**.
  
3.  Nella casella di testo **Nome gruppo**, digitare il primo *&lt;nome gruppo&gt;* elencato nella tabella precedente.
  
4.  Selezionare **Gruppo di protezione universale**, quindi fare clic su **OK**.
  
5.  Ripetere i punti da 2 a 4 per ciascun gruppo.
  
6.  Fare clic con il pulsante destro del mouse sul primo ***&lt;nome gruppo&gt;***, quindi scegliere **Proprietà**.
  
7.  Nella casella di testo **Descrizione**, digitare la prima *&lt;descrizione&gt;* elencata nella tabella precedente.
  
8.  Scegliere **OK**.
  
9.  Ripetere i punti da 6 a 8 per ciascun gruppo elencato nella tabella precedente.
  
##### Configurazione della protezione GPO
  
I gruppi sono utilizzati per controllare l'assegnazione dei criteri ai computer che partecipano all'ambiente IPsec. È necessario configurare gli ACL di protezione su ciascuno dei criteri IPsec appena creati, in modo che vengano configurati i gruppi corretti. Nella tabella seguente, sono riportati gli ACL da aggiungere a ciascun oggetto GPO.
  
**Nota:** se un'organizzazione intende delegare i diritti di amministrazione per la gestione dei criteri IPsec a un gruppo diverso da quello degli amministratori di dominio, è necessario garantire al gruppo amministrativo delegato il controllo completo del contenitore Protezione IP in Active Directory.
  
**Tabella C.4. Autorizzazioni per il gruppo di criteri della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome GPO</th>
<th style="border:1px solid black;" >Nome gruppo o account</th>
<th style="border:1px solid black;" >Diritti assegnati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Limite</td>
<td style="border:1px solid black;">CG_NoIPsec_computers</td>
<td style="border:1px solid black;">Nega applicazione Criteri di gruppo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">CG_BoundaryIG_computers</td>
<td style="border:1px solid black;">Consenti lettura e applicazione dei criteri di gruppo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Nessun fallback</td>
<td style="border:1px solid black;">CG_NoIPsec_computers</td>
<td style="border:1px solid black;">Nega applicazione Criteri di gruppo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">CG_NoFallbackIG_computers</td>
<td style="border:1px solid black;">Consenti lettura e applicazione dei criteri di gruppo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio dominio di isolamento</td>
<td style="border:1px solid black;">CG_NoIPsec_computers</td>
<td style="border:1px solid black;">Nega applicazione Criteri di gruppo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio dominio di isolamento</td>
<td style="border:1px solid black;">CG_ IsolationDomain_computers</td>
<td style="border:1px solid black;">Consenti lettura e applicazione dei criteri di gruppo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Crittografia</td>
<td style="border:1px solid black;">CG_NoIPsec_computers</td>
<td style="border:1px solid black;">Nega applicazione Criteri di gruppo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">CG_ EncryptionIG_computers</td>
<td style="border:1px solid black;">Consenti lettura e applicazione dei criteri di gruppo</td>
</tr>
</tbody>
</table>
  
**Nota:** il criterio gruppo di isolamento Limite è configurato in modo da consentire al gruppo Computer del dominio di applicare il criterio del processo di creazione iniziale collocando il gruppo Computer del dominio all'interno del gruppo CG\_BoundaryIG\_computers. Una volta spostati tutti i computer nei rispettivi gruppi, i computer del dominio verranno rimossi dal gruppo CG\_BoundaryIG\_computers.
  
**Per impostare le autorizzazioni del gruppo sul GPO**
  
1.  Avviare la Console di gestione Criteri di gruppo su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere **Insieme di strutture: corp.woodgrovebank.com**, il dominio, **americas.corp.woodgrovebank.com** e infine **Oggetti Criteri di gruppo**.
  
3.  Fare clic sul primo ***&lt;nome GPO&gt;*** elencato nella tabella precedente, quindi scegliere la scheda **Delega**.
  
4.  Fare clic sul pulsante **Avanzate**.
  
5.  Nella casella di scorrimento **Nome utente o gruppo**, fare clic su **Utenti autenticati** e deselezionare la casella di controllo **Applica criteri di gruppo** relativa al diritto ALLOW.
  
6.  Fare clic sul pulsante **Aggiungi**.
  
7.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare ogni *&lt;nome gruppo o account&gt;* elencato nella tabella precedente, separando i nomi con un punto e virgola, quindi scegliere **OK**.
  
8.  Nella casella di testo **Utenti e gruppi**, selezionare il ***&lt;nome gruppo o account&gt;****,* quindi impostare i *&lt;diritti assegnati&gt;* nelle caselle di controllo **Autorizzazioni**.
  
9.  Ripetere il punto 8 per ogni *&lt;nome gruppo o account&gt;* associato al criterio *&lt;Nome criterio&gt;*.
  
10. Scegliere **OK**.
  
11. Se il diritto assegnato è di tipo DENY, quando viene visualizzato il messaggio, scegliere **Sì**, in caso contrario andare al punto 12.
  
12. Ripetere i punti da 3 a 11 per ciascun *&lt;nome criterio&gt;*.
  
    **Nota:** controllare che agli utenti autenticati immessi siano state concesse solo autorizzazioni di lettura per gli ACL di protezione di ciascun criterio. Infatti, se vengono concesse anche autorizzazioni di applicazione, il criterio viene distribuito su tutti i computer.
  
#### Blocco delle connessioni ai computer del gruppo di isolamento Crittografia da parte dei computer del gruppo di isolamento Limite
  
Per la Woodgrove Bank, era necessario che i computer del gruppo di isolamento Limite non potessero avviare alcuna connessione con i computer del gruppo di isolamento Crittografia. Per implementare tale limitazione, è stato creato un gruppo denominato DNAG\_EncryptionIG\_computers, i cui membri non hanno accesso ai computer appartenenti al gruppo di isolamento Crittografia. Il criterio gruppo di isolamento Crittografia è stato configurato in modo che al gruppo DNAG\_EncryptionIG\_computers venisse concesso il diritto "Nega accesso al computer dalla rete" e che al suo interno venisse inserito il gruppo CG\_BoundaryIG\_computers. Questa configurazione è stata ottenuta modificando il GPO IPSEC - Criterio gruppo di isolamento Crittografia.
  
**Per creare il gruppo DNAG\_EncryptionIG\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01.
  
2.  Fare clic con il pulsante destro del mouse sul contenitore **Utenti**, scegliere **Nuovo**, quindi **Gruppo**.
  
3.  Nella casella di testo **Nome gruppo**, digitare DNAG\_EncryptionIG\_computers.
  
4.  Selezionare il gruppo di protezione **Locale al dominio**, quindi fare clic su **OK**.
  
5.  Fare clic con il pulsante destro del mouse su **DNAG\_EncryptionIG\_computers**, quindi scegliere **Proprietà**.
  
6.  Nella casella di testo **Descrizione**, digitare Utilizzato per negare l'accesso al gruppo di isolamento Crittografia.
  
7.  Scegliere **OK**.
  
**Per configurare IPSEC - Criterio gruppo di isolamento Crittografia in modo che blocchi i membri del gruppo DNAG\_EncryptionIG\_computers**
  
1.  Avviare la Console di gestione Criteri di gruppo su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere **Insieme di strutture: corp.woodgrovebank.com**, il dominio, **americas.corp.woodgrovebank.com** e infine **Oggetti Criteri di gruppo**.
  
3.  Fare clic con il pulsante destro del mouse su **IPSEC - Criterio gruppo di isolamento Crittografia**, quindi scegliere **Modifica**.
  
4.  Espandere **Configurazione computer**, **Impostazioni di Windows**, **Impostazioni di protezione**, **Criteri locali** e infine **Assegnazione diritti utente**.
  
5.  Fare clic con il pulsante destro del mouse su **Nega accesso al computer dalla rete**, quindi scegliere **Proprietà**.
  
6.  Selezionare la casella di controllo **Definisci le impostazioni relative ai criteri**.
  
7.  Fare clic sul pulsante **Aggiungi utente o gruppo**.
  
8.  Fare clic sul pulsante **Sfoglia**.
  
9.  Nel campo di testo, digitare DNAG\_EncryptionIG\_computers, quindi scegliere **OK**.
  
10. Scegliere nuovamente **OK**.
  
11. Fare clic su **OK** per chiudere la pagina **Proprietà**.
  
12. Chiudere l'editor dei criteri di gruppo.
  
13. Chiudere la console di gestione Criteri di gruppo.
  
**Per aggiungere al gruppo DNAG\_EncryptionIG\_computers il gruppo CG\_BoundaryIG\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **DNAG\_EncryptionIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare CG\_BoundaryIG\_computers, quindi fare clic su **OK**.
  
6.  Scegliere **OK**.
  
#### Aggiunta di computer del dominio al gruppo limite
  
Durante la distribuzione iniziale, il gruppo di isolamento Limite è il gruppo predefinito per i client aziendali protetti da IPsec. Per implementare il piano, al gruppo CG\_BoundaryIG\_computers viene aggiunto il gruppo Computer del dominio.
  
**Per aggiungere computer del dominio al gruppo CG\_BoundaryIG\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_BoundaryIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare Computer del dominio, quindi fare clic su **OK**.
  
6.  Scegliere nuovamente **OK**.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra l'aggiunta del gruppo Computer del dominio al gruppo CG\_BoundaryIG\_computers e l'applicazione del criterio del gruppo di isolamento Limite. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
#### Aggiunta di server dell'infrastruttura al gruppo CG\_NoIPSec\_Computers
  
Per garantire che i server dell'infrastruttura non ricevano un criterio che potrebbe interrompere la comunicazione (per esempio in caso di modifica dell'indirizzo IP di un server), al gruppo di protezione CG\_NoIPsec\_computers sono stati aggiunti i seguenti account dei computer infrastrutturali.
  
-   IPS-RT-DC-01
  
-   IPS-CH-DC-01
  
**Per aggiungere server dell'infrastruttura al gruppo CG\_NoIPsec\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_NoIPsec\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare il nome di ciascun computer dell'elenco precedente, separando i nomi con un punto e virgola, quindi scegliere **OK**.
  
7.  Scegliere nuovamente **OK**.
  
#### Collegamento dei criteri IPsec e degli oggetti GPO in un ambiente di dominio
  
Prima di procedere alla distribuzione, è necessario collegare i criteri IPsec a determinate posizioni all'interno dell'ambiente di dominio. Poiché la Woodgrove Bank ha scelto di amministrare gli oggetti GPO attraverso i gruppi di protezione, la struttura delle unità organizzative non riveste un'importanza fondamentale relativamente alla distribuzione dei criteri. Tuttavia, in presenza di unità organizzative che blocchino l'applicazione del criterio, perché l'applicazione riesca sarà necessario collegare direttamente gli oggetti GPO IPsec alle unità organizzative. In alternativa, è possibile attivare l'applicazione del criterio agli oggetti GPO IPsec del dominio.
  
**Per collegare i criteri IPsec agli oggetti GPO esistenti**
  
1.  Avviare la GPMC collegandosi come amministratore di dominio.
  
2.  Espandere il dominio.
  
3.  Fare clic con il pulsante destro del mouse sul nome del dominio, quindi scegliere **Collega oggetto Criteri di gruppo esistente**.
  
4.  Selezionare dall'elenco **Oggetti Criteri di gruppo** tutti i criteri il cui nome inizia con IPSEC, quindi scegliere **OK**.
  
5.  Nel riquadro a destra, ordinare i criteri come illustrato nella tabella seguente con l'ausilio dei tasti freccia.
  
    **Tabella C.5. Ordine di collegamento oggetti Criteri di gruppo a livello di dominio**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Ordine di collegamento</th>
    <th style="border:1px solid black;" >Nome oggetto Criteri di gruppo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">1</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Crittografia</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">2</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Nessun fallback</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">3</td>
    <td style="border:1px solid black;">IPSEC - Criterio dominio di isolamento</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">4</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Limite</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">5</td>
    <td style="border:1px solid black;">Default Domain Policy</td>
    </tr>
    </tbody>
    </table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Utilizzo del metodo graduale per abilitare i criteri IPsec di base
  
L'implementazione dell'infrastruttura IPsec prevede innanzitutto la distribuzione del criterio del gruppo di isolamento Limite secondo un metodo graduale. Benché nell'ambiente della Woodgrove Bank il gruppo di isolamento Limite non funga da dominio di isolamento per tutti i computer dell'ambiente, è stato configurato in modo che, nella prima fase di distribuzione, venga applicato a tutti i computer.
  
Poiché il criterio del gruppo di isolamento Limite consente e accetta le comunicazioni non protette da IPsec, è stato considerato il più sicuro per una distribuzione graduale nell'ambiente. Inizialmente, la distribuzione del criterio è stata effettuata senza definire alcuna subnet protetta. Ciò ha consentito agli amministratori della Woodgrove Bank di correggere gli eventuali criteri IPsec locali. Successivamente, le subnet vengono aggiunte e sottoposte a verifica una alla volta, per garantire che la negoziazione IPsec sia avvenuta correttamente.
  
#### Aggiunta delle subnet all'elenco filtri delle subnet protette
  
Dopo l'applicazione del criterio del gruppo di isolamento Limite ai computer dell'organizzazione e la risoluzione di eventuali conflitti con i criteri IPsec locali esistenti, gli amministratori della Woodgrove Bank si sono concentrati sulla creazione del criterio.
  
Il processo consiste nell'identificare le subnet dell'organizzazione che occorre proteggere. Le subnet così identificate sono state aggiunte al criterio una alla volta. Dopo l'aggiunta della prima voce all'elenco filtri, questo è stato aggiunto al criterio.
  
Dopo l'aggiunta di ciascuna subnet, è stato considerato il tempo necessario all'applicazione del criterio ai computer dell'organizzazione e sono stati risolti tutti gli eventuali conflitti. Il processo è stato poi ripetuto fino all'intera distribuzione delle subnet protette incluse nell'elenco filtri.
  
Nella tabella riportata di seguito, sono elencate le subnet protette utilizzate in laboratorio presso la Woodgrove Bank per riprodurre fedelmente la rete di produzione aziendale.
  
**Tabella C.6. Elenco delle subnet protette utilizzate nel laboratorio di test della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Subnet</th>
<th style="border:1px solid black;" >Netmask</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">192.168.1.0</td>
<td style="border:1px solid black;">255.255.255.0</td>
<td style="border:1px solid black;">Subnet LAN organizzazione 192.168.1.0/24</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">172.10.1.0</td>
<td style="border:1px solid black;">255.255.255.0</td>
<td style="border:1px solid black;">Subnet LAN organizzazione 172.10.1.0/24</td>
</tr>
</tbody>
</table>
  
**Per creare la prima voce dell'elenco filtri delle subnet protette**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Gestione criteri di protezione IP.
  
3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.
  
4.  Nella scheda **Gestisci elenchi filtri IP**, scegliere **IPSEC - Subnet protette organizzazione**, quindi fare clic su **Modifica**.
  
5.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.
  
6.  Scegliere **Aggiungi**.
  
7.  Nella scheda **Indirizzi**, scegliere **Qualsiasi indirizzo IP** dall'elenco a discesa **Indirizzo di origine**.
  
8.  Nell'elenco a discesa **Indirizzo di destinazione**, scegliere **Subnet IP specifica**, quindi inserire nelle caselle **Indirizzo IP** e **subnet mask** le informazioni contenute nella tabella precedente.
  
9.  Assicurarsi che l'opzione **Speculare** sia selezionata.
  
10. Nella scheda **Descrizione**, inserire la descrizione corrispondente contenuta nella tabella precedente.
  
11. Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà filtri IP**.
  
12. Fare clic su **OK** per chiudere la finestra di dialogo **Elenco filtri IP**.
  
13. Fare clic su **Chiudi** per chiudere la finestra di dialogo **Gestisci elenchi filtri IP e operazioni filtro**.
  
**Per aggiungere l'elenco filtri delle subnet protette al criterio del gruppo di isolamento Limite**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Gestione criteri di protezione IP.
  
3.  Fare clic con il pulsante destro del mouse su **IPSEC - Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)** e scegliere **Proprietà**.
  
4.  Nella scheda **Regole**, assicurarsi che la casella di controllo **Utilizza Aggiunta guidata** non sia selezionata, quindi fare **clic su** **Aggiungi**.
  
5.  Nella scheda **Elenco filtri IP**, scegliere **IPSEC - Subnet protette organizzazione**.
  
6.  Nella scheda **Operazione filtro**, scegliere **IPSEC - Modalità di richiesta (Accetta in ingresso, Consenti in uscita)**.
  
7.  Nella scheda **Tipo di connessione**, assicurarsi che la casella di controllo **Tutte le connessioni di rete** sia selezionata.
  
8.  Nella scheda **Impostazioni tunnel**, assicurarsi che la casella di controllo **Questa regola non specifica un tunnel IPsec** sia selezionata.
  
9.  Nella scheda **Metodi di autenticazione**, assicurarsi che il metodo Kerberos sia l'unico metodo elencato.
  
10. Fare clic su **OK** per chiudere la finestra di dialogo **Modifica regole - Proprietà**.
  
11. Fare clic su **OK** per chiudere la finestra di dialogo **IPSEC - Criterio IPsec di isolamento Limite (1.0.041001.1600) - Proprietà**.
  
12. Attendere l'applicazione del criterio, quindi eseguire la procedura di verifica descritta nella sezione "Verifica della distribuzione di base" della presente appendice.
  
**Per aggiungere le subnet rimanenti all'elenco filtri delle subnet protette**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Gestione criteri di protezione IP.
  
3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.
  
4.  Nella scheda **Gestisci elenchi filtri IP**, scegliere **IPSEC - Reti protette organizzazione**, quindi fare clic su **Modifica**.
  
5.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.
  
6.  Scegliere **Aggiungi**.
  
7.  Nella scheda **Indirizzi**, scegliere **Qualsiasi indirizzo IP** dall'elenco a discesa **Indirizzo di origine**.
  
8.  Nell'elenco a discesa **Indirizzo di destinazione**, scegliere **Subnet IP specifica**, quindi inserire nelle caselle relative a indirizzo IP e subnet mask le informazioni contenute nella tabella precedente.
  
9.  Assicurarsi che l'opzione **Speculare** sia selezionata.
  
10. Nella scheda **Descrizione**, inserire la descrizione corrispondente contenuta nella tabella precedente.
  
11. Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà filtri IP**.
  
12. Fare clic su **OK** per chiudere la finestra di dialogo **Elenco filtri IP**.
  
13. Fare clic su **Chiudi** per chiudere la finestra di dialogo **Gestisci elenchi filtri IP e operazioni filtro**.
  
14. Attendere l'applicazione del criterio, quindi eseguire la procedura di verifica descritta nella sezione "Verifica della distribuzione di base" della presente appendice.
  
15. Ripetere i punti da 2 a 14 per ciascuna subnet.
  
#### Verifica della distribuzione di base
  
Dopo aver creato e distribuito, allo stato inattivo, gli oggetti dei criteri in Active Directory, prima di configurare il criterio di base perché applichi il gruppo di isolamento di base a tutti i computer dell'organizzazione, è consigliabile procedere a una verifica. Tale verifica consente di ridurre al massimo potenziali problemi degli host che partecipano alla comunicazione in caso di errori della configurazione di base.
  
##### Test funzionali di implementazione
  
Il test più semplice da eseguire per verificare il funzionamento di IPsec è tentare di eseguire i comandi di **net view** su computer collegati alla rete protetta dell'organizzazione e su computer non appartenenti a subnet elencate nella rete protetta dell'organizzazione.
  
I computer appartenenti a una subnet protetta negozieranno una SA non trasferibile visibile nello snap-in MMC Monitor di protezione IP. Tra un computer protetto da IPsec e un computer non appartenente a una subnet elencata nella rete protetta dell'organizzazione, si creerà invece una SA trasferibile.
  
**Per verificare il funzionamento dei criteri IPsec applicati**
  
1.  Da un computer appartenente a una subnet protetta, aprire un prompt dei comandi e digitare  
    net view \\\\&lt;nome computer&gt;, quindi premere INVIO. Per il *&lt;nome computer&gt;,* utilizzare sia i nomi di computer appartenenti ad altre subnet protette, sia i nomi di computer non appartenenti alle subnet protette.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP dal computer su cui sono stati eseguiti i comandi **net view**.
  
3.  Espandere **Monitor di protezione IP**, ***&lt;nome computer&gt;*** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
4.  Per ogni computer su cui è stato eseguito un comando **net view**, verificare quanto segue:
  
    -   Gli host collegati alla rete protetta dell'organizzazione hanno negoziato una SA non trasferibile. La colonna **Integrità ESP***non* è impostata su &lt;nessuna&gt;.
  
    -   Gli host non protetti da IPsec hanno negoziato una SA trasferibile. La colonna **Integrità ESP** è impostata su &lt;nessuna&gt;.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Strumenti e script per i test funzionali
  
Nel corso dei test funzionali, è necessario monitorare un certo numero di impostazioni di configurazione. Benché sia possibile monitorare gran parte di queste impostazioni tramite strumenti standard, due operazioni richiedono l'utilizzo di strumenti di norma non molto conosciuti dagli amministratori. Tali operazioni consistono nell'identificare il criterio IPsec attivo sul computer e determinare il tipo di SA che è stato negoziato.
  
#### Verifica dell'applicazione del criterio IPsec
  
Identificare il criterio IPsec attivo su un computer presenta delle difficoltà, poiché non esiste un metodo supportato da tutte le piattaforme. In alcuni casi è possibile identificare il criterio IPsec tramite l'interfaccia grafica utente (GUI, Graphical User Interface), mentre in altri casi è necessario ricorrere a uno strumento di riga di comando che può essere installato o meno con il sistema operativo.
  
##### Windows 2000
  
Nei computer che eseguono Windows 2000 Server, l'amministratore può identificare il criterio IPsec corrente tramite il comando Netdiag. Per recuperare il nome del criterio e altre informazioni, l'amministratore esegue l'accesso al computer, apre un prompt dei comandi e digita quanto segue:
  
<codesnippet language displaylanguage containsmarkup="false">Netdiag /test:IPsec  
```  
Di seguito viene riportato un esempio di output del comando:
  
<codesnippet language displaylanguage containsmarkup="false">IP Security test . . . . . . . . . : Passed     Directory IPsec Policy Active: ' IPSEC – Isolation Domain IPsec Policy (1.0.041001.1600)'  
```  
##### Windows XP
  
Nei computer che eseguono Windows XP, l'amministratore può identificare il criterio IPsec corrente tramite lo strumento di riga di comando **IPseccmd.exe**. Per recuperare il nome del criterio e altre informazioni, l'amministratore esegue l'accesso al computer, apre un prompt dei comandi e digita quanto segue:
  
<codesnippet language displaylanguage containsmarkup="false">IPseccmd show gpo  
```  
Di seguito viene riportato un esempio di output del comando:
  
<codesnippet language displaylanguage containsmarkup="false">Active Directory Policy -----------------------      Directory Policy Name: IPSEC – Isolation Domain IPsec Policy (1.0.041001.1600)      Description: Isolation Domain Policy (Allow Outbound)      Last Change: Fri Sep 03 15:20:29 2004      Group Policy Object: IPSEC – Isolation Domain Policy      Organizational Unit: LDAP://DC=americas,DC=woodgrovebank,DC=com      Policy Path: LDAP://CN=IPsecPolicy{efa2185d-1a1d-40f6- b977-314f152643ca},CN=IP Security,CN=System,DC=americas,DC=woodgrovebank,DC=com  
```  
##### Windows Server 2003
  
Nei computer che eseguono Windows Server 2003, l'amministratore può identificare il criterio IPsec corrente tramite lo strumento di riga di comando Netsh. Per recuperare il nome del criterio e altre informazioni, l'amministratore esegue l'accesso al computer, apre un prompt dei comandi e digita quanto segue:
  
<codesnippet language displaylanguage containsmarkup="false">netsh IPsec static show gpoassignedpolicy  
```  
Di seguito viene riportato un esempio di output del comando:
  
<codesnippet language displaylanguage containsmarkup="false">Source Machine          : Local Computer GPO for &lt;IPS-TZ-W2K-02&gt; GPO Name                : IPSEC – Isolation Domain Policy Local IPsec Policy Name : NONE AD IPsec Policy Name    : IPSEC – Isolation Domain IPsec Policy (1.0.041001.1600) AD Policy DN            : LDAP://CN=IPsecPolicy {efa2185d-1a1d-40f6-b977-314f152643ca},CN=IP Security,CN=System,DC=americas,DC=woodgrovebank,DC=com Local IPsec Policy Assigned: Yes, but AD Policy is Overriding  
```  
#### Uso dello strumento Monitor di protezione IP per determinare il tipo di SA
  
Lo snap-in MMC Monitor di protezione IP viene utilizzato per esaminare le SA in modalità principale e rapida, i filtri associati, i criteri IKE (Internet Key Exchange) e quelli di negoziazione. Durante la risoluzione dei problemi, è possibile ricorrere allo snap-in MMC Monitor di protezione IP per determinare il tipo di SA negoziate tra peer. Esaminando le SA dalla struttura **Modalità rapida**, gli amministratori di sistema sono in grado di identificare i peer IPsec del computer su cui è in esecuzione lo strumento.
  
Quando un computer negozia una connessione IPsec, viene creata una SA non trasferibile, il cui valore all'interno dei campi **Autenticazione**, **Confidenzialità ESP** o **Integrità ESP** sarà diverso da &lt;Nessuno&gt;. Per esempio, l'incapsulamento ESP con SHA1, ma senza autenticazione, all'interno del campo **Integrità ESP** conterrà il valore HMAC-SHA1, mentre conterrà &lt;Nessuno&gt; negli altri due campi. Se la SA non trasferibile, inoltre, ha negoziato la crittografia, il campo **Confidenzialità ESP** conterrà il valore DES o 3DES.
  
Una SA trasferibile, invece, conterrà il valore &lt;Nessuno&gt; in tutti i campi, indicando che il risponditore ha utilizzato una modalità non crittografata.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione dell'elenco filtri delle subnet protette dell'organizzazione sui restanti criteri
  
Prima di abilitare i restanti criteri IPsec, è necessario aggiungere a ciascun criterio l'elenco filtri della rete protetta dell'organizzazione. Questa operazione è necessaria poiché, quando sono stati creati i criteri, l'elenco filtri della rete protetta dell'organizzazione era vuoto e non poteva dunque essere aggiunto ai criteri.
  
In una sezione precedente della presente appendice, è stato implementato l'elenco filtri della rete protetta dell'organizzazione ed è ora possibile aggiungerlo ai restanti criteri. Nella tabella seguente, sono riportati i nomi dei criteri e l'operazione filtro associata assegnata all'elenco filtri della rete protetta dell'organizzazione.
  
**Tabella C.7. Associazione dei criteri alle operazioni filtro**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome criterio</th>
<th style="border:1px solid black;" >Operazione filtro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio IPsec  gruppo di isolamento Nessun fallback (1.0.041001.1600)</td>
<td style="border:1px solid black;">IPSEC - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPSEC - Criterio IPsec dominio di isolamento (1.0.041001.1600)</td>
<td style="border:1px solid black;">IPSEC - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)</td>
<td style="border:1px solid black;">IPSEC - Modalità di richiesta crittografia (Ignora in ingresso, Impedisci in uscita)</td>
</tr>
</tbody>
</table>
  
**Per aggiungere l'elenco filtri della rete protetta dell'organizzazione ai criteri IPsec**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Gestione criteri di protezione IP.
  
3.  Fare clic con il pulsante destro del mouse sul **&lt;*nome criterio*&gt;**, quindi scegliere **Proprietà**.
  
4.  Nella scheda **Regole**, fare clic su **Aggiungi**.
  
5.  Nella scheda **Elenco filtri IP**, scegliere **IPSEC - Subnet protette organizzazione**.
  
6.  Nella scheda **Operazione filtro**, fare clic sulla rispettiva **&lt;*operazione filtro*&gt;** contenuta nella tabella C.7.
  
7.  Nella scheda **Tipo di connessione**, assicurarsi che la casella di controllo **Tutte le connessioni di rete** sia selezionata.
  
8.  Nella scheda **Impostazioni tunnel**, assicurarsi che la casella di controllo **Questa regola non specifica un tunnel IPsec** sia selezionata.
  
9.  Nella scheda **Metodi di autenticazione**, assicurarsi che il metodo Kerberos sia l'unico metodo elencato.
  
10. Fare clic su **OK** per chiudere la finestra di dialogo **Modifica regole - Proprietà**.
  
11. Fare clic su **OK** per chiudere la finestra di dialogo **&lt;*Nome criterio*&gt;** **Proprietà**.
  
12. Ripetere i punti da 3 a 11 per ciascun criterio elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione della configurazione del gruppo di accesso alla rete
  
I gruppi di accesso alla rete consentono di limitare ulteriormente il risponditore IPsec in modo che accetti solo le connessioni da parte di un gruppo selezionato di computer iniziatori e utenti identificati. Per esempio, mediante i gruppi di accesso alla rete gli amministratori possono configurare i computer client dei dirigenti in modo che accettino solo traffico in entrata proveniente dai computer dei dirigenti, mantenendo comunque la capacità di inviare traffico ad altre risorse.
  
**Nota:** si consiglia di prestare particolare attenzione quando si definisce questa opzione, poiché se non vengono inclusi nel gruppo di accesso alla rete, è possibile che i computer preposti all'avvio della comunicazione con il gruppo di accesso alla rete (per esempio, i sistemi di monitoraggio che utilizzano il polling) non riescano ad eseguire l'operazione.
  
#### Implementazione dei gruppi di accesso alla rete
  
I progettisti della Woodgrove Bank hanno deciso di implementare i gruppi d accesso alla rete utilizzando i gruppi locali di dominio. Successivamente, tali gruppi sono stati utilizzati per definire gli iniziatori. Agli iniziatori è stato concesso il diritto "Accedi al computer dalla rete" relativamente ai risponditori e il gruppo Utenti autenticati è stato rimosso dal diritto. La Woodgrove Bank ha implementato il gruppo di accesso alla rete utilizzando i gruppi locali di dominio perché memorizzati nel ticket di sessione che viene aggiornato ogni 60 minuti. Se fossero stati utilizzati i gruppi globali o universali, il gruppo di accesso alla rete sarebbe stato memorizzato nel ticket di concessione ticket (TGT, Ticket-Granting Ticket), il cui ciclo di vita è di 8 ore. Utilizzando invece i gruppi locali di dominio, le modifiche apportate ai gruppi vengono rese effettive molto più rapidamente.
  
**Nota:** benché per implementare i gruppi di accesso alla rete questa soluzione utilizzi i gruppi locali di dominio dotati di diritto "Accedi al computer dalla rete", per implementare singoli gruppi di accesso alla rete possono essere utilizzate chiavi già condivise o certificati.
  
I progettisti della Woodgrove Bank hanno identificato un singolo gruppo di rete, utilizzato per controllare l'accesso al gruppo di isolamento Crittografia.
  
##### Creazione di gruppi di protezione per il controllo degli accessi
  
**Tabella C.8. Gruppi di protezione gruppo di accesso alla rete della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome gruppo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ANAG _EncryptedResourceAccess_computers</td>
<td style="border:1px solid black;">Gruppo locale di dominio utilizzato per limitare il numero dei computer con accesso alle risorse crittografate</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ANAG _EncryptedResourceAccess_users</td>
<td style="border:1px solid black;">Gruppo locale di dominio utilizzato per limitare il numero degli utenti che possono avviare la comunicazione con le risorse crittografate</td>
</tr>
</tbody>
</table>
  
**Per creare i gruppi elencati nella tabella precedente**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01.
  
2.  Fare clic con il pulsante destro del mouse sul contenitore **Utenti**, scegliere **Nuovo**, quindi **Gruppo**.
  
3.  Nella casella di testo **Nome gruppo**, digitare il *&lt;nome gruppo&gt;* elencato nella tabella precedente.
  
4.  In **Ambito del gruppo,** selezionare **Locale al dominio**, quindi fare clic su **OK**.
  
5.  Ripetere i punti da 2 a 4 per ciascun gruppo.
  
6.  Fare clic con il pulsante destro del mouse sul **&lt;*nome gruppo*&gt;**, quindi scegliere **Proprietà**.
  
7.  Nella casella di testo **Descrizione**, digitare la prima &lt;*descrizione*&gt; della tabella precedente.
  
8.  Scegliere **OK**.
  
9.  Ripetere i punti da 6 a 8 per ciascun gruppo elencato nella tabella precedente.
  
##### Aggiunta di account ai gruppi di protezione gruppo di accesso alla rete
  
La Woodgrove Bank ha aggiunto i computer identificati, con funzione di iniziatori del traffico all'interno del gruppo di accesso alla rete, ai gruppi locali di dominio appropriati, utilizzati per implementare il gruppo di accesso alla rete.
  
Nella tabella riportata di seguito, viene indicata l'appartenenza del gruppo di accesso alla rete identificato dalla Woodgrove Bank.
  
**Tabella C.9. Appartenenza dei gruppi di isolamento della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome gruppo</th>
<th style="border:1px solid black;" >Membri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ANAG _EncryptedResourceAccess_computers</td>
<td style="border:1px solid black;">IPS-SQL-DFS-01
IPS-SQL-DFS-02
IPS-ST-XP-05</td>
</tr>
</tbody>
</table>
 

**Per popolare i gruppi elencati nella tabella precedente**

1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.

2.  Espandere il dominio, quindi fare clic su **Utenti**.

3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **&lt;*Nome gruppo*&gt;**, quindi scegliere **Proprietà**.

4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.

5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.

6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare il nome di tutti i computer elencati nella colonna Membri della tabella precedente, separando i nomi con un punto e virgola. Scegliere **OK**.

7.  Scegliere **OK**.

##### Aggiunta di account utente ai gruppi di protezione gruppo di accesso alla rete

La Woodgrove Bank ha identificato gli account utente autorizzati ad avviare il traffico all'interno del gruppo di accesso alla rete e li ha aggiunti ai gruppi locali di dominio appropriati, utilizzati per implementare il gruppo di accesso alla rete.

Nella tabella riportata di seguito, viene indicata l'appartenenza del gruppo di accesso alla rete identificato dalla Woodgrove Bank.

**Tabella C.10: Appartenenza al gruppo di accesso alla rete della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome gruppo</th>
<th style="border:1px solid black;" >Membri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ANAG _EncryptedResourceAccess_users</td>
<td style="border:1px solid black;">User7</td>
</tr>
</tbody>
</table>
  
**Per popolare i gruppi elencati nella tabella precedente**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **&lt;*Nome gruppo*&gt;**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare il nome di tutti gli utenti elencati nella colonna Membri della tabella precedente. Qualora vi siano più utenti, separare i nomi con un punto e virgola. quindi scegliere **OK**.
  
6.  Scegliere **OK**.
  
##### Creazione di un oggetto Criteri di gruppo per concedere il diritto "Accedi al computer dalla rete"
  
La Woodgrove Bank ha creato un oggetto Criteri di gruppo per applicare il gruppo di accesso alla rete definito. In particolare, l'oggetto Criteri di gruppo concede ai gruppi di protezione appropriati del gruppo di accesso alla rete il diritto "Accedi al computer dalla rete" sui computer con funzione di risponditori.
  
Gli amministratori hanno creato la tabella seguente, contenente il nome dell'oggetto Criteri di gruppo e i nomi dei gruppi ad esso associati utilizzati per implementare il gruppo di accesso alla rete.
  
**Tabella C.11. Definizione del criterio gruppo di isolamento della Woodgrove Bank**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome GPO</th>
<th style="border:1px solid black;" >Nome gruppo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criterio gruppo di isolamento accesso a risorse crittografate</td>
<td style="border:1px solid black;">ANAG_EncryptedResourceAccess_computers
ANAG_EncryptedResourceAccess_users
Amministratori
Operatori backup</td>
</tr>
</tbody>
</table>
 

**Nota:** come minimo, devono essere aggiunti tutti i gruppi elencati. L'amministratore dovrà stabilire se occorre concedere tale diritto anche ad altri gruppi.

**Per concedere il diritto "Accedi al computer dalla rete"**

1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture: corp.woodgrovebank.com**, il dominio e infine **americas.corp.woodgrovebank.com**.

4.  Fare clic con il pulsante destro del mouse su **Oggetti criteri di gruppo**, quindi fare clic su **Nuovo**.

5.  Nella casella di testo **Nome**, digitare *&lt;Nome GPO&gt;*, quindi fare clic su **OK**.

6.  Fare clic con il pulsante destro del mouse su **&lt;*Nome GPO*&gt;**, quindi scegliere **Modifica**.

7.  Espandere **Configurazione computer**, espandere **Impostazioni di Windows**, **Impostazioni di protezione**, **Criteri locali** e infine fare clic su **Assegnazione diritti utente**.

8.  Nel riquadro a destra, fare clic con il pulsante destro del mouse su **Accedi al computer dalla rete**, quindi scegliere **Proprietà**.

9.  Selezionare la casella di controllo **Definisci le impostazioni relative ai criteri**.

10. Fare clic sul pulsante **Aggiungi utente o gruppo**.

11. Fare clic sul pulsante **Sfoglia**.

12. Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare il *&lt;nome gruppo&gt;* di tutti i gruppi elencati nella tabella precedente, separandoli con un punto e virgola. Scegliere **OK**.

13. Fare clic di nuovo su **OK**.

14. Chiudere la console di gestione Criteri di gruppo.

##### Collegamento degli oggetti Criteri di gruppo di accesso alla rete

Prima di distribuire i criteri di gruppo di accesso alla rete, occorre collegare gli oggetti Criteri di gruppo a un percorso nell'ambiente di dominio. La Woodgrove Bank ha scelto di distribuire l'oggetto Criteri di gruppo collegandolo all'unità organizzativa appropriata in Active Directory, come illustrato nella tabella seguente.

**Tabella C.12. Nome GPO gruppo di accesso alla rete e UO di destinazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome GPO gruppo di accesso alla rete</th>
<th style="border:1px solid black;" >UO di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criteri di gruppo accesso alla rete crittografata</td>
<td style="border:1px solid black;">Server di database</td>
</tr>
</tbody>
</table>
  
**Per collegare un criterio GPO alla UO di destinazione**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe.
  
2.  Avviare la console di gestione Criteri di gruppo.
  
3.  Espandere **Insieme di strutture: corp.woodgrovebank.com**, il dominio, **americas.corp.woodgrovebank.com**, infine individuare la *&lt;UO di destinazione&gt;*.
  
4.  Fare clic con il pulsante destro del mouse sulla **&lt;*UO di destinazione*&gt;**, quindi scegliere **Collega oggetto Criteri di gruppo esistente**.
  
5.  Nell'elenco **Oggetti Criteri di gruppo** fare clic su &lt;*Nome GPO gruppo di accesso alla rete*&gt;, quindi scegliere **OK**.
  
#### Verifica della distribuzione dei gruppi di accesso alla rete
  
Dopo aver creato e distribuito i gruppi di accesso alla rete e i criteri, gli amministratori hanno verificato il funzionamento dei computer all'interno dei gruppi di accesso alla rete.
  
##### Test di implementazione prerequisiti
  
Prima di verificare il funzionamento dei computer all'interno del gruppo di accesso alla rete, la Woodgrove Bank ha controllato che le assegnazioni dei diritti utente fossero state correttamente aggiornate. Una volta trascorso un periodo di tempo sufficiente a garantire la replica e l'aggiornamento dei criteri, la Woodgrove Bank ha effettuato la seguente procedura sui computer elencati nella tabella seguente.
  
**Tabella C.13. Appartenenza al gruppo di accesso alla rete**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome del computer</th>
<th style="border:1px solid black;" >Gruppo elencato nel diritto utente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">ANAG_EncryptedResourceAccess_computers
ANAG_EncryptedResourceAccess_users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">ANAG_EncryptedResourceAccess_computers
ANAG_EncryptedResourceAccess_users</td>
</tr>
</tbody>
</table>
 

**Per confermare la corretta appartenenza del gruppo al gruppo di accesso alla rete**

1.  Connettersi al &lt;*nome computer*&gt; come amministratore del dominio Americhe.

2.  Avviare lo strumento Criteri di protezione locali.

3.  Espandere **Criteri locali**, espandere **Assegnazione diritti utente**, quindi fare doppio clic su **Accedi al computer dalla rete** nel riquadro a destra.

4.  Verificare che il gruppo Utenti autenticati non sia presente.

5.  Verificare che il gruppo &lt;*gruppo elencato in diritti utente*&gt; sia presente.  

6.  Chiudere lo strumento Criteri di protezione locali.

7.  Ripetere i punti da 1 a 6 per ciascun &lt;*nome computer*&gt; elencato nella tabella precedente.

##### Test funzionali di implementazione

Dopo aver verificato che ai gruppi di protezione fossero stati concessi i diritti utente appropriati, la Woodgrove Bank ha sottoposto a test incrociati i computer appartenenti ai gruppi di accesso alla rete. Quindi, ha utilizzato queste informazioni per verificare che le restrizioni sui diritti di accesso fossero implementate e funzionanti. La Woodgrove Bank ha poi tentato di eseguire i comandi **net view** su diverse combinazioni di iniziatore e risponditore. Oltre a questo test, si è utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate. Nella tabella riportata di seguito, vengono elencati l'iniziatore e il risponditore utilizzati per ogni esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate.

**Tabella C.14. Risultati previsti per il test funzionale del gruppo di accesso alla rete**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Iniziatore</th>
<th style="border:1px solid black;" >Risponditore</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-06</td>
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-06</td>
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-06</td>
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
</tbody>
</table>
  
**Per completare il test funzionale**
  
1.  Connettersi a &lt;*iniziatore*&gt; come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP.
  
3.  Espandere **Monitor di protezione IP**, &lt;*iniziatore*&gt; e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
4.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Responder&gt;  
```
  
5.  Tramite lo snap-in MMC Monitor di protezione IP, verificare che per ciascuna connessione riuscita sia stata negoziata la SA appropriata
  
6.  Ripetere i punti da 1 a 5 per ciascun &lt;*iniziatore*&gt; univoco elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione del dominio di isolamento
  
Prima di distribuire i criteri del dominio di isolamento, è necessario che l'amministratore individui un gruppo di computer da utilizzare per il testing del progetto pilota. Il gruppo di computer ideale deve rappresentare uno "spaccato" dell'infrastruttura IT dell'organizzazione e comprendere computer client e server.
  
Gli account di computer così identificati vengono aggiunti al gruppo CG\_IsolationDomain\_computers. Una volta trascorso il tempo necessario per la replica, il criterio di isolamento del dominio viene applicato ai computer pilota e attivato.
  
#### Implementazione del dominio di isolamento
  
La Woodgrove Bank ha identificato i seguenti computer da utilizzare per il progetto pilota:
  
-   IPS-TZ-XP-01
  
-   IPS-TZ-W2K-02
  
-   IPS-TZ-XP-06
  
-   IPS-WEB-DFS-01
  
**Per aggiungere computer pilota al gruppo CG\_IsolationDomain\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio**,** quindi scegliere **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_IsolationDomain\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare il nome di ciascun computer dell'elenco precedente, separando i nomi con un punto e virgola, quindi scegliere **OK**.
  
7.  Scegliere nuovamente **OK**.
  
    **Nota:** dopo l'aggiunta dei computer al gruppo universale CG\_IsolationDomain\_computers, è necessario attendere che trascorra il tempo necessario alla replica delle modifiche apportate alle appartenenze ai gruppi in tutto l'insieme di strutture e all'applicazione del criterio ai computer host.
  
#### Verifica della distribuzione del dominio di isolamento
  
Dopo aver creato e distribuito, allo stato attivo, gli oggetti dei criteri in Active Directory, procedere alla verifica del corretto funzionamento del computer all'interno del gruppo di isolamento.
  
##### Test di implementazione prerequisiti
  
Prima di eseguire eventuali test funzionali sul computer presente nel dominio di isolamento, la Woodgrove Bank ha atteso la replica e l'aggiornamento del criterio, quindi ha verificato che venisse applicato il criterio IPsec corretto.
  
**Per controllare che a IPS-TZ-XP-06 sia stato applicato il criterio IPsec corretto**
  
1.  Connettersi a IPS-TZ-XP-06 come amministratore del dominio Americhe.
  
2.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">IPseccmd show gpo  
```
  
3.  Controllare l'output per confermare che il nome del criterio sia il seguente: "IPSEC – Criterio IPsec dominio di isolamento (1.0.041001.1600)".
  
##### Test funzionali di implementazione
  
Dopo aver verificato la corretta applicazione del criterio a IPS-TZ-XP-06, la Woodgrove Bank ha eseguito alcuni semplici test funzionali per verificarne il corretto funzionamento. La Woodgrove Bank ha poi tentato di eseguire i comandi **net view** da IPS-TZ-XP-06 a diversi computer presenti in altri gruppi di isolamento. Inoltre, si è utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate. Nella tabella riportata di seguito, vengono elencati i computer di destinazione utilizzati per ogni esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate.
  
**Nota:** quando si tenta di eseguire un comando **net view** su un computer non attendibile, è necessario specificare le credenziali di amministratore locale del computer di destinazione.
  
**Tabella C.15. Risultati previsti dei test funzionali sul dominio di isolamento**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-W2K-02</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-WEB-DFS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
</tbody>
</table>
  
**Per eseguire il test funzionale su tutti i computer di destinazione**
  
1.  Connettersi a IPS-TZ-XP-06 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-TX-XP-06** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione del gruppo di isolamento Nessun fallback
  
I computer appartenenti al gruppo di isolamento Nessun fallback non possono avviare traffico non autenticato su computer non attendibili.
  
#### Implementazione del gruppo di isolamento Nessun fallback
  
La Woodgrove Bank ha collocato i computer che non possono avviare comunicazioni non autenticate su computer non attendibili nel gruppo universale CG\_NoFallbackIG\_computers.
  
**Per popolare il gruppo CG\_NoFallbackIG\_computers**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe, quindi avviare Utenti e computer di Active Directory.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_NoFallbackIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare **IPS-LT-XP-01**, quindi fare clic su **OK**.
  
7.  Scegliere **OK** per due volte.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra l'aggiunta del computer al gruppo CG\_NoFallbackIG\_computers e l'applicazione del criterio gruppo di isolamento Nessun fallback. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
#### Verifica della distribuzione del gruppo di isolamento Nessun fallback
  
Dopo aver creato e distribuito, allo stato attivo, gli oggetti dei criteri in Active Directory, procedere alla verifica del corretto funzionamento del computer all'interno del gruppo di isolamento.
  
##### Test di implementazione prerequisiti
  
Prima di eseguire eventuali test funzionali sui computer del gruppo di isolamento Nessun fallback, la Woodgrove Bank ha atteso la replica e l'aggiornamento del criterio, quindi ha verificato che venisse applicato il criterio IPsec corretto.
  
**Per controllare che a IPS-LT-XP-01 sia stato applicato il criterio IPsec corretto**
  
1.  Connettersi a IPS-LT-XP-01 come amministratore del dominio Americhe.
  
2.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">IPseccmd show gpo  
```
  
3.  Controllare l'output per confermare che il nome del criterio sia il seguente: "Modalità non crittografata consentita in uscita".
  
##### Test funzionali di implementazione
  
Dopo aver verificato la corretta applicazione del criterio a IPS-LT-XP-01, la Woodgrove Bank ha eseguito alcuni semplici test funzionali per verificarne il corretto funzionamento. La Woodgrove Bank ha poi tentato di eseguire i comandi **net view** da IPS-LT-XP-01 a diversi computer presenti in altri gruppi di isolamento. Inoltre, si è utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate. Nella tabella riportata di seguito, vengono elencati i computer di destinazione utilizzati per ogni esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate.
  
**Nota:** quando si tenta di eseguire un comando **net view** su un computer non attendibile, è necessario specificare le credenziali di amministratore locale del computer di destinazione.
  
**Tabella C.16. Risultati previsti per il test funzionale del criterio Modalità non crittografata consentita in uscita**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
</tbody>
</table>
  
**Per eseguire il test funzionale su tutti i computer di destinazione**
  
1.  Connettersi a IPS-LT-XP-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-LT-XP-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione del gruppo di isolamento Crittografia
  
È necessario che il traffico dei computer appartenenti al gruppo di isolamento Crittografia sia crittografato. Inoltre, i server che ospitano i dati sono configurati in modo da limitare l'accesso attraverso la rete mediante l'implementazione di un gruppo di isolamento specifico per i server selezionati.
  
Utilizzando un ulteriore criterio di gruppo e un gruppo di protezione, è possibile controllare l'accesso al server tramite la modifica del diritto "Accedi al computer dalla rete". Prestare particolare attenzione quando si modificano i diritti di accesso al server per evitare che anche agli utenti legittimi venga rifiutato l'accesso.
  
**Nota:** il gruppo di isolamento utilizzato in questa sezione è stato implementato nella precedente sezione "Abilitazione della configurazione del gruppo di isolamento" della presente guida.
  
#### Implementazione del gruppo di isolamento Crittografia
  
Il team di implementazione della Woodgrove Bank ha individuato i computer che richiedevano la crittografia IPsec e li ha inseriti nel gruppo universale Richiedi crittografia.
  
**Per popolare il gruppo Richiedi crittografia**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe, quindi avviare Utenti e computer di Active Directory.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_EncryptionIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare IPS-SQL-DFS-01; IPS-SQL-DFS-02, quindi fare clic su **OK**.
  
7.  Scegliere **OK**.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra l'aggiunta del computer al gruppo CG\_EncryptionIG\_computers e l'applicazione del criterio del gruppo di isolamento Crittografia. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
#### Verifica della distribuzione del gruppo di isolamento Crittografia
  
Dopo aver creato e distribuito, allo stato attivo, gli oggetti dei criteri in Active Directory, procedere alla verifica del corretto funzionamento del computer all'interno del gruppo di isolamento.
  
##### Test di implementazione prerequisiti
  
Prima di eseguire eventuali test funzionali sui computer del gruppo di isolamento Crittografia, la Woodgrove Bank ha atteso la replica e l'aggiornamento del criterio, quindi ha verificato che ai computer IPS-SQL-DFS-01 e IPS-SQL-DFS-02 venisse applicato il criterio IPsec corretto.
  
**Per controllare che sia stato applicato il criterio IPsec corretto**
  
1.  Connettersi a IPS-SQL-DFS-01 come amministratore del dominio Americhe.
  
2.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">netsh IPsec static show gpoassignedpolicy  
```
  
3.  Controllare l'output per confermare che il nome del criterio sia il seguente: "IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)".
  
4.  Avviare lo strumento Criteri di protezione locali.
  
5.  Espandere **Criteri locali**, espandere **Assegnazione diritti utente**, quindi fare doppio clic su **Accedi al computer dalla rete** nel riquadro a destra.
  
6.  Verificare che il gruppo Utenti autenticati non sia presente.
  
7.  Verificare che i gruppi ANAG\_EncryptedResourceAccess\_computers e ANAG\_EncryptedResourceAccess\_users siano presenti.
  
8.  Chiudere lo strumento Criteri di protezione locali.
  
9.  Ripetere i punti da 1 a 8 su IPS-SQL-DFS-02.
  
##### Test funzionali di implementazione
  
Dopo aver verificato la corretta applicazione del criterio ai computer IPS-SQL-DFS-01 e IPS-SQL-DFS-02, la Woodgrove Bank ha eseguito alcuni semplici test funzionali per verificarne il corretto funzionamento. La Woodgrove Bank ha poi tentato di eseguire i comandi **net view** su IPS-SQL-DFS-01 e IPS-SQL-DFS-02. Inoltre, si è utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate. Nelle tabelle riportate di seguito, vengono elencati i computer di destinazione utilizzati per l'esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate.
  
**Nota:** quando si tenta di eseguire un comando **net view** su un computer non attendibile, è necessario specificare le credenziali di amministratore locale del computer.
  
**Tabella C.17. Risultati previsti dei test funzionali su IPS-SQL-DFS-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-02</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
</tbody>
</table>
  
**Per collaudare il funzionamento dell'implementazione sui computer di destinazione**
  
1.  Connettersi a IPS-SQL-DFS-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-SQL-DFS-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione del gruppo di isolamento Limite
  
La Woodgrove Bank ha collocato i computer che devono avviare o ricevere comunicazioni non autenticate da o verso computer non attendibili nel gruppo universale CG\_BoundaryIG\_computers.
  
#### Implementazione del gruppo di isolamento Limite
  
Il team di implementazione della Woodgrove Bank ha identificato i computer appartenenti al gruppo di isolamento Limite e li ha collocati nel gruppo universale CG\_BoundaryIG\_computers.
  
**Per popolare il gruppo CG\_BoundaryIG\_computers**
  
1.  Connettersi a IPS-CH-DC-01 come amministratore del dominio Americhe, quindi avviare Utenti e computer di Active Directory.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_BoundaryIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.
  
6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare IPS-PRINTS-01, quindi fare clic su **OK**.
  
7.  Scegliere **OK**.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra l'aggiunta del computer al gruppo CG\_BoundaryIG\_computers e l'applicazione del criterio del gruppo di isolamento Limite. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
#### Verifica della distribuzione del gruppo di isolamento Limite
  
Dopo aver creato e distribuito, allo stato attivo, gli oggetti dei criteri in Active Directory, procedere alla verifica del corretto funzionamento del computer all'interno del gruppo di isolamento.
  
##### Test di implementazione prerequisiti
  
Prima di eseguire eventuali test funzionali sui computer del gruppo di isolamento Limite, la Woodgrove Bank ha atteso la replica e l'aggiornamento del criterio, quindi ha verificato che al computer venisse applicato il criterio IPsec corretto.
  
**Per controllare che a IPS-PRINTS-01 sia stato applicato il criterio IPsec corretto**
  
1.  Connettersi a IPS-PRINTS-01 come amministratore del dominio Americhe.
  
2.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">netsh IPsec static show gpoassignedpolicy  
```
  
3.  Controllare l'output per confermare che il nome del criterio sia il seguente: "IPSEC - Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)".
  
##### Test funzionali di implementazione
  
Dopo aver verificato la corretta applicazione del criterio a IPS-PRINTS-06, la Woodgrove Bank ha eseguito alcuni semplici test funzionali per verificarne il corretto funzionamento. La Woodgrove Bank ha poi tentato di eseguire i comandi **net view** sui computer elencati nella tabella seguente. Inoltre, si è utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate. Nella tabella riportata di seguito, vengono elencati i computer di destinazione utilizzati per ogni esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate per ogni computer appartenente al gruppo di accesso a risorse crittografate.
  
**Nota:** quando si tenta di eseguire un comando **net view** su un computer non attendibile, è necessario specificare le credenziali di amministratore locale del computer.
  
**Tabella C.18. Risultati previsti dei test funzionali su IPS-PRINTS-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
</tbody>
</table>
  
**Per collaudare il funzionamento dell'implementazione sui computer di destinazione**
  
1.  Connettersi a IPS-PRINTS-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-PRINTS-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione del dominio di isolamento come gruppo di isolamento predefinito
  
Prima di eseguire i test funzionali, gli amministratori della Woodgrove Bank hanno configurato la protezione del dominio di isolamento in modo che venisse applicata a tutti i computer del dominio. Questo metodo garantisce che tutti i nuovi computer aggiunti al dominio vengano automaticamente aggiunti al dominio di isolamento, a meno che non abbiano esigenze tali per cui debbano essere aggiunti a un gruppo di isolamento diverso.
  
Inoltre, il gruppo Computer del dominio è stato rimosso dal gruppo CG\_BoundaryIG\_computers.
  
**Per rimuovere Computer del dominio dal gruppo CG\_BoundaryIG\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_BoundaryIG\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri**, quindi il gruppo **Computer del domino**, infine scegliere **Rimuovi**.
  
5.  Fare clic su **Sì** per rimuovere il gruppo.
  
6.  Scegliere **OK**.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra la rimozione del gruppo dal gruppo CG\_BoundaryIG\_computers e la rimozione del criterio gruppo di isolamento Limite. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
**Per aggiungere Computer del dominio al gruppo CG\_BoundaryIG\_computers**
  
1.  Avviare Utenti e computer di Active Directory su IPS-CH-DC-01 collegandosi come amministratore del dominio Americhe.
  
2.  Espandere il dominio, quindi fare clic su **Utenti**.
  
3.  Nel riquadro a destra, fare clic con il pulsante destro del mouse sul gruppo di protezione **CG\_IsolationDomain\_computers**, quindi scegliere **Proprietà**.
  
4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.
  
5.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare Computer del dominio, quindi fare clic su **OK**.
  
6.  Scegliere nuovamente **OK**.
  
    **Nota:** a causa dei ritardi di replica e della frequenza di polling dei criteri IPsec, si verificherà un ritardo tra l'aggiunta del gruppo Computer del dominio al gruppo CG\_IsolationDomain\_computers e l'applicazione del criterio gruppo di isolamento del dominio. Riavviare il computer a questo punto se si desidera applicare immediatamente il criterio IPsec. In caso contrario, il criterio verrà applicato allo scadere del ticket di sessione e aggiornato con le nuove informazioni di appartenenza al gruppo locale.
  
#### Aggiornamento dell'ordine di collegamento dei criteri IPsec
  
Per garantire la corretta applicazione dei criteri agli host, è necessario aggiornare l'ordine di collegamento dei criteri IPsec. L'operazione è necessaria in quanto il criterio predefinito attuale è il criterio gruppo di isolamento standard e non più il criterio gruppo di isolamento Limite, impostato come predefinito nella fase iniziale della distribuzione.
  
**Per collegare i criteri IPsec agli oggetti GPO esistenti**
  
1.  Avviare la GPMC collegandosi come amministratore di dominio.
  
2.  Espandere il dominio.
  
3.  Fare clic sul nome del dominio.
  
4.  Nell'elenco **Oggetti Criteri di gruppo collegati**, ordinare i criteri come illustrato nella tabella seguente con l'ausilio dei tasti freccia.
  
    **Tabella C.19. Ordine di collegamento oggetti Criteri di gruppo a livello di dominio**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Ordine di collegamento</th>
    <th style="border:1px solid black;" >Nome oggetto Criteri di gruppo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">1</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Crittografia</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">2</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Nessun fallback</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">3</td>
    <td style="border:1px solid black;">IPSEC - Criterio gruppo di isolamento Limite</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">4</td>
    <td style="border:1px solid black;">IPSEC - Criterio dominio di isolamento</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">5</td>
    <td style="border:1px solid black;">Default Domain Policy</td>
    </tr>
    </tbody>
    </table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Test funzionali finali - Tutti i gruppi di isolamento abilitati
  
Dopo aver abilitato tutti i gruppi di isolamento, la Woodgrove Bank ha eseguito alcuni semplici test funzionali per verificare il corretto funzionamento dei criteri. Benché durante l'implementazione di ciascun criterio fossero stati eseguiti alcuni test funzionali, gli amministratori della Woodgrove Bank non erano riusciti ad eseguire un test funzionale completo in quanto i gruppi di isolamento sono stati abilitati uno alla volta. Gli amministratori hanno poi tentato di eseguire i comandi **net view** da uno o più computer appartenenti a ciascun gruppo di isolamento su computer appartenenti ad altri gruppi di isolamento, per verificare che la connettività fosse stata stabilita correttamente. In alcuni gruppi di isolamento, sono stati selezionati più computer, i cui modelli di traffico variano a seconda che si tratti di risponditori o iniziatori. Inoltre, gli amministratori hanno utilizzato lo snap-in MMC Monitor di protezione IP per verificare che fossero state create le SA appropriate.
  
Nelle tabelle riportate di seguito, vengono elencati i computer di destinazione utilizzati per ogni esecuzione di **net view**, un'indicazione sull'esito (positivo o negativo) previsto e il tipo di SA negoziate per tutti i computer selezionati per l'esecuzione di test.
  
**Nota:** quando si tenta di eseguire un comando **net view** su computer non attendibili, è necessario specificare le credenziali di amministratore locale del computer.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-SQL-DFS-01 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento o di accesso alla rete.
  
**Tabella C.20. Risultati previsti dei test funzionali su IPS-SQL-DFS-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile con crittografia</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile con crittografia</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">Il computer è in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile con crittografia</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">L'iniziatore non supporta la modalità non crittografata.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-SQL-DFS-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-SQL-DFS-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-TX-XP-06 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento o di accesso alla rete.
  
**Tabella C.21. Risultati previsti dei test funzionali su IPS-TZ-XP-06**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Il risponditore fa parte del gruppo <em>Accesso a risorse crittografate.</em></td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-TZ-XP-06 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-TZ-XP-06** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-ST-XP-06 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento.
  
**Tabella C.22. Risultati previsti dei test funzionali su IPS-ST-XP-05**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">Il risponditore fa parte del gruppo <em>Accesso a risorse crittografate.</em></td>
<td style="border:1px solid black;">SA non trasferibile con crittografia</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-SZ-XP-05 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-ST-XP-05** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-TX-XP-01 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento o di accesso alla rete.
  
**Tabella C.23. Risultati previsti dei test funzionali su IPS-TZ-XP-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Il risponditore fa parte del gruppo Accesso a risorse crittografate.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">L'iniziatore supporta la modalità non crittografata.</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-TZ-XP-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-TZ-XP-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-LT\_XP-01 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento o di accesso alla rete.
  
**Tabella C.24. Risultati previsti dei test funzionali su IPS-LT-XP-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Il risponditore fa parte del gruppo Accesso a risorse crittografate.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">L'iniziatore non supporta la modalità non crittografata.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-LT-XP-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-LT-XP-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-PRINTS-01 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento.
  
**Tabella C.25. Risultati previsti dei test funzionali su IPS-PRINTS-01**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Il risponditore nega esplicitamente l'accesso agli host appartenenti al gruppo di isolamento Limite. Il risponditore fa parte del gruppo <em>Accesso a risorse crittografate</em>.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">I computer sono in grado di completare la negoziazione di IPsec.</td>
<td style="border:1px solid black;">SA non trasferibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-UT-XP-03</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">L'iniziatore supporta la modalità non crittografata.</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-PRINTS-01 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-PRINTS-01** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su IPS-UT-XP-03, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
Mediante la seguente procedura, è possibile verificare la connettività tra IPS-UT-XP-03 (con funzione di iniziatore) e diversi computer appartenenti ad altri gruppi di isolamento o di accesso alla rete.
  
**Tabella C.26. Risultati previsti dei test funzionali su IPS-UT-XP-03**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Computer di destinazione</th>
<th style="border:1px solid black;" >Risultato</th>
<th style="border:1px solid black;" >Motivo</th>
<th style="border:1px solid black;" >SA negoziata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IPS-SQL-DFS-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">L'iniziatore non supporta la modalità non crittografata e il passthrough in ingresso. Il risponditore fa parte del gruppo Accesso a risorse crittografate.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-ST-XP-05</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">L'iniziatore non supporta la modalità non crittografata e il passthrough in ingresso.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IPS-TZ-XP-01</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">L'iniziatore non supporta la modalità non crittografata e il passthrough in ingresso.</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IPS-PRINTS-01</td>
<td style="border:1px solid black;">Operazioni riuscite</td>
<td style="border:1px solid black;">L'iniziatore supporta la modalità non crittografata e il passthrough in ingresso.</td>
<td style="border:1px solid black;">SA trasferibile</td>
</tr>
</tbody>
</table>
  
**Per verificare la connettività dai computer di destinazione**
  
1.  Connettersi a IPS-UT-XP-03 come amministratore del dominio Americhe.
  
2.  Avviare lo snap-in MMC Monitor di protezione IP, espandere **Monitor di protezione IP**, **IPS-UT-XP-03** e **Modalità rapida**, quindi scegliere **Associazioni protezione**.
  
3.  Aprire un prompt dei comandi e specificare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false"> net view \\\\&lt;Target Computer&gt;  
```
  
    **Nota:** su tutti i computer basati sul dominio, specificare le credenziali di amministratore locale con il comando **net view**.
  
4.  Tramite lo snap-in MMC Monitor di protezione IP, controllare il campo **Associazioni protezione** di tutte le connessioni riuscite per verificare che sia stata negoziata la SA appropriata.
  
5.  Ripetere i punti 3 e 4 per ciascun &lt;*computer di destinazione*&gt; elencato nella tabella precedente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Una volta completate le attività descritte nella presente appendice, si sarà provveduto a:
  
-   Creare gli elenchi filtri, le operazioni filtro, le regole e i criteri IPsec in Active Directory.
  
-   Configurare gli oggetti GPO presenti in Active Directory per una corretta applicazione dei criteri IPsec.
  
-   Effettuare una distribuzione in più fasi del gruppo di isolamento Limite e del dominio di isolamento nell'intera azienda.
  
-   Configurare più gruppi di isolamento per il controllo dell'accesso al risponditore.
  
-   Abilitare e collaudare il dominio di isolamento.
  
-   Abilitare e collaudare il gruppo di isolamento Nessun fallback.
  
-   Abilitare e collaudare il gruppo di isolamento Crittografia.
  
-   Abilitare e collaudare il gruppo di isolamento Limite.
  
**Scarica la soluzione completa**
  
[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)
  
[](#mainsection)[Inizio pagina](#mainsection)
