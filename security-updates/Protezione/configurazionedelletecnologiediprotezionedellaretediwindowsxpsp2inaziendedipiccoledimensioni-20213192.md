---
TOCTitle: Configurazione delle tecnologie di protezione della rete di Windows XP SP2 in aziende di piccole dimensioni
Title: Configurazione delle tecnologie di protezione della rete di Windows XP SP2 in aziende di piccole dimensioni
ms:assetid: 'c74175c6-46bd-4fd2-976f-9b89daf37348'
ms:contentKeyID: 20213192
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875819(v=TechNet.10)'
---

Configurazione delle tecnologie di protezione della rete di Windows XP SP2 in aziende di piccole dimensioni
===========================================================================================================

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[Prima di iniziare](#egaa)
[](#efaa)[Applicazione di patch di protezione](#efaa)
[](#eeaa)[Aggiornamento degli oggetti Criteri di gruppo esistenti](#eeaa)
[](#edaa)[Configurazione di oggetti Criteri di gruppo](#edaa)
[](#ecaa)[Informazioni sulle impostazioni di protezione di Internet Explorer](#ecaa)
[](#ebaa)[Applicazione di nuove configurazioni con GPUpdate](#ebaa)
[](#eaaa)[Informazioni correlate](#eaaa)

### Introduzione

Il servizio directory Active Directory consente di gestire in modo centralizzato la configurazione della protezione delle workstation e dei server di una piccola azienda e offre un modo più sicuro e più facile di gestire l'ambiente delle workstation.

In questo articolo viene illustrata la gestione centralizzata delle workstation che eseguono Microsoft Windows XP con Service Pack 2 (SP2). L'applicazione di oggetti Criteri di gruppo (GPO) alle workstation per la gestione delle impostazioni di protezione dipende unicamente da Active Directory.

#### Obiettivo del documento

Le esigenze di protezione variano in base all'organizzazione. Ogni utente, indipendentemente dalla rigorosità dei propri requisiti di protezione, dovrebbe essere in grado di applicare i concetti illustrati in questo articolo per meglio gestire la protezione delle workstation.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

Per completare le procedure seguenti, è necessario eseguire l'accesso come membro del gruppo Domain Admins.

**Nota**   Se risulta impossibile apportare modifiche a una workstation o a un server, la causa potrebbe essere dovuta a Criteri di gruppo. In questi casi, sarà necessario apportare le modifiche a livello di Criteri di gruppo.

Completare le attività descritte in questo documento per configurare le tecnologie di protezione della rete di Windows XP SP2 con Criteri di gruppo:

-   Applicazione di patch di protezione

-   Aggiornamento degli oggetti Criteri di gruppo (GPO) esistenti

-   Configurazione delle impostazioni di Centro sicurezza PC

-   Configurazione delle impostazioni di Windows Firewall

-   Configurazione delle impostazioni di Internet Explorer

-   Configurazione delle impostazioni di Gestione comunicazioni Internet

-   Applicazione delle impostazioni con GPUpdate

[](#mainsection)[Inizio pagina](#mainsection)

### Applicazione di patch di protezione

È consigliabile applicare le patch di protezione e i Service Pack più aggiornati in tutte le workstation e i server Windows. Prima di applicare le patch, è sempre buona norma eseguire il backup del computer o dei file importanti.

**Nota**   Alcune delle funzionalità illustrate in questo articolo e alcune delle funzionalità di protezione critiche dipendono da alcune delle patch o dagli aggiornamenti rapidi più recenti. Se i controller di dominio non sono aggiornati, potrebbero non contenere i modelli amministrativi necessari per la workstation Windows XP SP2 all'interno degli oggetti Criteri di gruppo. Senza i modelli amministrativi, le nuove funzionalità di protezione di SP2 non saranno disponibili.

[](#mainsection)[Inizio pagina](#mainsection)

### Aggiornamento degli oggetti Criteri di gruppo esistenti

Il modo migliore di gestire gli oggetti Criteri di gruppo consiste nell'utilizzare la [console Microsoft Group Policy Management Console (GPMC)](http://www.microsoft.com/windowsserver2003/gpmc/gpmcintro.mspx), che può essere scaricata dal sito Web Microsoft all'indirizzo www.microsoft.com/windowsserver2003/gpmc/gpmcintro.mspx (in inglese). Rappresenta un'alternativa all'utilizzo di Microsoft Management Console (MMC) con lo snap-in Editor oggetti Criteri di gruppo.

Nella console Microsoft Gestione Criteri di gruppo l'Editor oggetti Criteri di gruppo viene utilizzato anche per modificare gli oggetti Criteri di gruppo.

1.  Nella console Microsoft Gestione Criteri di gruppo fare doppio clic sull'oggetto Criteri di gruppo che si desidera aggiornare con il nuovo modello amministrativo. L'oggetto Criteri di gruppo verrà visualizzato nell'Editor oggetti Criteri di gruppo.

2.  Fare clic su **OK**, quindi su **Fine**. Verrà così applicato il nuovo modello.

3.  Ripetere la procedura per ogni oggetto Criteri di gruppo.

[](#mainsection)[Inizio pagina](#mainsection)

### Configurazione di oggetti Criteri di gruppo

Per configurare oggetti Criteri di gruppo nell'ambiente in uso, eseguire le procedure seguenti.

#### Configurazione delle impostazioni del Centro sicurezza PC

È possibile attivare Centro sicurezza PC in ogni workstation sotto il controllo Criteri di gruppo. Se il Centro sicurezza PC è installato, l'utente di ogni workstation può ricevere informazioni sullo stato di Windows Firewall, dell'antivirus e delle impostazioni di Aggiornamenti automatici. Per impostazione predefinita, questa funzionalità non viene attivata da Criteri di gruppo.

1.  Aprire la console Microsoft Gestione Criteri di gruppo e fare doppio clic sull'oggetto Criteri di gruppo che si desidera utilizzare per applicare Centro sicurezza PC in ogni workstation.

2.  All'interno dell'oggetto Criteri di gruppo selezionato aprire **Configurazione computer**, **Modelli amministrativi**, **Componenti di Windows**, quindi **Centro sicurezza PC**.

3.  Fare doppio clic su **Attiva Centro sicurezza PC (solo computer in un dominio)**.

4.  Attivare questa impostazione.

5.  Fare clic su **OK**.

#### Configurazione delle impostazioni di Windows Firewall

In questa sezione vengono descritte le impostazioni di Windows Firewall in un oggetto Criteri di gruppo e le impostazioni consigliate per le aziende di piccole dimensioni.

1.  All'interno dell'oggetto Criteri di gruppo selezionato aprire **Configurazione computer**, **Modelli amministrativi**, **Rete**, **Connessioni di rete**, **Windows Firewall**, quindi **Profilo di dominio**.

2.  Fare doppio clic su ogni impostazione e configurare in base alle informazioni riportate nella tabella seguente.

    **Nota**   Dopo aver attivato **Definisci eccezioni programmi** nel profilo di dominio, è necessario immettere tutti i programmi ai quali è consentito stabilire connessioni con i computer, prima di fare clic su **OK**.

**Tabella 1. Impostazioni di Windows Firewall consigliate per aziende di piccole dimensioni**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Impostazione</p></th>
<th><p>Descrizione</p></th>
<th><p>Profilo di dominio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Proteggi tutte le connessioni di rete</p></td>
<td style="border:1px solid black;"><p>Consente di attivare Windows Firewall su tutte le connessioni di rete.</p></td>
<td style="border:1px solid black;"><p>Attivata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Non consentire eccezioni</p></td>
<td style="border:1px solid black;"><p>Specifica che tutto il traffico non richiesto deve essere ignorato, compreso quello elencato nelle eccezioni.</p></td>
<td style="border:1px solid black;"><p>Non configurata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Definisci eccezioni programmi</p></td>
<td style="border:1px solid black;"><p>Consente di definire il traffico consentito in termini di nomi di file di programma.</p></td>
<td style="border:1px solid black;"><p>Attivata e configurata per i programmi (applicazioni e servizi) utilizzati dai computer della rete basati su Windows XP SP2.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Consenti eccezioni programmi locali</p></td>
<td style="border:1px solid black;"><p>Consente la configurazione locale delle eccezioni programmi.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consenti eccezione per amministrazione remota</p></td>
<td style="border:1px solid black;"><p>Consente la configurazione remota mediante strumenti.</p></td>
<td style="border:1px solid black;"><p>Disattivata, a meno che non si desideri attivare l'amministrazione remota dei computer con gli snap-in MMC.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Consenti eccezione condivisione file e stampanti</p></td>
<td style="border:1px solid black;"><p>Consente di specificare se il traffico di condivisione di file e stampanti è consentito.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consenti eccezioni ICMP</p></td>
<td style="border:1px solid black;"><p>Consente di specificare i tipi di messaggi ICMP consentiti.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Consenti eccezione per Desktop remoto</p></td>
<td style="border:1px solid black;"><p>Consente di specificare se il computer è autorizzato ad accettare una richiesta di connessione basata su Desktop remoto.</p></td>
<td style="border:1px solid black;"><p>Attivata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consenti eccezione per framework UPnP</p></td>
<td style="border:1px solid black;"><p>Consente di specificare se il computer è autorizzato a ricevere messaggi UPnP non richiesti.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Proibisci notifiche</p></td>
<td style="border:1px solid black;"><p>Consente di disattivare le notifiche.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consenti registrazione</p></td>
<td style="border:1px solid black;"><p>Attiva la registrazione del traffico e configura le impostazioni del file registro.</p></td>
<td style="border:1px solid black;"><p>Non configurata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Impedisci risposte unicast a richieste multicast o broadcast</p></td>
<td style="border:1px solid black;"><p>Consente di ignorare i pacchetti unicast ricevuti in risposta a un messaggio di richiesta multicast o broadcast.</p></td>
<td style="border:1px solid black;"><p>Attivata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Definisci eccezioni porte</p></td>
<td style="border:1px solid black;"><p>Consente di specificare il traffico consentito in termini di TCP e UDP.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Consenti eccezioni porte locali</p></td>
<td style="border:1px solid black;"><p>Consente la configurazione locale delle eccezioni porte.</p></td>
<td style="border:1px solid black;"><p>Disattivata.</p></td>
</tr>  
</tbody>  
</table>
  
Per ulteriori informazioni, vedere [How to Configure Windows Firewall in a Small Business Environment using Group Policy](http://technet.microsoft.com/it-it/library/cc875816.aspx) all'indirizzo www.microsoft.com/technet/security/smallbusiness/prodtech/windowsxp/fwgrppol.mspx (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Informazioni sulle impostazioni di protezione di Internet Explorer
  
Le impostazioni dei criteri di protezione consentono di gestire scenari specifici che potrebbero influenzare la protezione di Internet Explorer. Nella maggior parte dei casi, si desidera impedire un comportamento specifico ed è pertanto necessario assicurarsi che le funzionalità di protezione siano attivate. Microsoft consiglia Internet Explorer 6 in quanto le sue nuove funzionalità aumentano la protezione del browser.
  
#### Aree di protezione
  
In Internet Explorer i siti Web vengono classificati in quattro aree di protezione, ognuna delle quali offre diversi livelli di protezione. Le aree di protezione sono Internet, Intranet locale, Siti attendibili e Siti con restrizioni. Ogni area può essere configurata in modo indipendente con livelli di protezione predefiniti da Alta a Bassa. Internet Explorer consente inoltre di definire un insieme personalizzato di opzioni di protezione per ogni area di protezione. Microsoft ha specificato impostazioni di protezione predefinite per ogni area. Nella tabella seguente sono riportate una descrizione di ogni area di protezione e le relative impostazioni di protezione predefinite Microsoft.
  
**Tabella 2. Descrizioni delle aree di protezione e impostazioni di protezione predefinite**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Area di protezione</p></th>  
<th><p>Livello di protezione predefinito</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Area Internet</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>L'area Internet è costituita da tutti i siti Web non inclusi nelle altre aree.<br />
<br />
<strong>Nota</strong>   La minaccia proveniente da Internet è estremamente concreta. Microsoft è particolarmente impegnata a proteggere gli utenti dalle minacce Internet, pertanto non è possibile impostare il livello di protezione su Bassa, nemmeno con il pulsante avanzato <strong>Livello personalizzato</strong>.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Area Intranet locale</p></td>
<td style="border:1px solid black;"><p>Medio-bassa</p></td>
<td style="border:1px solid black;"><p>Tutti i siti in quest'area devono trovarsi all'interno del firewall.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Area Siti attendibili</p></td>
<td style="border:1px solid black;"><p>Bassa</p></td>
<td style="border:1px solid black;"><p>I siti nell'Area siti attendibili sono autorizzati a eseguire una gamma più ampia di operazioni e in essi agli utenti viene chiesto di prendere un numero minore di decisioni relative alla protezione. Aggiungere siti a quest'area solo se si è certi che nessuna parte del loro contenuto comporterà mai l'esecuzione di operazioni dannose sui computer.<br />
Per l'Area siti attendibili, è consigliabile utilizzare il protocollo HTTPS (Hypertext Transmission Protocol, Secure) o assicurarsi in altro modo che le connessioni al sito siano completamente protette.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Area Siti con restrizioni</p></td>
<td style="border:1px solid black;"><p>Alta</p></td>
<td style="border:1px solid black;"><p>Quest'area è stata progettata per consentire di aggiungere siti considerati non attendibili. Controlla e limita le funzionalità Web, ma non blocca l'accesso ai siti. I siti possono essere aggiunti dall'utente o applicati tramite Criteri di gruppo. Per bloccare l'accesso ai siti Web è necessario utilizzare un server proxy che supporti questa funzionalità.</p></td>
</tr>  
</tbody>  
</table>
  
#### Aumento della protezione
  
In ogni area di protezione sono presenti oltre 30 impostazioni che possono essere modificate singolarmente per aumentare specifiche aree di funzionalità. La maggior parte delle impostazioni consente di attivare o disattivare l'opzione oppure di richiedere l'intervento dell'utente. È consigliabile che gli utenti limitino il numero di impostazioni delle opzioni che richiedono intervento in tutte le aree di protezione. Criteri restrittivi di protezione delle informazioni limitano le autorizzazioni degli utenti e impediscono loro di intraprendere azioni che potrebbero compromettere la protezione. È necessario definire e stabilire le impostazioni dell'area di protezione per singola area. Non è mai consigliato utilizzare un'unica serie di definizioni per tutte le aree. Nella tabella seguente è riportato un esempio di alcune impostazioni predefinite per le aree di protezione. Per soddisfare le esigenze delle organizzazioni è possibile modificare queste e altre impostazioni.
  
**Tabella 3. Impostazione dei criteri per le aree di protezione**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Area di protezione</p></th>  
<th><p>Impostazioni criteri</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Area Internet</p></td>
<td style="border:1px solid black;"><p>Usa blocco popup = Attiva<br />
Richiesta di conferma automatica per controlli ActiveX = Disattiva<br />  
Scarica controlli ActiveX con firma elettronica = Chiedi conferma<br />
Download dei file = Attiva</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Area Intranet locale</p></td>
<td style="border:1px solid black;"><p>Usa blocco popup = Disattiva<br />
Richiesta di conferma automatica per controlli ActiveX = Attiva<br />  
Scarica controlli ActiveX con firma elettronica = Chiedi conferma<br />
Download dei file = Attiva</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Area Siti attendibili</p></td>
<td style="border:1px solid black;"><p>Usa blocco popup = Disattiva<br />
Richiesta di conferma automatica per controlli ActiveX = Attiva<br />  
Scarica controlli ActiveX con firma elettronica = Attiva<br />
Download dei file = Attiva</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Area Siti con restrizioni</p></td>
<td style="border:1px solid black;"><p>Usa blocco popup = Attiva<br />
Richiesta di conferma automatica per controlli ActiveX = Disattiva<br />  
Scarica controlli ActiveX con firma elettronica = Disattiva<br />
Download dei file = Disattiva</p></td>
</tr>
</tbody>
</table>
<p> </p>

ActiveX è una potente piattaforma di sviluppo Web di estendibilità che agevola in modo notevole l'esperienza in linea dell'utente. Molti utenti aziendali utilizzano i controlli ActiveX per applicazioni line-of-business interne. È pertanto necessario attivare ActiveX in Internet Explorer. Gli standard di protezione e i criteri di utilizzo accettabili dell'utente possono richiedere la disattivazione di ActiveX per l'area Internet. La disattivazione dei controlli ActiveX, tramite Criteri di gruppo o l'impostazione del controllo dell'area di protezione su Alta, può causare il funzionamento non corretto dei siti Web. Microsoft consiglia alle organizzazioni di definire i criteri per risolvere questo problema e di predisporre una strategia che consenta l'accesso in base alla giustificazione commerciale.

ActiveX rappresenta un problema per la protezione poiché può eseguire comandi all'interno della console del browser. È consigliabile consentire l'esecuzione di ActiveX solo da siti Web attendibili.

Per una spiegazione più dettagliata delle aree di protezione e delle opzioni di configurazione visitare la pagina relativa alla [configurazione delle aree di protezione](http://www.microsoft.com/windows/ie/using/howto/security/setup.mspx) all'indirizzo www.microsoft.com/windows/ie/using/howto/security/setup.mspx.

#### Privacy/cookie

Al fine di offrire esperienze in linea personalizzate più sicure, in alcuni siti Web le informazioni vengono memorizzate in piccoli file di testo nel computer dell'utente,chiamati cookie. In Internet Explorer 6 sono disponibili diversi meccanismi che consentono di controllare l'utilizzo dei cookie.

Esistono diversi tipi di cookie. I cookie dei siti Web visualizzati sono leggibili solo dal sito Web che li emette. Esiste un altro tipo di cookie, chiamato cookie di terze parti, utilizzato da entità Web per registrare i dati sui visitatori. I cookie di terze parti sono utilizzati da numerosi siti Web. I dati in essi contenuti possono spaziare dagli ID e password degli utenti ai codici postali.

-   **Cookie dei siti Web visualizzati**. Leggibili solo dal sito che li emette.

-   **Cookie di terze parti**. Possono essere letti e scritti da numerosi siti Web.

Gli utenti possono non sapere di avere un qualche controllo sui dati che vengono memorizzati nei cookie. Il semplice clic su una casella di controllo per ricordare un indirizzo di fatturazione può lasciare dati indesiderati in un cookie dei siti Web visualizzati o di terze parti.

Ogni organizzazione deve stabilire criteri propri in merito ai cookie. Microsoft consiglia almeno l'impostazione **Media**. Questa impostazione blocca i cookie di terze parti privi di una versione compatta dell'informativa sulla privacy e i cookie di terze parti che utilizzano informazioni che consentono l'identificazione personale dell'utente senza il consenso implicito di quest'ultimo. Blocca inoltre i cookie dei siti Web visualizzati che utilizzano informazioni che consentono l'identificazione personale dell'utente senza il consenso implicito di quest'ultimo. L'impostazione **Alta** limita tutti i cookie, mentre le altre li consentono in determinate condizioni. L'impostazione **Bassa** consente incondizionatamente tutti i cookie.

Per eludere l'impostazione complessiva è possibile aggiungere siti. Le scelte disponibili per aggiungere un sito sono **Blocca sempre** o **Consenti sempre**. Sarà possibile aggiungere siti a prescindere dall'opzione più o meno restrittiva scelta. È possibile utilizzare Criteri di gruppo per applicare non solo le impostazioni dei cookie ma anche per specificare i siti.

**Nota**   Non è possibile controllare i cookie in ogni area. Questa impostazione è espressa su tutte e quattro le aree di protezione.

#### Blocco popup

Blocco popup consente di bloccare la maggior parte delle finestre popup indesiderate. Le finestre popup che vengono aperte quando l'utente fa clic su un collegamento non verranno bloccate. È possibile configurare il Blocco popup per ogni singola area, per bloccare i siti in un'area e non in altre. È possibile utilizzare Criteri di gruppo per applicare il Blocco popup in ogni area e aggiungere un elenco dei siti consentiti.

I popup possono diventare ingombranti e talmente numerosi e persistenti da rendere praticamente inutilizzabile il browser. Ogni volta che un popup viene bloccato, viene segnalato nella barra degli strumenti di Internet Explorer.

**Nota**   È possibile controllare il Blocco popup in ogni area, ma i siti consentiti vengono aggiunti in tutte e quattro le aree.

#### Programmi Internet

È possibile configurare Internet Explorer per avviare altri programmi che consentono di inviare messaggi di posta elettronica, gestire i contatti o visualizzare l'origine della pagina. Quando un utente fa clic su un indirizzo di posta elettronica in una pagina Web, ad esempio, in Internet Explorer viene aperto il programma di posta elettronica definito con un nuovo messaggio di posta elettronica in uscita contenente l'indirizzo del destinatario. Questa funzionalità consente di inviare in modo efficiente i messaggi di posta elettronica senza dover aprire un altro programma e immettere manualmente l'indirizzo. Comporta, tuttavia, un certo rischio potenziale. Se uno di questi programmi associati venisse cambiato rispetto alle applicazioni standard dell'organizzazione, potrebbero verificarsi un comportamento o funzionalità impreviste. Per applicare le impostazioni per questo elenco di programmi e offrire una certa sicurezza che non verranno avviati programmi indesiderati, è possibile utilizzare Criteri di gruppo.

#### Componenti aggiuntivi

I componenti aggiuntivi sono piccoli programmi progettati per eseguire specifiche funzioni e possono essere caricati su richiesta da una pagina Web. Le barre degli strumenti e gli oggetti browser helper (BHO, Browser Helper Objects) sono altri programmi che consentono di installare pulsanti e funzioni aggiuntive per estendere le funzionalità dall'interno del browser. Microsoft consiglia alle organizzazioni di definire un elenco di barre degli strumenti e oggetti browser helper consentiti e di utilizzare Criteri di gruppo per applicare queste impostazioni.

Molti sviluppatori utilizzano la piattaforma ActiveX per realizzare strumenti che consentono di aumentare la produttività o di migliorare le funzionalità. Microsoft incoraggia la comunità di sviluppo a continuare a offrire questi componenti aggiuntivi, ma riconosce la necessità di distribuirli da fonti attendibili. In Internet Explorer 6 è disponibile Authenticode per convalidare l'autenticità di un componente aggiuntivo tramite firme digitali. Microsoft consiglia alle organizzazioni di autorizzare solo componenti aggiuntivi con firma nell'area Internet. I siti nell'area Intranet locale potrebbero non richiedere la firma Authenticode, perché è probabile che questi componenti aggiuntivi vengano sviluppati da sviluppatori interni attendibili.

#### Configurazione di Criteri di gruppo per Internet Explorer 6

È possibile configurare e proteggere tutte le funzionalità di protezione di Internet Explorer 6 tramite Criteri di gruppo. Esistono numerose impostazioni di protezione basate su oggetti Criteri di gruppo per gestire vari componenti di Internet Explorer. In questo documento vengono pertanto illustrate le diramazioni principali (a, b, c e d nella procedura seguente). L'Editor oggetti Criteri di gruppo fornisce dettagli sulle ramificazioni di tutte le impostazioni nelle quattro diramazioni. Leggere attentamente ogni descrizione e verificare l'efficacia delle impostazioni desiderate prima di implementarle.

1.  Aprire la console Gestione Criteri di gruppo.

2.  Creare un nuovo oggetto Criteri di gruppo, ad esempio Internet Explorer 6.

3.  I criteri di Internet Explorer sono contenuti nelle quattro diramazioni seguenti della struttura dei criteri nell'Editor oggetti Criteri di gruppo. Configurare ogni oggetto Criteri di gruppo in tutte e quattro le diramazioni in base ai requisiti dell'organizzazione.

    1.  **Configurazione computer**, **Modelli amministrativi**, **Componenti di Windows**, **Internet Explorer**

        All'interno di questa diramazione sono presenti criteri di protezione supplementari per bloccare le impostazioni di protezione, oltre a quanto è già disponibile all'interno del browser stesso. Uno dei criteri più utili è **Aree di protezione: impedisci la modifica del criterio**. Per impostazione predefinita, questo criterio è disattivato nell'oggetto Criteri di gruppo. Se è attivato, impedisce all'utente di modificare qualsiasi impostazione di protezione all'interno delle impostazioni del browser. Microsoft consiglia di impostarlo su **Attivato**. Dopo essere state configurate da Criteri di gruppo, queste impostazioni non possono essere modificate nemmeno dagli amministratori locali. Esistono altri criteri che possono essere attivati, alcuni riguardano la protezione, altri no. Prima di attivarli leggere attentamente le descrizioni pertinenti.

    2.  **Configurazione computer**, **Modelli amministrativi**, **Sistema**, **Impostazioni di comunicazione Internet**

        Questa diramazione è specifica per Window XP SP2. Contiene 20 nuovi criteri che vanno dalle funzionalità di pubblicazione Web al supporto multimediale. Un criterio, **Disattiva servizio Internet associazioni file**, impedisce al browser di aprire le applicazioni associate a estensioni file quando il contenuto viene scaricato da un sito Web. Questa funzione è simile a quella del sistema operativo che apre automaticamente Notepad.exe per i file con estensione txt. Un altro criterio, **Disattiva stampa su HTTP**, è progettato per impedire a un utente di stampare su Internet/Intranet tramite HTTP. Non influisce sulla sua capacità di ospitare una stampante HTTP propria. Prima di attivarlo leggere attentamente le descrizioni pertinenti.

    3.  **Configurazione utente**, **Impostazioni di Windows**, **Manutenzione di Internet Explorer**, **Protezione**, **Programmi**

        In queste due sezioni sono contenute le impostazioni/i criteri che influenzano la protezione del browser. In entrambe sono presenti le impostazioni a livello di utente che si trovano all'interno di ogni singola impostazione di protezione/privacy del browser. È consigliare utilizzare le impostazioni predefinite minime Microsoft, ma è necessario impostare le configurazioni in base ai requisiti dell'organizzazione.

        **Nota**   È possibile aggiungere siti a qualsiasi area tranne Internet. Selezionare attentamente i siti da aggiungere alla Intranet locale, alle aree attendibili e con restrizioni poiché si applicano a tutte le workstation e a tutti i server collegati con l'oggetto Criteri di gruppo.

    4.  **Configurazione utente**, **Modelli amministrativi**, **Componenti di Windows**, **Internet Explorer**

        In questa diramazione sono contenute impostazioni dettagliate per limitare le modifiche alle impostazioni del browser, invece di impedire completamente agli utenti di eseguire qualsiasi modifica. Queste impostazioni si applicano alle modifiche per elementi quali i controlli File Internet temporanei e la modifica della pagina iniziale. In questa diramazione sono contenute numerose opzioni di impostazione e Microsoft consiglia agli amministratori di leggere e di verificare i loro effetti prima di utilizzarli in un ambiente di produzione.

4.  Al termine delle operazioni con l'Editor dei criteri, collegare il nuovo oggetto Criteri di gruppo a tutti i domini con le workstation e i server Windows.

5.  Configurare i **filtri di protezione** per l'oggetto Criteri di gruppo secondo i gruppi, gli utenti e i computer che potrebbero essere interessati da questo oggetto Criteri di gruppo. Alcuni criteri sono progettati per i computer, altri si applicano solo agli utenti.

[](#mainsection)[Inizio pagina](#mainsection)

### Applicazione di nuove configurazioni con GPUpdate

L'utilità GPUpdate consente di aggiornare le impostazioni di Criteri di gruppo basate su Active Directory. Dopo aver configurato Criteri di gruppo è possibile attendere che le impostazioni vengano applicate ai computer client nel corso dei cicli di aggiornamento standard. Per impostazione predefinita, tali cicli si verificano a intervalli di 90 minuti, con un ritardo o un anticipo casuale di 30 minuti. Questa procedura può contribuire ad accelerare la verifica dell'applicazione dei criteri alle workstation.

Per aggiornare i Criteri di gruppo tra i cicli standard, utilizzare l'utilità GPUpdate come segue:

1.  Nel desktop di Windows XP SP2, fare clic sul pulsante **Start** e scegliere **Esegui**.

2.  Nella casella **Apri** digitare **cmd**, quindi fare clic su **OK**. Verrà visualizza una finestra del prompt dei comandi.

3.  Al prompt dei comandi digitare **GPUpdate**, quindi fare clic su **OK**. Dovrebbe venire visualizzato il messaggio riportato nella schermata seguente:

    [![](images/Cc875819.XPNPT01(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875819.xpnpt01_big(it-it,technet.10).gif)

    Per chiudere il prompt dei comandi, digitare **exit**, quindi premere INVIO.

[](#mainsection)[Inizio pagina](#mainsection)

### Informazioni correlate

Per conoscere le definizioni dei termini correlati alla protezione, consultare la risorsa seguente:

-   [Microsoft Security Glossary](http://www.microsoft.com/security/glossary.mspx), disponibile nel sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35468 (in inglese).

Per ulteriori informazioni sulla protezione della rete Windows XP SP2, fare riferimento alle risorse seguenti:

-   "[Funzionalità modificate in Microsoft Windows XP Service Pack 2: Parte 2: Tecnologie di protezione della rete](http://technet.microsoft.com/en-us/library/bb457156.aspx)" nel sito Web Microsoft TechNet all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/it/maintain/sp2netwk.mspx.

-   "[Using Windows XP Professional with Service Pack 2 in a Managed Environment: Controlling Communication with the Internet](http://technet.microsoft.com/en-us/library/cc507837.aspx)" nel sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35489 (in inglese).

-   [Deploying Windows Firewall Settings for Microsoft Windows XP with Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35303) nell'Area download Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35303 (in inglese).

Per ulteriori informazioni sulla protezione di Windows XP SP2, consultare la risorsa seguente:

-   [*Windows XP Security Guide*](http://go.microsoft.com/fwlink/?linkid=35309), disponibile nell'Area download Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35309 (in inglese).

-   [*Guida per la protezione di Windows XP: Appendice A: Impostazioni principali da considerare*](http://technet.microsoft.com/it-it/library/cc163065) nel sito Web Microsoft TechNet all'indirizzo http://www.microsoft.com/italy/technet/security/prodtech/windowsxp/secwinxp/xpsgapxa.mspx.

Per ulteriori informazioni su Criteri di gruppo, fare riferimento alle risorse seguenti:

-   "[Troubleshooting Group Policy in Microsoft Windows Server](http://go.microsoft.com/fwlink/?linkid=35481)" nell'Area download Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35481 (in inglese).

-   [Enterprise Management with the Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=35479) nel sito Web Microsoft Windows Server all'indirizzo http://go.microsoft.com/fwlink/?linkID=35479 (in inglese).

**Download**

[Download della guida Configurazione delle tecnologie di protezione della rete di Windows XP SP2 in aziende di piccole dimensioni](http://go.microsoft.com/fwlink/?linkid=70393)

[](#mainsection)[Inizio pagina](#mainsection)
