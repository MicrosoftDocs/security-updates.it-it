---
TOCTitle: 'Appendice A: Guida aggiuntiva per Windows XP Service Pack 2'
Title: 'Appendice A: Guida aggiuntiva per Windows XP Service Pack 2'
ms:assetid: '6446ddfe-0b69-4b57-86b6-903df99c7f74'
ms:contentKeyID: 20200899
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536300(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Appendice A: Guida aggiuntiva per Windows XP Service Pack 2

Questa appendice descrive le modifiche alla guida per la protezione basate su Microsoft Windows XP Service Pack 2 (SP2) per Windows XP.

Leggere le sezioni precedenti della *Guida per la protezione di Windows XP* prima di considerare questa appendice. Essa integra tali sezioni e descrive unicamente le modifiche alla configurazione specifiche di SP2. Non deve essere considerata un documento indipendente.

##### In questa pagina

[](#efaa)[Panoramica di Windows XP SP2](#efaa)
[](#eeaa)[Modifiche alle impostazioni di protezione](#eeaa)
[](#edaa)[Modifiche a Modelli amministrativi](#edaa)
[](#ecaa)[Impostazioni di configurazione del computer](#ecaa)
[](#ebaa)[Impostazioni configurazione utente](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica di Windows XP SP2

Windows XP SP2 contiene gli aggiornamenti più recenti a Windows XP. Questi aggiornamenti consentono di migliorare la protezione, l'affidabilità e la compatibilità del sistema operativo introducendo un insieme di tecnologie di protezione che potenzieranno la capacità dei computer dotati di Windows XP di contrastare gli attacchi dannosi di virus e worm. Queste tecnologie comprendono:

-   Protezione di rete

-   Protezione della memoria

-   Migliore protezione della posta elettronica

-   Navigazione più sicura

-   Migliore manutenzione del computer

SP2 contiene diversi miglioramenti relativi alla facilità di gestione dei servizi di protezione. Questi miglioramenti consentono agli amministratori di installare impostazioni di protezione più specifiche sia per gli utenti sia per i computer.

Una delle principali modifiche apportate a SP2 è la maggiore sicurezza delle impostazioni di protezione predefinite. La maggior parte delle modifiche alla protezione sono predefinite e non richiedono di cambiare la configurazione. Sebbene molti di questi miglioramenti creino dei problemi di compatibilità, il miglioramento generale nella protezione del sistema operativo compensa tali difficoltà.

Per ulteriori informazioni sulle importanti modifiche di SP2, vedere "Changes to Functionality in Microsoft Windows XP Service Pack 2" all'indirizzo [http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/sp2chngs.mspx.](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/sp2chngs.mspx)

[](#mainsection)[Inizio pagina](#mainsection)

### Modifiche alle impostazioni di protezione

Le importanti modifiche dei criteri e delle impostazioni apportate a Windows XP SP2 sono limitate principalmente alla sezione Modelli amministrativi di Criteri di Gruppo. Di conseguenza, in questa appendice non esistono modifiche consigliate per le impostazioni di protezione.

[](#mainsection)[Inizio pagina](#mainsection)

### Modifiche a Modelli amministrativi

Sono state apportate importanti modifiche a Modelli amministrativi di Windows XP SP 2. Sono presenti centinaia di nuove impostazioni che consentono all'utente di avere un controllo più preciso sul proprio utilizzo del computer e dell'ambiente di protezione. Questa appendice fornisce soprattutto dettagli sulle nuove impostazioni di Modelli amministrativi, che consentiranno di migliorare la protezione dell'ambiente.

**Nota:** le impostazioni descritte in questa appendice non hanno effetto su sistemi operativi diversi da Windows XP SP2. Le impostazioni non riguardano Windows XP Service Pack 1 e le versioni precedenti del sistema operativo.

#### Nuovi Modelli amministrativi

Impostazioni di protezione aggiuntive sono disponibili in file Unicode denominati Modelli amministrativi. Questi file contengono le impostazioni del Registro di sistema relative a Windows XP e ai suoi componenti. Windows XP SP2 comprende nuovi Modelli amministrativi. Questi nuovi modelli richiedono l'utilizzo di un computer dotato di Windows XP SP2 quando si gestiscono i GPO.

Le versioni precedenti dell'Editor oggetti Criteri di gruppo (Gpedit.exe) non supportano i nuovi Modelli amministrativi. Le modifiche ai GPO nuovi o esistenti devono essere apportate utilizzando un computer dotato di Windows XP SP2. Per informazioni sull'utilizzo di altri sistemi operativi per gestire i GPO, vedere l'articolo della Microsoft Knowledge Base 842933 all'indirizzo [http://support.microsoft.com/kb/842933/it.](http://support.microsoft.com/kb/842933/it)

Le impostazioni nei nuovi Modelli amministrativi riguardano unicamente i computer dotati di Windows XP SP2; Windows XP SP1 e le versioni precedenti del sistema operativo ignoreranno le nuove impostazioni. Questo approccio consente di installare i GPO utilizzando la stessa struttura OU descritta nel Capitolo 2 della *Guida per la protezione di Windows XP* per migliorare la protezione di tutti i computer dotati di Windows XP dell'ambiente.

[](#mainsection)[Inizio pagina](#mainsection)

### Impostazioni di configurazione del computer

Le sezioni seguenti descrivono le impostazioni stabilite in Configurazione computer nell'Editor oggetti Criteri di gruppo. Configurare queste impostazioni nel seguente percorso:

Configurazione computer\\Modelli amministrativi

Applicare queste impostazioni attraverso un GPO collegato a un OU che contiene gli account computer dell'ambiente. Collegare le impostazioni per i computer portatili nel GPO all'OU del computer portatile e le impostazioni del desktop nel GPO all'OU del desktop, come descritto nel Capitolo 2 della *Guida per la protezione di Windows XP.*

#### Internet Explorer

Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:

Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer

##### Disattiva rilevamento errori critici

**Tabella A.1: impostazioni Disattiva rilevamento errori critici**

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
<th><p>Desktop client organizzazione</p></th>
<th><p>Portatile client organizzazione</p></th>
<th><p>Desktop livello di protezione Alto</p></th>
<th><p>Portatile livello di protezione Alto</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Disattiva rilevamento errori critici** consente di configurare la funzionalità di rilevamento errori critici nella gestione dei componenti aggiuntivi di Internet Explorer. Se si abilita questa impostazione di criterio, un errore critico in Internet Explorer sarà simile a quello su un computer dotato di Windows XP Professional Service Pack 1 e versioni precedenti: sarà richiamata la Segnalazione errori di Windows. Se si disattiva questo criterio, sarà operativa la funzionalità di rilevamento errori critici nella gestione dei componenti aggiuntivi.
  
Poiché i dati relativi al report di arresti anomali di Internet Explorer potrebbero contenere informazioni riservate della memoria del computer, questa appendice consiglia di impostare questa opzione su **Attivato**, a meno che non si verifichino errori critici ripetuti di frequente e ci sia la necessità di segnalarli per una successiva risoluzione dei problemi. In questi casi è possibile configurare temporaneamente l'impostazione su **Disattivato.**
  
##### Non consentire agli utenti di abilitare o disabilitare i componenti aggiuntivi
  
**Tabella A.2: impostazioni Non consentire agli utenti di abilitare o disabilitare i componenti aggiuntivi**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Non consentire agli utenti di abilitare o disabilitare i componenti aggiuntivi** consente di stabilire se gli utenti hanno la possibilità di abilitare o disabilitare i componenti aggiuntivi attraverso Gestione componenti aggiuntivi. Se si configura questo criterio su **Attivato**, gli utenti non possono abilitare o disabilitare i componenti aggiuntivi attraverso Gestione componenti aggiuntivi. La sola eccezione è se un componente aggiuntivo è stato espressamente inserito nell'**Elenco componenti aggiuntivi** dei criteri in modo da consentire agli utenti di continuare a gestire il componente aggiuntivo. In tal caso, l'utente può gestire il componente aggiuntivo attraverso Gestione componenti aggiuntivi. Se si configura questo criterio su **Disattivato**, gli utenti potranno abilitare o disabilitare i componenti aggiuntivi.
  
**Nota:** per ulteriori informazioni sulla gestione dei componenti aggiuntivi di Internet Explorer in Windows XP SP2, vedere l'articolo della Microsoft Knowledge Base 883256 "Gestione dei componenti aggiuntivi di Internet Explorer in Windows XP Service Pack 2" all'indirizzo [http://support.microsoft.com/kb/883256/it.](http://support.microsoft.com/kb/883256/it)
  
Gli utenti scelgono spesso di installare componenti aggiuntivi che non sono consentiti dai criteri di protezione di un'organizzazione. Tali componenti possono rappresentare un rischio significativo per la protezione e la privacy della rete. Per tale ragione, si consiglia di configurare il criterio come **Attivato**.
  
**Nota**: riesaminare le impostazioni dei GPO in Internet Explorer\\Funzioni di protezione\\Gestione componenti aggiuntivi per accertarsi che i componenti aggiuntivi autorizzati e corretti possano ancora essere utilizzati nell'ambiente.
  
##### Pannello di controllo Internet\\Protezione
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet\\Protezione
  
SP2 introduce nuove impostazioni di criterio che consentono di proteggere la configurazione delle aree di Internet Explorer nell'ambiente. SP2 configura i computer utilizzando valori predefiniti per queste impostazioni che migliorano la protezione. Tuttavia, è possibile riesaminare queste impostazioni e configurare i criteri per renderli obbligatori o meno rigorosi all'interno dell'ambiente, al fine di garantirne l'utilizzabilità o la compatibilità con le applicazioni.
  
Per esempio, SP2 configura Internet Explorer in modo che blocchi i pop-up di tutte le aree di Internet per impostazione predefinita. È possibile configurare questa impostazione su tutti i computer dell'ambiente per eliminare fastidiose finestre pop-up e ridurre la possibilità che vengano installati software e spyware dannosi che sono spesso generati su siti Web in Internet. Tuttavia, l'ambiente potrebbe contenere applicazioni che richiedono l'uso di pop-up per funzionare. In questo caso, è possibile configurare questo criterio in modo da consentire i pop-up per i siti Web all'interno di Intranet.
  
##### Pannello di controllo Internet\\Avanzate
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Pannello di controllo Internet\\Avanzate
  
###### Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida.
  
**Tabella A.3: impostazioni Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
Ai controlli e ai download di file di Microsoft ActiveX sono spesso allegate firme digitali che garantiscono l'integrità del file e l'identità dell'autore della firma (il creatore) del software. Le firme consentono di verificare di aver scaricato software non modificato e di identificare l'autore della firma per determinare se ci si fida abbastanza per eseguire il software.
  
L'impostazione di criterio **Consenti l'esecuzione o l'installazione del software anche se la firma è non è valida** consente di stabilire se gli utenti possono installare o utilizzare il software scaricato anche se la firma non è valida. Una firma non valida potrebbe indicare che qualcuno ha manomesso il file. Se si abilita questa impostazione del criterio, sarà richiesta l'autorizzazione per installare o eseguire file con firma non valida. Se si disattiva questa impostazione del criterio, gli utenti non potranno eseguire o installare file con una firma non valida.
  
Poiché il software privo di firma può creare vulnerabilità nella protezione, questa appendice consiglia di bloccare tale software configurando l'impostazione su **Disattivato.**
  
**Nota:** alcuni software e controlli legittimi possono avere una firma non valida ma essere comunque sicuri. Verificare con cura e in sede separata tali software prima di consentirne l'utilizzo sulla rete dell'organizzazione.
  
##### Funzioni di protezione\\Limitazione protocollo di protezione MK
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limitazione protocollo di protezione MK
  
###### Processi di Internet Explorer (Protocollo MK)
  
**Tabella A.4: impostazioni Limitazione protocollo di protezione MK**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Limitazione protocollo di protezione MK** riduce l'area esposta ad attacchi bloccando il protocollo MK, raramente utilizzato. Alcune applicazioni Web meno aggiornate utilizzano il protocollo MK per recuperare le informazioni dai file compressi. Impostando questo criterio su **Attivato**, il protocollo MK viene bloccato per Esplora risorse e Internet Explorer, in modo da interdire le risorse che utilizzano tale protocollo. La disattivazione di questa impostazione consente alle applicazioni di utilizzare l'API del protocollo MK.
  
Poiché il protocollo MK non è diffuso, dovrebbe essere bloccato quando non necessario. Questa appendice consiglia di configurare l'impostazione su **Attivato** per bloccare il protocollo MK, a meno che non sia specificamente necessario per l'ambiente.
  
**Nota:** poiché le risorse che utilizzano il protocollo MK verranno interdette quando si distribuisce questa impostazione, assicurarsi che nessuna delle applicazioni utilizzi tale protocollo.
  
##### Funzioni di protezione\\Gestione MIME coerente
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Gestione MIME coerente
  
###### Processi di Internet Explorer (Gestione MIME coerente)
  
**Tabella A.5: Impostazioni Gestione MIME coerente**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Internet Explorer utilizza i dati MIME (Multipurpose Internet Mail Extensions) per determinare le procedure di gestione dei file ricevuti attraverso un server Web. L'impostazione di criterio **Gestione MIME coerente\\Processi di Internet Explorer** determina se Internet Explorer richiede che tutte le informazioni relative al tipo di file fornite dai server Web siano coerenti. Per esempio, se il tipo MIME di un file è text/plain ma i dati MIME indicano che il file è in realtà un eseguibile, Internet Explorer ne modifica l'estensione per riflettere questa condizione. Questa funzione consente di evitare che il codice eseguibile possa essere mascherato come altri tipi di dati non pericolosi.
  
Se si abilita questa impostazione del criterio, Internet Explorer esamina tutti i file ricevuti e applica ad essi i dati MIME coerenti. Se si disattiva o non si configura questa impostazione di criterio, Internet Explorer non richiede che i dati MIME siano coerenti per tutti i file ricevuti e utilizzerà i dati MIME forniti dal file.
  
Lo spoofing del tipo di file MIME è un pericolo potenziale per l'organizzazione. Assicurarsi che questi file siano coerenti e correttamente denominati per evitare che download di file dannosi infettino la rete. Per tale ragione, si consiglia di configurare questo criterio su **Attivato** in tutti gli ambienti specificati in questa guida.
  
**Nota:** questa impostazione opera unitamente a, ma non sostituisce, le impostazioni della **Funzionalità di protezione analisi MIME**.
  
##### Funzioni di protezione\\Funzionalità di protezione analisi MIME
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Funzionalità di protezione analisi MIME
  
###### Processi di Internet Explorer (Analisi MIME)
  
**Tabella A.6: impostazioni Analisi MIME**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'analisi MIME è una processo che esamina il contenuto di un file MIME per determinare il suo contesto, cioè se si tratta di un file di dati, di un file eseguibile o di qualche altro tipo di file. Questa impostazione di criterio determina se l'analisi MIME di Internet Explorer eviterà la conversione di un tipo di file a un file di tipo più pericoloso. Quando impostato su **Attivato**, l'analisi MIME non convertirà mai un file a un tipo di file più pericoloso. Disattivando l'analisi MIME, i processi di Internet Explorer vengono configurati in modo da eseguire un analisi che converte un tipo di file a un file di tipo più pericoloso. Per esempio, convertendo un file di testo a un file eseguibile è pericoloso, perché può essere eseguito qualsiasi codice all'interno del presunto file di testo.
  
Lo spoofing del tipo di file MIME è un pericolo potenziale per l'organizzazione. Assicurarsi che questi file siano gestiti in modo coerente per evitare che download di file dannosi infettino la rete. Per tale ragione, si consiglia di configurare questo criterio su **Attivato** in tutti gli ambienti specificati in questa guida.
  
**Nota:** questa impostazione opera unitamente a, ma non sostituisce, le impostazioni di **Gestione MIME coerente**.
  
##### Funzioni di protezione\\Limitazioni protezione Windows tramite script
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limitazioni protezione Windows tramite script
  
###### Processi di Internet Explorer (Limitazioni protezione Windows tramite script)
  
**Tabella A.7: impostazioni Limitazioni protezione Windows tramite script**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Internet Explorer consente agli script di aprire, ridimensionare e riposizionare in modo programmato vari tipi di finestre. I siti Web malintenzionati spesso ridimensioneranno finestre per nascondere altre finestre o costringere l'utente a interagire con una finestra che contiene codice dannoso.
  
La funzione di protezione **Limitazioni protezione Windows tramite script** limita le finestre pop-up e impedisce agli script di visualizzare finestre nelle quali le barre di titolo e di stato non sono visibili all'utente o nascondono altre barre di titolo e di stato della finestra. Se si abilita l'impostazione di criterio **Limitazioni protezione Windows tramite script\\Processi di Internet Explorer**, le restrizioni relative alle finestre pop-up e le altre restrizioni vengono applicate ai processi di Esplora risorse e di Internet Explorer. Se si disattiva o non si configura questa impostazione di criterio, gli script continuano a creare finestre pop-up e finestre che ne nascondono altre.
  
Questa appendice consiglia di configurare questa impostazione su **Attivato** per evitare che i siti Web dannosi controllino le finestre di Internet Explorer o inducano erroneamente gli utenti a fare clic sulla finestra sbagliata.
  
##### Funzioni di protezione\\Protezione da promozione di area
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di Protezione\\Protezione da promozione di area
  
###### Processi di Internet Explorer (Protezione da promozione di area)
  
**Tabella A.8: impostazioni Protezione da promozione di area**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Internet Explorer pone delle restrizioni a ogni pagina Web aperta che dipendono dalla posizione della pagina stessa (come l'area Internet, l'area Intranet o l'area Computer locale). Le pagine Web su un computer locale hanno le restrizioni di protezione più basse e risiedono nell'area Computer locale, il che rende l'area di protezione del computer locale uno dei bersagli principali per gli attacchi informatici.
  
Se si abilita questa impostazione di criterio, tutte le aree possono essere protette dalla promozione di area da parte dei processi di Internet Explorer. Questo approccio evita che il contenuto in esecuzione in un'area ottenga i privilegi di promozione di un'altra area. Se si disattiva questa impostazione del criterio, nessuna area riceverà tale protezione per i processi di Internet Explorer.
  
A causa della gravità e della relativa frequenza degli attacchi di promozione di area, questa appendice consiglia di configurare l'impostazione su **Attivato** in tutti gli ambienti.
  
##### Funzioni di protezione\\Limita installazione ActiveX
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limita installazione ActiveX
  
###### Processi di Internet Explorer (Limita installazione ActiveX)
  
**Tabella A.9: impostazioni Limita installazione ActiveX**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Limita installazione ActiveX\\Processi di Internet Explorer** consente di bloccare i prompt di installazione del controllo ActiveX per i processi di Internet Explorer.
  
Se si abilita questa impostazione di criterio, i prompt di installazione del controllo ActiveX per i processi di Internet Explorer saranno bloccati. Se si disabilita questa impostazione di criterio, i prompt di installazione del controllo ActiveX non verranno bloccati.
  
Gli utenti installano spesso software come i controlli ActiveX, che non sono permessi dai criteri di protezione aziendale. Tale software può comportare significativi rischi di protezione e di riservatezza per la rete. Per tale ragione, si consiglia di configurare il criterio come **Attivato.**
  
**Nota:** questa impostazione impedisce inoltre agli utenti di installare controlli ActiveX autorizzati e legittimi che interferiscono con importanti componenti di sistema come Windows Update. Se si abilita questa impostazione, assicurarsi di installare Software Update Services (SUS) o un metodo alternativo di distribuire gli aggiornamenti di protezione.
  
Per ulteriori informazioni su SUS, vedere la pagina Software Update Services (che contiene anche informazioni su Windows Update Services, il successore di SUS) all'indirizzo [http://www.microsoft.com/windowsserversystem/sus/default.mspx.](http://www.microsoft.com/windowsserversystem/sus/default.mspx)
  
##### Funzioni di protezione\\Limita download file
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Limita download file
  
###### Internet Explorer Elabora (Limita download file)
  
**Tabella A.10: impostazioni Limita download file**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
In certe circostanze, i siti Web possono iniziare il download di file senza l'interazione da parte degli utenti. Questa tecnica può consentire ai siti Web di salvare file non autorizzati sul disco fisso se l'utente fa clic sul pulsante sbagliato e accetta il download.
  
Se si configura l'impostazione di criterio **Limita download file\\Processi di Internet Explorer** su **Attivato**, vengono bloccati per Internet Explorer i prompt di download dei file non avviati dagli utenti. Se si configura questa impostazione di criterio su **Disattivato**, i prompt di download dei file non avviati dagli utenti saranno consentiti per i processi di Internet Explorer.
  
**Nota**: questa impostazione è configurata su **Attivato** in tutti gli ambienti specificati in questa guida per evitare che i pirati informatici inseriscano codici arbitrari sui computer degli utenti.
  
##### Funzioni di protezione\\Gestione componenti aggiuntivi
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Internet Explorer\\Funzioni di protezione\\Gestione componenti aggiuntivi
  
###### Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi
  
**Tabella A.11: impostazioni Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione e il criterio **Elenco componenti aggiuntivi** consentono di controllare i componenti aggiuntivi di Internet Explorer. Per impostazione predefinita, le impostazioni del criterio **Elenco componenti aggiuntivi** definiscono un elenco di componenti aggiuntivi che possono essere consentiti o bloccati attraverso i Criteri di gruppo. L'impostazione **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** assicura che tutti gli elementi aggiuntivi siano bloccati a meno che non siano specificatamente elencati nell'impostazione di criterio dell'**Elenco componenti aggiuntivi**.
  
Se si abilita questa impostazione di criterio, Internet Explorer accetta unicamente i componenti aggiuntivi specificamente elencati (e consentiti) dall'impostazione di criterio **Elenco componenti aggiuntivi**. Se si disattiva questa impostazione, gli utenti potranno utilizzare Gestione componenti aggiuntivi per consentire o bloccare qualsiasi aggiunta.
  
Si consiglia l'uso di entrambe le impostazioni **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** ed **Elenco componenti aggiuntivi** per controllare i componenti aggiuntivi che possono essere utilizzati nell'ambiente. Questo approccio contribuirà ad assicurare che siano usati soltanto i componenti aggiuntivi autorizzati.
  
###### Elenco componenti aggiuntivi
  
**Tabella A.12: impostazioni Elenco componenti aggiuntivi**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione e il criterio **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** consentono di controllare i componenti aggiuntivi di Internet Explorer. Per impostazione predefinita, le impostazioni del criterio **Elenco componenti aggiuntivi** definiscono un elenco di componenti aggiuntivi che possono essere consentiti o bloccati attraverso i Criteri di gruppo. L'impostazione **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** assicura che tutti gli elementi aggiuntivi siano bloccati a meno che non siano specificatamente elencati nell'impostazione di criterio dell'**Elenco componenti aggiuntivi**.
  
Se si abilita questa impostazione di criterio, è necessario creare un elenco di componenti aggiuntivi che Internet Explorer deve accettare o rifiutare. Per ogni voce aggiunta all'elenco, è necessario fornire le informazioni seguenti:
  
-   **Il nome del valore.** Il CLSID (identificatore di classe) per il componente aggiuntivo che si desidera aggiungere all'elenco. Il CLSID deve essere tra parentesi; per esempio, {000000000-0000-0000-0000-0000000000000}. È possibile ottenere il CLSID di un componente aggiuntivo leggendo il tag OBJECT all'interno della pagina Web in cui il componente aggiuntivo è presente.
  
-   **Valore**. Un numero che indica se Internet Explorer deve rifiutare o consentire il caricamento del componente aggiuntivo. I valori seguenti sono validi:
  
    **Tabella A.13: impostazione dei valori nell'elenco dei componenti aggiuntivi**

<p> </p>
    <table style="border:1px solid black;">  
    <colgroup>  
    <col width="50%" />  
    <col width="50%" />  
    </colgroup>  
    <thead>  
    <tr class="header">  
    <th><p>Valore</p></th>  
    <th><p>Descrizione</p></th>  
    </tr>  
    </thead>  
    <tbody>  
    <tr class="odd">
    <td style="border:1px solid black;"><p>0</p></td>
    <td style="border:1px solid black;"><p>Rifiuta il componente aggiuntivo</p></td>
    </tr>  
    <tr class="even">
    <td style="border:1px solid black;"><p>1</p></td>
    <td style="border:1px solid black;"><p>Accetta il componente aggiuntivo</p></td>
    </tr>  
    <tr class="odd">
    <td style="border:1px solid black;"><p>2</p></td>
    <td style="border:1px solid black;"><p>Accetta il componente aggiuntivo e consente all'utente di gestirlo attraverso Gestione componenti aggiuntivi</p></td>
    </tr>  
    </tbody>  
    </table>
  
Se si disattiva questa impostazione di criterio, l'elenco viene eliminato.
  
Si consiglia l'uso di entrambe le impostazioni **Rifiuta tutti i componenti aggiuntivi a meno che non siano consentiti nell'elenco dei componenti aggiuntivi** ed **Elenco componenti aggiuntivi** per controllare i componenti aggiuntivi che possono essere utilizzati nell'ambiente. Questo approccio contribuirà ad assicurare che siano usati soltanto i componenti aggiuntivi autorizzati.
  
#### Servizi terminal\\Client
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Componenti di Windows\\Servizi terminal\\ Client
  
##### Non consentire salvataggio password
  
**Tabella A.14: impostazioni Non consentire salvataggio password**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Non consentire salvataggio password** impedisce che le password vengano salvate su un computer da client di Servizi terminal. Abilitando questa impostazione, la casella di controllo del salvataggio della password in Client di Servizi terminal viene disabilitata, in modo che gli utenti non possano più salvare le password. Poiché il salvataggio delle password può portare a ulteriori violazioni, questa impostazione è configurata su **Attivato** per gli ambienti definiti in questa guida.
  
**Nota:** se questa impostazione era precedentemente configurata su **Disattivato** o **Non configurato**, qualsiasi password salvata sarà eliminata la prima volta che un client di Servizi terminal si disconnette da un server.
  
#### Windows Update
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Componenti di Windows\\Windows Update
  
##### Non visualizzare l'opzione "Installa aggiornamenti e spegni" nella finestra di dialogo Fine della sessione di lavoro di Windows.
  
**Tabella A.15: impostazioni Non visualizzare le opzioni "Installa aggiornamenti e spegni" nella finestra di dialogo Fine della sessione di lavoro di Windows**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Non visualizzare l'opzione "Installa aggiornamenti e spegni" nella finestra di dialogo Fine della sessione di lavoro di Windows** consente di decidere se l'opzione **Installa aggiornamenti e spegni** deve essere visualizzata nella finestra di dialogo **Fine della sessione di lavoro di Windows.**
  
Disattivando questa impostazione di criterio l'opzione **Installa aggiornamenti e spegni** viene visualizzata nella finestra di dialogo **Fine della sessione di lavoro di Windows** se gli aggiornamenti sono disponibili quando l'utente seleziona l'opzione **Spegni computer** nel menu **Start** o fa clic sul pulsante **Chiudi sessione** nella finestra visualizzata premendo CTRL+ALT+DELETE. Questa impostazione è configurata su **Disattivato** per tutti gli ambienti definiti in questa guida, poiché installare aggiornamenti è importante per la protezione complessiva di tutti i computer. Questa impostazione opera unitamente al criterio **Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro**, elencato di seguito.
  
##### Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro.
  
**Tabella A.16: impostazioni Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Non impostare "Installa aggiornamenti e spegni" come opzione predefinita nella finestra di dialogo Fine della sessione di lavoro** consente di stabilire se l'opzione **Installa aggiornamenti e spegni** debba essere quella predefinita nella finestra di dialogo **Fine della sessione di lavoro di Windows.** Disattivando questa impostazione di criterio, l'opzione **Installa aggiornamenti e spegni** sarà quella predefinita nella finestra di dialogo **Fine della sessione di lavoro di Windows** se gli aggiornamenti sono disponibili per l'installazione quando l'utente seleziona l'opzione **Spegni computer** nel menu **Start**.
  
Questa impostazione è configurata su **Disattivato** per tutti gli ambienti definiti in questa guida, poiché installare aggiornamenti è importante per la protezione complessiva di tutti i computer.
  
**Nota:** questa impostazione non ha alcun effetto se l'opzione **Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Windows Update\\Non visualizzare l'opzione "Installa aggiornamenti e spegni"** nell'impostazione di criterio della **finestra di dialogo Fine della sessione di lavoro di Windows** è attivata.
  
#### System
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione computer\\Modelli amministrativi\\Sistema
  
##### Disattiva richiesta ricerca driver periferiche in Windows Update
  
**Tabella A.17: impostazioni Disattiva richiesta ricerca driver periferiche in Windows Update**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Disattiva richiesta ricerca driver periferiche in Windows Update** verifica se all'amministratore viene richiesto di ricercare driver di periferiche in Windows Update utilizzando Internet. Se questa impostazione è attivata, agli amministratori non verrà richiesto di eseguire la ricerca in Windows Update. Se questa impostazione e **Disattiva ricerca driver periferiche in Windows Update** sono disattivati o non sono configurati, verrà chiesto il consenso dell'amministratore prima di ricercare driver di periferiche in Windows Update.
  
Poiché è rischioso scaricare driver da Internet, si consiglia di configurare l'impostazione su **Attivato** per gli ambienti con alti requisiti di protezione e su **Disattivato** per gli ambienti aziendali. Questo perché i tipi di attacchi che possono utilizzare il download di un driver saranno generalmente contenuti da una corretta gestione delle risorse aziendali.
  
**Nota**: questa impostazione è efficace solo se **Disattiva ricerca driver periferiche in Windows Update** in **Modelli amministrativi/Sistema/Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet** è disabilitato o non è configurato.
  
##### Sistema\\Segnalazione errori
  
Il capitolo 4 della *Guida per la protezione di Windows XP* stabilisce diverse impostazioni per la configurazione della Segnalazione errori. Queste impostazioni sono uguali a quelle dei computer dotati di Windows XP SP2, ma il nome di una di esse è stato modificato. L'impostazione **Segnala errori** descritta nella Tabella 4.42 è ora denominata **Configura segnalazione errori.** Le impostazioni richieste sono uguali a quelle descritte nel Capitolo 4.
  
##### Sistema\\RPC (Remote Procedure Call)
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Sistema\\RPC
  
###### Restrizioni per client RPC non autenticati
  
**Tabella A.18: impostazioni Restrizioni per client RPC non autenticati**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Abilitando l'impostazione **Restrizioni per client RPC non autenticati**, è possibile configurare il runtime RPC in un server RPC per limitare i client RPC non autenticati che si connettono ai server RPC in esecuzione su un computer. Un cliente è considerato non autenticato se utilizza un named pipe per comunicare col server o se utilizza la Protezione RPC. Le interfacce RPC che hanno chiesto specificatamente di essere accessibili da client non autenticati possono essere esenti da questa restrizione, in base al valore scelto per questo criterio. Abilitando questa impostazione sono disponibili i seguenti valori:
  
-   **Nessuno**. Questo valore consente a tutti i client RPC di connettersi ai server RPC in esecuzione sul computer a cui il criterio è applicato.
  
-   **Autenticato.** Questo valore consente soltanto a client RPC autenticati di connettersi ai server RPC in esecuzione sul computer su cui il criterio è applicato. Alle interfacce che hanno chiesto di essere esenti da questa restrizione sarà concessa un'esenzione.
  
-   **Autenticato senza eccezioni.** Questo valore consente soltanto a client RPC autenticati di connettersi ai server RPC in esecuzione sul computer su cui il criterio è applicato. Non sono consentite eccezioni.
  
Poiché la comunicazione RPC non autenticata può creare vulnerabilità nella protezione, questa appendice consiglia di configurare questa impostazione su **Attivato** e il valore **Restrizioni runtime RPC client non autenticati da applicare** su **Autenticato** per tutti gli ambienti definiti in questa guida.
  
**Nota**: le applicazioni RPC che non autenticano richieste di connessione in ingresso indesiderate potrebbero non funzionare correttamente quando tale configurazione è attiva. Assicurarsi di verificare le applicazioni prima di distribuire tale impostazione. Sebbene il valore **Autenticato** per questa impostazione non sia completamente sicuro, può essere utile per assicurare la compatibilità delle applicazioni nell'ambiente.
  
###### Autenticazione client mapping degli endpoint RPC
  
**Tabella A.19: impostazioni Autenticazione client mapping degli endpoint RPC**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Abilitando l'impostazione **Autenticazione client mapping degli endpoint RPC**, i client che comunicano con questo computer sono obbligati a fornire l'autenticazione prima che venga stabilita la comunicazione RPC.
  
##### Sistema\\Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet
  
Il gruppo Impostazioni di comunicazione Internet contiene parecchie impostazioni di configurazione. Questa appendice consiglia di limitare molte di queste impostazioni, principalmente per migliorare la riservatezza dei dati sui sistemi informatici. Se queste impostazioni non sono limitate, le informazioni potrebbero essere intercettate e utilizzate dagli aggressori. Sebbene sia raro che si verifichi questo tipo di attacco, la corretta configurazione di queste impostazioni protegge l'ambiente da attacchi futuri.
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Sistema\\Gestione comunicazioni Internet\\Impostazioni di comunicazione Internet
  
###### Disattiva l'operazione per file e cartelle Pubblica sul Web
  
**Tabella A.20: impostazioni Disattiva l'operazione per file e cartelle Pubblica sul Web**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione specifica se visualizzare le operazioni **Pubblica file sul Web**, **Pubblica cartella sul Web** e **Pubblica elementi selezionati sul Web** in Operazioni file e cartella nelle cartelle di Windows. La Pubblicazione guidata sul Web scarica sul computer un elenco di provider e consente agli utenti di pubblicare contenuto sul Web. Se si configura questa impostazione su **Attivato**, queste opzioni vengono rimosse dalle operazioni file e cartelle nelle cartelle di Windows.
  
###### Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet
  
**Tabella A.21: Impostazioni Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Configurando l'impostazione **Disattiva download Internet per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet**, è possibile controllare se Windows scaricherà un elenco di provider per le procedure di pubblicazione guidata sul Web e ordinazione guidata via Internet. Abilitando questa impostazione, si evita che Windows scarichi i provider; saranno visualizzati solo i provider di servizi memorizzati nel Registro di sistema locale.
  
###### Disattiva Analisi utilizzo software Windows Messenger
  
**Tabella A.22: impostazioni Disattiva Analisi utilizzo software Windows Messenger**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Disattiva Analisi utilizzo software Windows Messenger** specifica se Windows Messenger raccoglie informazioni anonime sulla modalità di utilizzo del software e dei servizi di Windows Messenger. Configurare questa impostazione su **Attivato** per evitare che Windows Messenger raccolga informazioni di utilizzo e che vengano visualizzate le impostazioni dell'utente per l'attivazione della raccolta di tali informazioni.
  
###### Disattiva aggiornamenti file contenuto Ricerca guidata
  
**Tabella A.23: impostazioni Disattiva aggiornamenti file contenuto Ricerca guidata**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Disattiva aggiornamenti file contenuto Ricerca guidata** specifica se la Ricerca guidata deve scaricare automaticamente gli aggiornamenti di contenuto nel corso delle ricerche locali e in Internet. Configurando questa impostazione su **Attivato**, la Ricerca guidata non scaricherà gli aggiornamenti di contenuto durante le ricerche.
  
**Nota**: le ricerche in Internet inviano comunque il testo della ricerca e altre informazioni sulla ricerca a Microsoft e al provider di ricerca prescelto. Se viene scelta la modalità di ricerca classica, la funzionalità di Ricerca guidata viene disattivata completamente. È possibile scegliere la ricerca classica facendo clic su **Start**, **Cerca**, **Cambia preferenze**, quindi su **Change Internet Search Behavior**.
  
###### Disattiva stampa su HTTP
  
**Tabella A.24: impostazioni Disattiva stampa su HTTP**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione consente di disattivare la stampa su HTTP da questo client. La stampa su HTTP consente a un client di stampare tramite stampanti su Intranet e su Internet. Abilitando questa impostazione si evita che il client stampi tramite stampanti in Internet su HTTP.
  
Le informazioni trasmesse quando si stampa su HTTP non sono protette e possono essere intercettate da utenti malintenzionati. Per questa ragione, tale impostazione è raramente utilizzata dalle aziende o dagli ambienti ad alta protezione. Disattivando questa funzionalità si evita che venga utilizzata accidentalmente, cosa che potrebbe compromettere la protezione con un processo di stampa non sicuro.
  
**Nota**: questa impostazione riguarda unicamente il lato client della stampa su Internet. Non evita che un computer agisca da server di stampa su Internet e metta a disposizione stampanti condivise via HTTP.
  
###### Disattiva download driver di stampa su HTTP
  
**Tabella A.25: impostazioni Disattiva download driver di stampa su HTTP**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Disattiva download driver di stampa su HTTP** controlla se il computer può scaricare pacchetti di driver di stampa su HTTP. Per impostare la stampa su HTTP, i driver di stampa non disponibili nell'installazione standard del sistema operativo devono essere scaricati su HTTP. Si consiglia di configurare questa impostazione su **Attivato**, per evitare che i driver di stampa vengano scaricati su HTTP.
  
**Nota**: questa impostazione non evita che il client stampi tramite stampanti in Intranet o Internet su HTTP. Impedisce unicamente lo scaricamento di driver che non sono già installati in locale.
  
###### Disattiva ricerca driver periferiche in Windows Update
  
**Tabella A.26: impostazioni Disattiva ricerca driver periferiche in Windows Update**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Il criterio **Disattiva ricerca driver periferiche in Windows Update** specifica se Windows ricerca i driver di periferiche in Windows Update quando non sono presenti driver locali per una periferica.
  
Poiché è rischioso scaricare driver da Internet, si consiglia di configurare l'impostazione su **Attivato** per gli ambienti con alti requisiti di protezione e su **Disattivato** per gli ambienti aziendali. Questo perché i tipi di attacchi che possono utilizzare il download di un driver saranno generalmente ridotti da una corretta gestione delle risorse aziendali e della configurazione.
  
**Nota**: vedere anche **Disattiva richiesta ricerca driver periferiche in Windows Update** in **Modelli amministrativi/Sistema**, che consente di gestire le richieste all'amministratore prima di ricercare i driver di periferiche in Windows Update se un driver non è presente in locale.
  
#### Windows Firewall\\Profilo di dominio
  
Le impostazioni in questa sezione configurano il Profilo di dominio di Windows Firewall. Windows Firewall può determinare dinamicamente se il computer è in un ambiente di dominio e applicare una configurazione di firewall specifica basata su tale rilevamento. Questa funzione consente di distribuire impostazioni di firewall separate in base alla posizione del computer.
  
Si utilizza il Profilo di dominio quando viene rilevato un ambiente di dominio. È possibile configurare questo profilo in modo che sia meno restrittivo del Profilo standard, perché un ambiente di dominio fornisce spesso livelli aggiuntivi di protezione. Le informazioni sulla configurazione del Profilo standard vengono fornite più avanti in questa appendice.
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Rete\\Connessioni di rete\\Windows Firewall\\Profilo di dominio
  
##### Windows Firewall: proteggi tutte le connessioni di rete (Profilo di dominio)
  
**Tabella A.27: impostazioni Proteggi tutte le connessioni di rete (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: proteggi tutte le connessioni di rete** attiva Windows Firewall, che sostituisce Firewall connessione Internet su tutti i computer con Windows XP SP2. Questa appendice consiglia di configurare questa impostazione su **Attivato** per proteggere tutte le connessioni di rete dei computer in tutti gli ambienti.
  
Se questa impostazione è configurata su **Disattivato**, Windows Firewall è disabilitato e tutte le altre impostazioni di Windows Firewall sono ignorate.
  
**Nota**: se si abilita questa impostazione di criterio, Windows Firewall viene eseguito e ignora il criterio **Configurazione computer\\Modelli amministrativi\\Rete\\Connessioni di Rete\\Proibisci l'uso del Firewall Connessione Internet nella rete del dominio DNS**.
  
##### Windows Firewall: non consentire eccezioni (Profilo di dominio)
  
**Tabella A.28: impostazioni Non consentire eccezioni (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: non consentire eccezioni** specifica che Windows Firewall deve bloccare tutti i messaggi indesiderati in ingresso. Questa impostazione ignora tutte le altre impostazioni di criterio di Windows Firewall che consentono tali messaggi. Se si abilita questa impostazione nel componente Windows Firewall del Pannello di controllo, la casella **Non consentire eccezioni** sarà selezionata e gli amministratori non potranno deselezionarla.
  
Molti ambienti contengono applicazioni e servizi che devono poter ricevere comunicazioni indesiderate in ingresso, come parte del loro normale funzionamento. In questi casi potrebbe essere opportuno configurare questo criterio su **Disattivato** per consentire a tali applicazioni e servizi di funzionare correttamente. Tuttavia, prima di apportare qualunque modifica a questo criterio, è necessario verificare l'ambiente per determinare esattamente cosa consentire e cosa rifiutare.
  
**Nota**: questa impostazione fornisce una solida difesa contro i pirati informatici e dovrebbe essere configurata su **Attivato** nelle situazioni in cui è necessaria una protezione completa dagli attacchi esterni, come la diffusione di un nuovo worm di rete. L'impostazione di questo criterio su **Disattivato** consente a Windows Firewall di applicare altre impostazioni di criterio che consentano l'ingresso di messaggi indesiderati.
  
##### Windows Firewall: Definisci le eccezioni programmi (Profilo di dominio)
  
**Tabella A.29: impostazioni Definisci le eccezioni programmi (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
Alcune applicazioni possono avere bisogno di aprire ed utilizzare le porte di rete che non sono normalmente abilitate da Windows Firewall. L'impostazione **Windows Firewall: definisci eccezioni programmi** consente di visualizzare e modificare l'elenco eccezioni di programmi definito nei Criteri di gruppo.
  
L'impostazione di questo criterio su **Attivato** consente di visualizzare e modificare l'elenco eccezioni di programmi. Se si aggiunge un programma a questo elenco e si imposta lo stato su **Attivato**, tale programma può ricevere messaggi in ingresso indesiderati su qualunque porta che chieda di aprire a Windows Firewall, anche se quella porta è bloccata da un'altra impostazione di criterio.
  
Se si configura questo criterio su **Disattivato**, l'elenco eccezioni di programmi definito di Criteri di gruppo viene cancellato.
  
**Nota**: se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza cercare errori. Poiché l'immissione non viene controllata, è possibile aggiungere programmi non ancora installati. È inoltre possibile creare accidentalmente più eccezioni per lo stesso programma con valori di stato o ambito in conflitto.
  
##### Windows Firewall: Consenti eccezioni programmi locali (Profilo di dominio)
  
**Tabella A.30: impostazioni Consenti eccezioni programmi locali (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezioni programmi locali** consente che gli amministratori utilizzino il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di programmi locali. Disattivando questa impostazione di criterio si impedisce agli amministratori di definire un elenco di eccezioni programmi locali e si assicura che le eccezioni derivino unicamente dai Criteri di gruppo. Se si imposta questo criterio su **Attivato**, gli amministratori locali potranno utilizzare il Pannello di controllo per definire eccezioni di programmi a livello locale.
  
Per i computer client aziendali possono sussistere le condizioni che giustificano la definizione di eccezioni programmi locali da parte del client. Queste condizioni possono includere applicazioni che non sono state analizzate durante la creazione dei criteri firewall dell'organizzazione o nuove applicazioni che richiedono una configurazione non standard della porta. In questi casi è possibile abilitare questa impostazione, accettando la maggiore ampiezza della superficie di attacco dei computer interessati.
  
##### Windows Firewall: Consenti eccezione per amministrazione remota (Profilo di dominio)
  
**Tabella A.31: impostazioni Consenti eccezione per amministrazione remota (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
Molte organizzazioni approfittano dell'amministrazione remota del computer durante le attività quotidiane. Tuttavia, alcuni attacchi hanno sfruttato le porte utilizzate di norma dai programmi di amministrazione remoti; Windows Firewall può bloccare queste porte. Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per amministrazione**.
  
Configurare questa impostazione su **Attivato** per consentire che il computer riceva messaggi in ingresso indesiderati per l'amministrazione remota sulle porte TCP 135 e 445. Questa impostazione di criterio consente inoltre a SVCHOST.EXE e a LSASS.EXE di ricevere messaggi in ingresso indesiderati e consente a servizi ospitati di aprire le porte aggiuntive assegnate dinamicamente, tipicamente nell'intervallo 1024-1034 ma potenzialmente dovunque da 1024 a 65535. Per abilitare questa impostazione è necessario specificare gli indirizzi di IP o le sottoreti da cui sono consentiti tali messaggi in ingresso.
  
Se si configura questo criterio su **Disattivato**, Windows Firewall non applicherà alcuna delle eccezioni descritte.
  
Questa appendice consiglia di abilitare questa impostazione per i computer aziendali (se necessario) e di disattivarla sempre per i computer ad alta protezione. I computer nell'ambiente dovrebbero accettare le richieste di amministrazione remota da parte del minor numero di computer possibili. Per elevare al massimo la protezione fornita da Windows Firewall, assicurarsi di specificare soltanto gli indirizzi IP necessari e le sottoreti di computer utilizzati per l'amministrazione remota.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezione per condivisione file e stampanti (Profilo di dominio)
  
**Tabella A.32: impostazioni Consenti eccezione per condivisione file e stampanti (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione consente la condivisione di file e stampanti configurando Windows Firewall in modo da aprire le porte UDP 137 e 138 e le porte TCP 139 e 445. Se si abilita questa impostazione di criterio, Windows Firewall apre queste porte in modo che il computer possa ricevere i processi di stampa e le richieste per l'accesso ai file condivisi. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi in ingresso sono consentiti.
  
Se si disattiva questa impostazione di criterio, Windows Firewall blocca queste porte e impedisce al computer di condividere file e stampanti.
  
Poiché i computer dell'ambiente in cui è in esecuzione Windows XP non condividono normalmente file e stampanti, si consiglia di configurare queste impostazioni su **Disattivato** in tutti gli ambienti.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezioni ICMP (Profilo di dominio)
  
**Tabella A.33: impostazioni Consenti eccezioni ICMP (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
L'opzione **Windows Firewall: consenti eccezioni ICMP** definisce la serie di tipi di messaggi ICMP (Internet Control Message Protocol) consentiti da Windows Firewall. Le utilità possono utilizzare i messaggi ICMP per determinare lo stato di altri computer. Per esempio, Ping utilizza il messaggio di richiesta echo.
  
Se questo criterio è impostato su **Attivato**, specificare quali tipi di messaggi ICMP Windows Firewall consente di inviare o ricevere. Se questo criterio è impostato su **Disattivato**, Windows Firewall blocca tutti i tipi di messaggi ICMP in ingresso indesiderati e i tipi di messaggi ICMP in uscita contenuti nell'elenco. Di conseguenza, le utilità che utilizzano i messaggi ICMP bloccati non saranno in grado di inviare i messaggi a o dal computer.
  
Molti strumenti di aggressione approfittano dei computer che accettano i tipi di messaggi ICMP ed utilizzano questi messaggi per preparare vari attacchi. Tuttavia, alcune applicazioni richiedono certi messaggi ICMP per funzionare correttamente. Per tale ragione, quando è possibile, si consiglia di configurare l'impostazione su **Disattivato**. Se l'ambiente richiede che alcuni messaggi ICMP attraversino Windows Firewall, configurare l'impostazione con i tipi di messaggio appropriati.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezione per Desktop remoto (Profilo di dominio)
  
**Tabella A.34: impostazioni Consenti eccezione per Desktop remoto (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
Molte organizzazioni utilizzano connessioni Desktop remoto per le procedure di risoluzione dei problemi o per le normali attività. Tuttavia, alcuni attacchi sfruttano le porte tipicamente utilizzate dal desktop remoto. Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per Desktop remoto**.
  
Abilitando questa impostazione Windows Firewall apre la porta TCP 3389 per le connessioni in ingresso. Specificare inoltre gli indirizzi di IP o le sottoreti da cui è possibile ricevere questi messaggi in ingresso.
  
Se si disattiva questa impostazione di criterio, Windows Firewall blocca questa porta ed impedisce al computer di ricevere richieste di Desktop remoto. Se un amministratore tenta di aprire questa porta aggiungendola a un elenco di eccezioni porte locali, Windows Firewall non apre la porta.
  
Alcuni attacchi possono utilizzare una porta aperta 3389. Per mantenere le capacità di gestione migliorate fornite da Desktop remoto, configurare questa impostazione su **Attivato** e specificare gli indirizzi di IP e le sottoreti dei computer utilizzati per l'amministrazione remota. I computer nell'ambiente dovrebbero accettare richieste di Desktop remoto da meno computer possibile.
  
##### Windows Firewall: Consenti eccezione per framework UPnP (Profilo di dominio)
  
**Tabella A.35: impostazioni Consenti eccezione per framework UPnP (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezione per framework UPnP** consente a un computer di ricevere messaggi Plug and Play indesiderati inviati da periferiche di rete, come i router con firewall incorporati. Per ricevere questi messaggi, Windows Firewall apre la porta TCP 2869 e porta UDP 1900.
  
Se si abilita questa impostazione di criterio, Windows Firewall apre queste porte in modo che il computer possa ricevere i messaggi Plug and Play. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi in ingresso sono consentiti. Se si disattiva questa impostazione di criterio, Windows Firewall blocca queste porte e impedisce al computer di ricevere messaggi Plug and Play.
  
Il blocco del traffico di rete UPnP riduce efficacemente l'esposizione agli attacchi dei computer nell'ambiente. Questa appendice consiglia di configurare questa impostazione su **Disattivato** a meno che sulla rete non vengano utilizzati dispositivi UPnP.
  
##### Windows Firewall: Proibisci notifiche (Profilo di dominio)
  
**Tabella A.36: impostazioni Proibisci notifiche (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
Windows Firewall può mostrare notifiche agli utenti quando un programma richiede che Windows Firewall aggiunga il programma all'elenco di eccezioni di programmi. Questa situazione si verifica quando i programmi tentano di aprire una porta e non sono autorizzati a farlo, in base alle regole di Windows Firewall attuali. L'impostazione **Windows Firewall: Proibisci notifiche** consente di scegliere se tali impostazioni devono essere mostrate agli utenti.
  
Se questo criterio è impostato su **Attivato**, Windows Firewall impedisce la visualizzazione di queste notifiche. Se questo criterio è impostato su **Disattivato**, Windows Firewall consente la visualizzazione di queste notifiche.
  
Spesso gli utenti non potranno aggiungere applicazioni e porte in risposta a questi messaggi in ambienti aziendali o ad alta protezione. In tali casi, questo messaggio informerà l'utente relativamente a un aspetto su cui non ha controllo. In quei casi impostare l'opzione su **Attivato.** In altri ambienti dove l'utente è configurato per consentire le eccezioni, impostare questa opzione su **Disattivato.**
  
##### Windows Firewall: Impedisci risposte unicast a richieste multicast o broadcast (Profilo di dominio)
  
**Tabella A.37: impostazioni Impedisci risposte unicast a richieste multicast o broadcast (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: impedisci risposte unicast a richieste multicast o broadcast** impedisce a un computer di ricevere risposte unicast ai messaggi multicast o broadcast in uscita. Quando questa impostazione di criterio è abilitata ed il computer invia messaggi multicast o broadcast ad altri computer, Windows Firewall blocca le risposte unicast inviate da tali computer. Quando l'impostazione è disattivata e il computer invia un messaggio multicast o broadcast agli altri computer, Windows Firewall attende fino a tre secondi le risposte unicast dagli altri computer, quindi blocca tutte le successive risposte.
  
Generalmente, non è corretto ricevere risposte unicast a messaggi multicast o broadcast. Tali risposte possono indicare un attacco DoS (Denial of Service) o il tentativo di un aggressore di sondare un computer noto. Configurare questo criterio su **Attivato** per evitare questo tipo di attacco.
  
**Nota**: questa impostazione di criterio non ha effetto se il messaggio unicast è una risposta a un messaggio broadcast DHCP (Dynamic Host Configuration Protocol) inviato dal computer. Windows Firewall permette sempre tali risposte unicast DHCP. Tuttavia, questa impostazione di criterio può interferire con i messaggi NetBIOS che rilevano conflitti di nome.
  
##### Windows Firewall: Definisci eccezioni porte (Profilo di dominio)
  
**Tabella A.38: impostazioni Definisci eccezioni porte (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
L'elenco eccezioni porte di Windows Firewall deve essere definito dai Criteri di gruppo, che consente di gestire e distribuire centralmente le eccezioni di porta ed assicura che gli amministratori locali non creino impostazioni meno sicure. L'impostazione **Windows Firewall: definisci eccezioni porte** consente di gestire centralmente queste impostazioni.
  
Se si abilita questa impostazione di criterio, è possibile visualizzare e modificare l'elenco eccezioni porta definito dai Criteri di gruppo. Per visualizzare e modificare l'elenco eccezioni porte, configurare il criterio su **Attivato** e fare clic su pulsante **Mostra**. Se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza controllare la presenza di errori, il che significa che è possibile creare accidentalmente più voci per la stessa porta con valori di stato o ambito in conflitto.
  
Se si disattiva questa impostazione di criterio, l'elenco eccezioni porte definito dai Criteri di gruppo viene cancellato, ma le altre impostazioni di criterio possono continuare ad aprire o bloccare le porte. Inoltre, se esiste un elenco di eccezioni porte locali, viene ignorato, a meno che non si abiliti l'impostazione **Windows Firewall: consenti eccezioni porte locali**.
  
Gli ambienti con applicazioni non standard che richiedono porte specifiche per essere aperti dovrebbero considerare la distribuzione di eccezioni di programmi. Abilitare questa impostazione e specificare un elenco di eccezioni di porte soltanto quando non possono essere definite eccezioni di programmi. Le eccezioni di programmi consentono a Windows Firewall di accettare il traffico di rete indesiderato soltanto mentre il programma specificato è in esecuzione, e le eccezioni di porta tengono sempre aperte le porte specificate.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezioni porte locali (Profilo di dominio)
  
**Tabella A.39: impostazioni Consenti eccezioni porte locali (Profilo di dominio)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezioni porte locali** consente agli amministratori di utilizzare il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di porte locali. Windows Firewall può utilizzare due elenchi di eccezioni di porte; l'altro è definito dal criterio **Windows Firewall: definisci eccezioni porte**.
  
Se si attiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo consente agli amministratori di definire un elenco di eccezioni di porte locali. Se si disattiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo non consente agli amministratori di definire tale elenco.
  
Di norma, gli amministratori locali non sono autorizzati a ignorare il criterio dell'organizzazione e a stabilire i propri elenchi di eccezioni porte in ambienti aziendali o ad alta protezione. Per tale ragione, si consiglia di configurare questa opzione su **Disattivato.**
  
#### Windows Firewall\\Profilo standard
  
Le impostazioni in questa sezione configurano il profilo standard di Windows Firewall. Windows Firewall può determinare dinamicamente se il computer è in un ambiente di dominio e applicare una configurazione di firewall specifica basata su tale rilevamento. Questa funzione consente di distribuire impostazioni di firewall separate in base alla posizione del computer.
  
Quando viene rilevato un ambiente non di dominio si utilizza il Profilo standard. Questo profilo è spesso più restrittivo del Profilo di dominio, che presume che un ambiente di dominio fornisca un livello di protezione base. Si suppone che il Profilo standard sia utilizzato quando un computer è su una rete non attendibile, come la rete di hotel o un punto di accesso pubblico senza fili. Tali ambienti rappresentano rischi sconosciuti e richiedono precauzioni di protezione aggiuntive.
  
Per ulteriori informazioni sulla modalità di utilizzo di NLA (Network Location Awareness) da parte di Windows XP per determinare il tipo di rete a cui è connesso, vedere l'articolo "Network Determination Behavior for Network-Related Group Policy Settings" sul sito Web di Microsoft all'indirizzo [http://www.microsoft.com/technet/community/columns/cableguy/cg0504.mspx.](http://www.microsoft.com/technet/community/columns/cableguy/cg0504,mspx)
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Modelli amministrativi\\Rete\\Connessioni di rete\\Windows Firewall\\Profilo standard
  
##### Windows Firewall: proteggi tutte le connessioni di rete (Profilo standard)
  
**Tabella A.40: impostazioni Proteggi tutte le connessioni di rete (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: proteggi tutte le connessioni di rete** attiva Windows Firewall, che sostituisce Firewall connessione Internet su tutti i computer con Windows XP SP2. Poiché tutte le connessioni di rete dovrebbero essere protette da un firewall in tutti gli ambienti, questa impostazione è configurata su **Attivato.**
  
Se questa impostazione è configurata su **Disattivato**, Windows Firewall è disabilitato e tutte le altre impostazioni di Windows Firewall sono ignorate.
  
**Nota**: se si abilita questa impostazione di criterio, Windows Firewall viene eseguito e ignora il criterio **Configurazione computer\\Modelli amministrativi\\Rete\\Connessioni di Rete\\Proibisci l'uso del Firewall Connessione Internet nella rete del dominio DNS**.
  
##### Windows Firewall: non consentire eccezioni (Profilo standard)
  
**Tabella A.41: impostazioni Non consentire eccezioni (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: non consentire eccezioni** specifica che Windows Firewall deve bloccare tutti i messaggi indesiderati in ingresso. Questa impostazione ignora tutte le altre impostazioni di criterio di Windows Firewall che consentono tali messaggi. Se si abilita questa impostazione nel componente Windows Firewall del Pannello di controllo, la casella **Non consentire eccezioni** sarà selezionata e gli amministratori non potranno deselezionarla.
  
**Nota**: questa impostazione fornisce una solida difesa contro i pirati informatici e dovrebbe essere configurata su **Attivato** a meno che non siano presenti eccezioni in altre impostazioni di criterio. L'impostazione di questo criterio su **Disattivato** consente a Windows Firewall di applicare altre impostazioni di criterio che consentano l'ingresso di messaggi indesiderati.
  
##### Windows Firewall: Definisci le eccezioni di programmi (Profilo standard)
  
**Tabella A.42: impostazioni Definisci le eccezioni programmi (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
<td style="border:1px solid black;"><p>Consigliata</p></td>
</tr>  
</tbody>  
</table>
  
Alcune applicazioni possono avere bisogno di aprire ed utilizzare le porte di rete che non sono normalmente abilitate da Windows Firewall. L'impostazione **Windows Firewall: definisci eccezioni programmi** consente di visualizzare e modificare l'elenco eccezioni di programmi definito nei Criteri di gruppo.
  
L'impostazione di questo criterio su **Attivato** consente di visualizzare e modificare l'elenco eccezioni di programmi. Se si aggiunge un programma a questo elenco e si imposta lo stato su **Attivato**, tale programma può ricevere messaggi in ingresso indesiderati su qualunque porta che chieda di aprire a Windows Firewall, anche se quella porta è bloccata da un'altra impostazione di criterio.
  
Se si configura questo criterio su **Disattivato**, l'elenco eccezioni di programmi definito di Criteri di gruppo viene cancellato.
  
**Nota**: se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza cercare errori. Questa funzionalità consente di aggiungere programmi non ancora installati; occorre considerare tuttavia che è possibile creare accidentalmente più voci per lo stesso programma con valori di stato o ambito in conflitto.
  
##### Windows Firewall: Consenti eccezioni di programmi locali (Profilo standard)
  
**Tabella A.43: impostazioni Consenti eccezioni programmi locali (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezioni programmi locali** consente che gli amministratori utilizzino il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di programmi locali. Se si disattiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo non consente agli amministratori di definire tale elenco e assicura che le eccezioni di programmi derivino unicamente dai Criteri di gruppo. Se si imposta questo criterio su **Attivato**, gli amministratori locali potranno utilizzare il Pannello di controllo per definire eccezioni di programmi in locale.
  
##### Windows Firewall: Consenti eccezione per amministrazione remota (Profilo standard)
  
**Tabella A.44: impostazioni Consenti eccezione per amministrazione remota (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
Molte organizzazioni approfittano dell'amministrazione remota del computer durante le attività quotidiane. Tuttavia, alcuni attacchi sfruttano le porte tipicamente utilizzate dai programmi di amministrazione remoti. Di conseguenza, Windows Firewall può bloccare queste porte. Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per amministrazione**.
  
Configurare questa impostazione su **Attivato** per consentire che il computer riceva messaggi in ingresso indesiderati per l'amministrazione remota sulle porte TCP 135 e 445. Questa impostazione di criterio consente inoltre a SVCHOST.EXE e a LSASS.EXE di ricevere messaggi in ingresso indesiderati e consente a servizi ospitati di aprire le porte aggiuntive assegnate dinamicamente, tipicamente nell'intervallo 1024-1034 ma potenzialmente dovunque da 1024 a 65535. Per abilitare questa impostazione è necessario specificare gli indirizzi di IP o le sottoreti da cui sono consentiti tali messaggi in ingresso.
  
Se si configura questo criterio su **Disattivato**, Windows Firewall non applicherà alcuna delle eccezioni descritte.
  
Questa appendice consiglia di disattivare questa impostazione per tutti i computer nel Profilo standard per evitare gli attacchi noti che utilizzano specificamente i punti deboli delle porte TCP 135 e 445.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezione per condivisione file e stampanti (Profilo standard)
  
**Tabella A.45: impostazioni Consenti eccezione per condivisione file e stampanti (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
Questa impostazione consente la condivisione di file e stampanti, configurando Windows Firewall in modo da aprire le porte UDP 137 e 138 e le porte TCP 139 e 445. Se si abilita questa impostazione di criterio, Windows Firewall apre queste porte in modo che il computer possa ricevere i processi di stampa e le richieste per l'accesso ai file condivisi. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi in ingresso sono consentiti.
  
Se si disattiva questa impostazione di criterio, Windows Firewall blocca queste porte e impedisce al computer di condividere file e stampanti.
  
Poiché i computer dell'ambiente in cui è in esecuzione Windows XP non condividono normalmente file e stampanti, si consiglia di configurare queste impostazioni su **Disattivato** in tutti gli ambienti.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezioni ICMP (Profilo standard)
  
**Tabella A.46: impostazioni Consenti eccezioni ICMP (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'opzione **Windows Firewall: consenti eccezioni ICMP** definisce la serie di tipi di messaggi ICMP (Internet Control Message Protocol) consentiti da Windows Firewall. Le utilità possono utilizzare i messaggi ICMP per determinare lo stato di altri computer. Per esempio, l'utilità Ping utilizza il messaggio di richiesta echo.
  
Se questo criterio è impostato su **Attivato**, specificare quali tipi di messaggi ICMP Windows Firewall consente di inviare o ricevere. Se questo criterio è impostato su **Disattivato**, Windows Firewall blocca tutti i tipi di messaggi ICMP in ingresso indesiderati e i tipi di messaggi ICMP in uscita contenuti nell'elenco. Di conseguenza, le utilità che utilizzano i messaggi ICMP bloccati non saranno in grado di inviare i messaggi a o dal computer.
  
Molti strumenti di aggressione approfittano dei computer che accettano i tipi di messaggi ICMP ed utilizzano questi messaggi per preparare vari attacchi. Tuttavia, alcune applicazioni richiedono certi messaggi ICMP per funzionare correttamente. Per tale ragione, quando è possibile, si consiglia di configurare l'impostazione su **Disattivato**. Quando il computer si trova su una rete non attendibile, questa impostazione dovrebbe essere **disattivata**.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezione per Desktop remoto (Profilo standard)
  
**Tabella A.47: impostazioni Consenti eccezione per Desktop remoto (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
Molte organizzazioni utilizzano connessioni Desktop remoto per le procedure di risoluzione dei problemi o per le normali attività. Tuttavia, alcuni attacchi sfruttano le porte tipicamente utilizzate dal desktop remoto. Per fornire flessibilità nell'amministrazione remota, è disponibile l'impostazione **Windows Firewall: consenti eccezione per Desktop remoto**.
  
Abilitando questa impostazione Windows Firewall apre la porta TCP 3389 per le connessioni in ingresso. Specificare inoltre gli indirizzi di IP o le sottoreti da cui è possibile ricevere questi messaggi in ingresso.
  
Se si disattiva questa impostazione di criterio, Windows Firewall blocca questa porta ed impedisce al computer di ricevere richieste di Desktop remoto. Se un amministratore tenta di aprire questa porta aggiungendola a un elenco di eccezioni porte locali, Windows Firewall non apre la porta.
  
Alcuni attacchi possono utilizzare una porta aperta 3389. Per mantenere le capacità di gestione migliorate fornite da Desktop remoto, configurare questa impostazione su **Attivato** e specificare gli indirizzi di IP e le sottoreti dei computer utilizzati per l'amministrazione remota. I computer nell'ambiente dovrebbero accettare richieste di Desktop remoto da meno computer possibile.
  
##### Windows Firewall: Consenti eccezione per framework UPnP (Profilo standard)
  
**Tabella A.48: impostazioni Consenti eccezione per framework UPnP (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezione per framework UPnP** consente a un computer di ricevere messaggi Plug and Play indesiderati inviati da periferiche di rete, come i router con firewall incorporati. Per ricevere questi messaggi, Windows Firewall apre la porta TCP 2869 e porta UDP 1900.
  
Se si abilita questa impostazione di criterio, Windows Firewall apre queste porte in modo che il computer possa ricevere i messaggi Plug and Play. Specificare gli indirizzi IP o le sottoreti da cui questi messaggi in ingresso sono consentiti. Se si disattiva questa impostazione di criterio, Windows Firewall blocca queste porte e impedisce al computer di ricevere messaggi Plug and Play.
  
Bloccando in modo efficace il traffico di rete UPnP, la superficie di attacco del computer viene ridotta. Questa impostazione dovrebbe essere sempre **disattivata** sulle reti non attendibili.
  
##### Windows Firewall: Proibisci notifiche (Profilo standard)
  
**Tabella A.49: impostazioni Proibisci notifiche (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
Windows Firewall può mostrare notifiche agli utenti quando un programma richiede che Windows Firewall aggiunga il programma all'elenco di eccezioni di programmi. Questa situazione si verifica quando i programmi tentano di aprire una porta e non sono autorizzati a farlo, in base alle regole di Windows Firewall attuali. L'impostazione **Windows Firewall: Proibisci notifiche** consente di scegliere se tali impostazioni devono essere mostrate agli utenti.
  
Se questo criterio è impostato su **Attivato**, Windows Firewall impedisce la visualizzazione di queste notifiche. Se questo criterio è impostato su **Disattivato**, Windows Firewall consente la visualizzazione di queste notifiche.
  
Spesso gli utenti non potranno aggiungere applicazioni e porte in risposta a questi messaggi in ambienti aziendali o ad alta protezione. In tali casi, questo messaggio informerà l'utente relativamente a un aspetto su cui non ha controllo. In quei casi impostare l'opzione su **Attivato.** In altri ambienti dove l'utente è configurato per consentire le eccezioni, impostare questa opzione su **Disattivato.**
  
##### Windows Firewall: Impedisci risposte unicast a richieste multicast o broadcast (Profilo standard)
  
**Tabella A.50: impostazioni Impedisci risposte unicast a richieste multicast o broadcast (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: impedisci risposte unicast a richieste multicast o broadcast** impedisce a un computer di ricevere risposte unicast ai messaggi multicast o broadcast in uscita. Quando questa impostazione di criterio è abilitata ed il computer invia messaggi multicast o broadcast ad altri computer, Windows Firewall blocca le risposte unicast inviate da tali computer. Quando l'impostazione è disattivata e il computer invia un messaggio multicast o broadcast agli altri computer, Windows Firewall attende per tre secondi le risposte unicast dagli altri computer, quindi blocca tutte le successive risposte.
  
Generalmente non è corretto ricevere risposte unicast a messaggi multicast o broadcast. Tali risposte possono indicare un attacco DoS (Denial of Service) o il tentativo di un aggressore di sondare un computer noto. Configurare questo criterio su **Attivato** per evitare questo tipo di attacco.
  
**Nota**: questa impostazione di criterio non ha effetto se il messaggio unicast è una risposta a un messaggio broadcast DHCP (Dynamic Host Configuration Protocol) inviato dal computer. Windows Firewall permette sempre tali risposte unicast DHCP. Tuttavia, questa impostazione di criterio può interferire con i messaggi NetBIOS che rilevano conflitti di nome.
  
##### Windows Firewall: Definisci eccezioni porte (Profilo standard)
  
**Tabella A.51: impostazioni Definisci eccezioni porte (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
<td style="border:1px solid black;"><p>Sconsigliato</p></td>
</tr>  
</tbody>  
</table>
  
L'elenco eccezioni porte di Windows Firewall deve essere definito dai Criteri di gruppo, che consente di gestire e distribuire centralmente le eccezioni di porta ed assicura che gli amministratori locali non creino impostazioni meno sicure. L'impostazione **Windows Firewall: definisci eccezioni porte** consente di gestire centralmente queste impostazioni.
  
Se si abilita questa impostazione di criterio, è possibile visualizzare e modificare l'elenco eccezioni porta definito dai Criteri di gruppo. Per visualizzare e modificare l'elenco eccezioni porte, configurare il criterio su **Attivato** e fare clic su pulsante **Mostra**. Se si digita una stringa di definizione non valida, Windows Firewall l'aggiunge all'elenco senza controllare la presenza di errori, il che significa che è possibile creare accidentalmente più voci per la stessa porta con valori di stato o ambito in conflitto.
  
Se si disattiva questa impostazione di criterio, l'elenco eccezioni porte definito dai Criteri di gruppo viene cancellato, ma le altre impostazioni di criterio possono continuare ad aprire o bloccare le porte. Inoltre, se esiste un elenco di eccezioni porte locali, viene ignorato, a meno che non si abiliti l'impostazione **Windows Firewall: consenti eccezioni porte locali**.
  
Gli ambienti con applicazioni non standard che richiedono porte specifiche per essere aperti dovrebbero considerare la distribuzione di eccezioni di programmi. Abilitare questa impostazione e specificare un elenco di eccezioni di porte soltanto quando non possono essere definite eccezioni di programmi. Le eccezioni di programmi consentono a Windows Firewall di accettare il traffico di rete indesiderato soltanto mentre il programma specificato è in esecuzione, e le eccezioni di porta tengono sempre aperte le porte specificate.
  
**Nota**: se una impostazione di criterio apre la porta TCP 445, Windows Firewall consente i messaggi di richiesta echo ICMP in ingresso (come quelli inviati dall'utilità Ping), anche se l'opzione **Windows Firewall: consenti eccezioni ICMP** li bloccherebbe. Le impostazioni di criterio che possono aprire la porta di TCP 445 comprendono **Windows Firewall: consenti eccezione e condivisione file e stampanti**, **Windows Firewall: consenti eccezione per amministrazione remota**, e **Windows Firewall: definisci eccezioni porte**.
  
##### Windows Firewall: Consenti eccezioni porte locali (Profilo standard)
  
**Tabella A.52: impostazioni Consenti eccezioni porte locali (Profilo standard)**

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
<th><p>Desktop client organizzazione</p></th>  
<th><p>Portatile client organizzazione</p></th>  
<th><p>Desktop livello di protezione Alto</p></th>  
<th><p>Portatile livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione **Windows Firewall: consenti eccezioni porte locali** consente agli amministratori di utilizzare il componente Windows Firewall nel Pannello di controllo per definire un elenco di eccezioni di porte locali. Windows Firewall può utilizzare due elenchi di eccezioni di porte; l'altro è definito dal criterio **Windows Firewall: definisci eccezioni porte**.
  
Se si attiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo consente agli amministratori di definire un elenco di eccezioni di porte locali. Se si disattiva questa impostazione di criterio, il componente di Windows Firewall nel Pannello di controllo non consente agli amministratori di definire tale elenco.
  
Di norma, gli amministratori locali non sono autorizzati a ignorare il criterio dell'organizzazione e a stabilire i propri elenchi di eccezioni porte in ambienti aziendali o ad alta protezione. Per tale ragione, si consiglia di configurare questa opzione su **Disattivato.**
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni configurazione utente
  
Le sezioni rimanenti di questa appendice descrivono le impostazioni configurazione utente. Applicare queste impostazioni attraverso un GPO collegato a un OU che contiene gli account utente.
  
**Nota**: le impostazioni configurazione utente vengono applicate a tutti i client ai quali un utente accede in un dominio del servizio di directory Microsoft Active Directory. Le impostazioni di configurazione del computer si riferiscono a tutti i client gestiti da un GPO in Active Directory, indipendentemente dall'utente che accede al client. Perciò, le tabelle in questa sezione contengono solo impostazioni consigliate per gli ambienti Client di organizzazione e Livello di protezione Alto definiti in questa guida. Non sono presenti indicazioni relative ai computer portatili o ai desktop per queste impostazioni.
  
#### Gestione allegati
  
Utilizzare l'Editor oggetti Criteri di gruppo per configurare i Modelli amministrativi corretti. Le impostazioni consigliate sono in:
  
Configurazione utente\\Modelli amministrativi\\Componenti di Windows\\Gestione allegati
  
##### Non conservare le informazioni di area nei file allegati
  
**Tabella A.53: impostazioni Non conservare le informazioni di area nei file allegati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Client di organizzazione</p></th>  
<th><p>Livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Non conservare le informazioni di area nei file allegati** consente di configurare Windows in modo da contrassegnare i file allegati di Internet Explorer o Outlook Express con informazioni relative all'area di origine (come limitato, Internet, Intranet o locale). Questa impostazione richiede che i file siano scaricati sulle partizioni del disco NTFS per funzionare correttamente. Se le informazioni di area non sono conservate, Windows non può valutare correttamente il rischio in base alla zona da cui proviene l'allegato.
  
Se si imposta questo criterio su **Attivato**, i file allegati non vengono contrassegnati con le informazioni relative all'area di origine. Se si imposta questo criterio su **Disattivato**, Windows memorizza i file allegati con le informazioni relative all'area di origine. Poiché gli allegati pericolosi vengono spesso scaricati da aree di Internet Explorer non attendibili come l'area Internet, questa appendice consiglia di configurare questa impostazione su **Disattivato** per assicurare che i file conservino il più possibile informazioni relative alla protezione.
  
##### Nascondi meccanismi di rimozione informazioni sull'area
  
**Tabella A.54: impostazioni Nascondi meccanismi di rimozione informazioni sull'area**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Client di organizzazione</p></th>  
<th><p>Livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
L'impostazione di criterio **Nascondi meccanismi di rimozione informazioni sull'area** consente di scegliere se gli utenti possono rimuovere manualmente le informazioni sull'area dai file allegati salvati facendo clic sul pulsante **Annulla blocco** nella finestra **Proprietà** del file o selezionando la casella di controllo nella finestra di dialogo **Avviso di protezione**. Se si rimuovono le informazioni sull'area, gli utenti possono aprire file allegati potenzialmente pericolosi che Windows impedisce di aprire.
  
Windows nasconde la casella di controllo e il pulsante **Annulla blocco** quando questa impostazione di criterio è **attivata.** Quando l'impostazione è **disattivata**, Windows visualizza la casella di controllo e il pulsante **Annulla blocco**. Poiché gli allegati pericolosi vengono spesso scaricati da aree di Internet Explorer non attendibili come l'area Internet, questa appendice consiglia di configurare questa impostazione su **Attivato** per assicurare che i file conservino il più possibile informazioni relative alla protezione.
  
**Nota**: per configurare il salvataggio dei file con le informazioni sull'area, vedere la precedente impostazione di criterio **Non conservare le informazioni di area nei file allegati.**
  
##### Notifica programmi antivirus quando vengono aperti allegati
  
**Tabella A.55: impostazioni Notifica programmi antivirus quando vengono aperti allegati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Client di organizzazione</p></th>  
<th><p>Livello di protezione Alto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
I programmi antivirus stanno diventando obbligatori nella maggior parte degli ambienti e sono una solida linea di difesa contro gli attuali attacchi. L'impostazione di criterio **Notifica programmi antivirus quando vengono aperti allegati** consente di gestire le notifiche relative ai programmi antivirus registrati.
  
Se si seleziona **Attivato**, questa impostazione di criterio configura Windows in modo da chiedere al programma antivirus registrato di eseguire una scansione dei file allegati quando vengono aperti dagli utenti. Se la scansione antivirus non è completata con successo, l'apertura degli allegati non è consentita. Se questa impostazione di criterio è configurata su **Disattivato**, Windows non richiama il programma antivirus registrato quando i file allegati vengono aperti.
  
Per assicurarsi che i programmi antivirus esaminino ogni file prima che venga aperto, questa appendice consiglia di configurare questo criterio su **Attivato** in tutti gli ambienti.
  
**Nota**: perché questa impostazione funzioni correttamente, è necessario installare un programma antivirus aggiornato. Molti programmi antivirus aggiornati utilizzano API nuove incluse con SP2.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
I numerosi miglioramenti relativi alla facilità di gestione dei servizi di protezione in Windows XP SP2 consente agli amministratori di installare impostazioni di protezione più specifiche sia per gli utenti sia per i computer. Questa appendice ha illustrato le impostazioni più importanti che dovrebbero essere utilizzate per migliorare la protezione di un ambiente SP2. Sebbene l'appendice non descriva tutte le possibili impostazioni, quelle specificate possono avere un impatto diretto e profondo sull'ambiente.
  
SP2 rappresenta una modifica significativa rispetto alle versioni precedenti di Windows, perciò è probabile che si verifichino problemi di compatibilità tra le applicazioni dell'ambiente. È consigliabile verificare attentamente tutte le impostazioni consigliate prima di installarle. Sebbene queste impostazioni siano state esaurientemente verificate per assicurarne la funzionalità negli ambienti specificati, non c'è modo di testarle in un ambiente specifico.
  
[](#mainsection)[Inizio pagina](#mainsection)
