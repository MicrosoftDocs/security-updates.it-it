---
TOCTitle: Processo di gestione delle patch
Title: Processo di gestione delle patch
ms:assetid: 'd90522b7-21dd-4183-a81e-cfc05a0315dc'
ms:contentKeyID: 20213218
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700840(v=TechNet.10)'
---

Processo di gestione delle patch
================================

### Fase 3 - Stima e pianificazione

Aggiornato: 1 giugno 2007

##### In questa pagina

[](#ekaa)[Argomenti del modulo](#ekaa)
[](#ejaa)[Obiettivi](#ejaa)
[](#eiaa)[Ambito di applicazione](#eiaa)
[](#ehaa)[Utilizzo del modulo](#ehaa)
[](#egaa)[Panoramica](#egaa)
[](#efaa)[Stabilire la risposta appropriata](#efaa)
[](#eeaa)[Pianificazione del rilascio](#eeaa)
[](#edaa)[Generazione del rilascio](#edaa)
[](#ecaa)[Test di accettabilità](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Passaggio alla fase di distribuzione](#eaaa)

### Argomenti del modulo

In questo modulo viene descritta la terza fase, stima e pianificazione, del processo di gestione in quattro fasi degli aggiornamenti. La fase di stima e pianificazione riguarda la decisione sulla distribuzione di un aggiornamento, su quanto è necessario per la distribuzione e il test dell'aggiornamento software in un ambiente simile a quello di produzione per controllare che non comprometta le applicazioni e i sistemi critici per l'attività dell'azienda.

Lo scopo di questo modulo è descrivere i principi della fase di stima e pianificazione del processo di gestione degli aggiornamenti e introdurre i tipi di attività che consentono di eseguire la stima e la pianificazione con Microsoft Windows Server Update Service (WSUS) e Microsoft Systems Management Server (SMS).

Nota: la versione di valutazione del successivo rilascio di SMS, chiamata System Center Configuration Manager 2007, è ora disponibile per il download all'indirizzo <http://www.microsoft.com/technet/sms/2007/evaluate/download.mspx> (in inglese). Grazie ai notevoli investimenti in semplificazione, configurazione, distribuzione e protezione, Configuration Manager 2007 rende radicalmente più facile la distribuzione dei sistemi, l'automazione delle attività, la gestione della conformità e la gestione della protezione basata su criteri, aumentando l'agilità dell'azienda.

Senza un processo di stima e di pianificazione non si disporrà di una serie chiara di criteri utili per stabilire se distribuire un aggiornamento, non si saprà cosa è necessario per distribuirlo e non si potrà contare su procedure per generare un software di rilascio affidabile e ben collaudato.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Stabilire se la distribuzione di un aggiornamento è effettivamente necessaria.

-   Pianificare il rilascio dell'aggiornamento software.

-   Generare il rilascio.

-   Condurre test di accettazione dell'aggiornamento.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica a tutti i prodotti e a tutte le tecnologie Microsoft.

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo sono descritte le attività di base necessarie per effettuare una stima e una pianificazione utilizzando WSUS e SMS. Informazioni più dettagliate sono fornite nelle Technical Library elencate di seguito.

Per trarre il massimo vantaggio dal modulo:

-   Leggere l'introduzione del modulo sul processo di gestione degli aggiornamenti. Si avrà così una panoramica di tutte e quattro le fasi del processo di gestione degli aggiornamenti e un'introduzione agli strumenti disponibili per supportare la gestione degli aggiornamenti negli ambienti con il sistema operativo Microsoft Windows.

-   Utilizzare le Technical Library WSUS e SMS per altri materiali di riferimento specifici. Queste librerie si trovano all'indirizzo:

    -   [Windows Server Update Services (WSUS) Technical Library (in inglese)](http://technet.microsoft.com/en-us/library/cc706995.aspx)

    -   [http://technet.microsoft.com/en-us/library/cc181833.aspx (in inglese)](http://www.microsoft.com/technet/sms/2003/library/default.mspx)

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

La stima e pianificazione è la terza fase del processo di gestione degli aggiornamenti illustrato nella Figura 1.

![](images/Cc700840.secmod196figure1-0(it-it,TechNet.10).gif)

**Figura 1. Il processo di gestione degli aggiornamenti**

In questa fase viene valutato l'aggiornamento software e se ne pianifica la distribuzione nell'ambiente di produzione, presumendo che sia stata approvata.

La prima azione della fase di stima e pianificazione riguarda una richiesta di modifica (RFC, Request For Change) per un aggiornamento software identificato come pertinente per l'ambiente di produzione.

Entro la fine della fase di stima e pianificazione, si sarà dovuto stabilire se la richiesta di modifica deve essere classificata come un'emergenza, si sarà dovuto provvedere a esaminare e approvare la richiesta e si sarà dovuto stabilire le attività richieste per la distribuzione delle modifiche approvate nella produzione. Inoltre sarà necessario aver eseguito il test dell'aggiornamento software in un ambiente simile a quello di produzione per controllare che non comprometta le applicazioni e i sistemi critici per l'attività dell'azienda.

Questo modulo è dedicato ai requisiti per la stima e la pianificazione:

-   Stabilire la risposta appropriata.

-   Pianificare il rilascio dell'aggiornamento software.

-   Generare il rilascio.

-   Condurre test di accettazione dell'aggiornamento.

[](#mainsection)[Inizio pagina](#mainsection)

### Stabilire la risposta appropriata

L'RFC stabilisce il tipo di modifica richiesto nell'ambiente di produzione, ad esempio la distribuzione di un aggiornamento software, l'applicazione di contromisure per attenuare la vulnerabilità o entrambe le cose, e descrive la modifica richiesta per permettere che altri agiscano di conseguenza.

Il primo passaggio della fase di stima e pianificazione consiste nell'esaminare l'RFC e nel decidere quale sia la risposta più appropriata a una vulnerabilità software o a un pericolo. Azioni richieste:

-   Definizione della priorità e classificazione della richiesta.

-   Ottenimento dell'autorizzazione per la distribuzione dell'aggiornamento software.

#### Definizione della priorità e classificazione di una richiesta di aggiornamento software

Prima di poter autorizzare una richiesta di aggiornamento software, è necessario stabilirne la priorità e la categoria. Anche se priorità e categoria vengono inizialmente assegnate da colui che ha dato inizio alla modifica e sono incluse nell'RFC, perché sia possibile autorizzare la richiesta di modifica è prima necessario esaminare queste assegnazioni e confermarle o modificarle.

##### Assegnazione della priorità a un aggiornamento software

Il livello di priorità è particolarmente importante perché stabilisce la rapidità del processo di modifica di un aggiornamento software. Le seguenti considerazioni possono aiutare a stabilire il livello di priorità di un aggiornamento software:

-   Quali sono le risorse aziendali critiche? Saranno esposte a una potenziale violazione della protezione o instabilità del sistema fino all'installazione dell'aggiornamento software? L'assegnazione della priorità alle richieste di modifica deve basarsi sull'impatto dell'aggiornamento o del mancato aggiornamento di risorse ad alto valore.

-   L'aggiornamento software si applicherà a un sistema con un servizio vitale per l'attività dell'azienda, quale un'applicazione line-of-business (LOB), che è stato oggetto di attacchi in passato? Questa potrebbe essere una valida ragione per aumentare la priorità di una richiesta di modifica.

-   Sono state applicate le contromisure che dovrebbero ridurre al minimo l'esposizione di una particolare vulnerabilità della protezione? Queste misure potrebbero diminuire la priorità della richiesta di modifica, anche se potrebbe essere comunque appropriato distribuire l'aggiornamento software per eliminare la vulnerabilità.

-   Quale pericolo comporta per l'ambiente di produzione la vulnerabilità in questione? Molti bollettini sulla sicurezza e relativi aggiornamenti software potrebbero applicarsi solo a pochi computer dell'ambiente. Se il pericolo della vulnerabilità è basso, questo potrebbe abbassare la priorità della richiesta.

Le seguenti tabelle possono aiutare a valutare la priorità della richiesta in relazione ad altre richieste. Nella Tabella 1, i livelli di priorità sono correlati a intervalli di tempo consigliati e a intervalli di tempo minimi consigliati.

**Tabella 1: Priorità dell'aggiornamento e intervalli di tempo di distribuzione consigliati**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Priorità</p></th>
<th><p>Intervallo di tempo consigliato</p></th>
<th><p>Intervallo di tempo minimo consigliato</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Emergenza</p></td>
<td style="border:1px solid black;"><p>Entro 24 ore</p></td>
<td style="border:1px solid black;"><p>Entro due settimane</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elevata</p></td>
<td style="border:1px solid black;"><p>Entro un mese</p></td>
<td style="border:1px solid black;"><p>Entro due mesi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>A seconda della disponibilità, distribuire un nuovo service pack o un rollup di aggiornamento che includa la correzione di questa vulnerabilità entro quattro mesi.</p></td>
<td style="border:1px solid black;"><p>Distribuire l'aggiornamento software entro sei mesi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Bassa</p></td>
<td style="border:1px solid black;"><p>A seconda della disponibilità, distribuire un nuovo service pack o un rollup di aggiornamento che includa la correzione di questa vulnerabilità entro 1 anno.</p></td>
<td style="border:1px solid black;"><p>Distribuire l'aggiornamento software entro 1 anno oppure scegliere di non procedere alla distribuzione.</p></td>
</tr>  
</tbody>  
</table>
  
Nella Tabella 2 sono riportati degli esempi di fattori che potrebbero innalzare o abbassare il livello di priorità.
  
**Tabella 2: Fattori che influenzano le priorità di aggiornamento**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Fattore ambientale/organizzativo</p></th>  
<th><p>Correzione della priorità</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Impatto su risorse di alto valore o alta esposizione.</p></td>
<td style="border:1px solid black;"><p>Innalzare</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Risorse storicamente prese di mira dai pirati informatici.</p></td>
<td style="border:1px solid black;"><p>Innalzare</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Esistono fattori di attenuazione, quali contromisure che riducono al minimo il pericolo.</p></td>
<td style="border:1px solid black;"><p>Abbassare</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Impatto su risorse di poco valore o scarsa esposizione.</p></td>
<td style="border:1px solid black;"><p>Abbassare</p></td>
</tr>  
</tbody>  
</table>
  
**Richiesta di modifica di emergenza**
  
Se la vulnerabilità risolta dall'aggiornamento per la protezione viene già sfruttata o sta per esserlo, o se l'aggiornamento corregge un'instabilità del sistema riscontrata nell'ambiente di produzione, potrebbe essere necessario classificare la richiesta come "emergenza", assegnandole la priorità su tutte le altre modifiche che hanno luogo all'interno dell'ambiente di produzione.
  
##### Classificazione di un aggiornamento software
  
La categoria di un aggiornamento software è importante, perché aiuta chi si occupa dell'esame della modifica a capire l'impatto che avrà sui sistemi e sui servizi all'interno dell'ambiente di produzione. Per stabilire la categoria (o l'impatto) della richiesta di modifica, è necessario individuare:
  
-   Su quali macchine deve essere installato l'aggiornamento software e i ruoli che esse svolgono (criticità per l'azienda).
  
    Un aggiornamento software che richiede il riavvio di un computer critico per l'attività dell'azienda, ad esempio, avrà un impatto maggiore di uno che non richiede il riavvio.
  
-   Se saranno necessarie ulteriori modifiche per supportare la distribuzione dell'aggiornamento software.
  
    Se, ad esempio, l'aggiornamento software si applica solo al service pack corrente e quest'ultimo non è installato in certi sistemi di produzione, potrebbe non essere possibile proteggere quei sistemi da una particolare vulnerabilità della protezione. In questo caso, l'impatto e di conseguenza la categoria della richiesta di modifica sarebbero maggiori, in quanto sia il service pack che l'aggiornamento software dovrebbero essere distribuiti.
  
-   Se l'aggiornamento software può essere disinstallato, dopo essere stato installato.
  
    In caso negativo, presenta un rischio maggiore per l'ambiente di produzione rispetto a uno che può essere disinstallato senza problemi. Anche se potrebbe essere necessario distribuire questi aggiornamenti software per fornire una protezione da una particolare vulnerabilità o per risolvere una particolare instabilità del sistema, la categoria della richiesta deve riflettere questa eventualità.
  
-   L'impatto probabile sull'infrastruttura di rete.
  
    La distribuzione di un aggiornamento software di grandi dimensioni in molti computer contemporaneamente potrebbe deteriorare le prestazioni della rete e influire negativamente sul corretto funzionamento dell'intero ambiente. Esaminare attentamente tutta la documentazione sull'aggiornamento software ed essere sempre al corrente della dimensione dell'aggiornamento e del numero di computer che saranno interessati. Queste informazioni possono essere utili per pianificare correttamente il rilascio.
  
-   Se, durante l'installazione, è necessario interrompere, sospendere o chiudere determinati servizi.
  
    Questo potrebbe influire sui servizi critici di un'organizzazione o impedire a un utente finale di lavorare al computer mentre è in corso l'installazione.
  
Ulteriori informazioni sull'impostazione della priorità e della categoria di una richiesta di modifica sono reperibili nella funzione di gestione del servizio (SMF, Service Management Function) Gestione dei cambiamenti all'indirizzo <http://technet.microsoft.com/en-us/library/cc543211.aspx> (in inglese).
  
#### Ottenimento dell'autorizzazione per la distribuzione dell'aggiornamento software
  
Una volta stabilite la priorità e la categoria di una richiesta di modifica, è necessario esaminare la richiesta e autorizzarla prima della distribuzione del software di aggiornamento nella produzione. Per ottenere l'autorizzazione per la richiesta di modifica, è necessario:
  
-   Stabilire chi deve essere coinvolto nel processo decisionale.
  
-   Esaminare la richiesta di modifica, valutare i rischi e le conseguenze della distribuzione dell'aggiornamento software e scegliere l'azione più appropriata.
  
-   Identificare chi sarà responsabile della distribuzione dell'aggiornamento software su tutti i sistemi interessati.
  
##### Decisione sulle persone da coinvolgere
  
È importante stabilire chi coinvolgere nell'esame e nell'autorizzazione dell'aggiornamento software per la distribuzione nella produzione. In caso di aggiornamenti non di emergenza, l'esame e l'autorizzazione devono essere a carico di un consiglio consultivo per le modifiche (CAB, Change Advisory Board), composto dai rappresentanti di tutte le aree dell'azienda interessate.
  
Del CAB devono far parte persone con esperienza nelle tecnologie e nei servizi specifici che verranno utilizzati per la distribuzione dell'aggiornamento. Nel gruppo devono essere inclusi anche rappresentanti dell'azienda, della rete, della protezione, del servizio di assistenza e dei team del supporto tecnico.
  
Ulteriori informazioni sui CAB e sulla loro formazione sono reperibili nella SMF Gestione dei cambiamenti, che può essere scaricata da <http://technet.microsoft.com/en-us/library/cc543211.aspx> (in inglese).
  
**Richiesta di modifica di emergenza**
  
Quando è necessaria una decisione rapida su una richiesta critica, mirata a risolvere una vulnerabilità della protezione o a evitare un errore di sistema critico, l'autorizzazione deve essere presa dal comitato di emergenza del CAB (CAB/EC).
  
Un CAB/EC deve essere composto da persone che possiedono l'autorità per approvare le modifiche di emergenza e che saranno anche disponibili per prendere decisioni rapide. Ulteriori informazioni sui CAB/EC sono reperibili nella SMF Gestione dei cambiamenti, che può essere scaricata da: <http://technet.microsoft.com/en-us/library/cc543211.aspx>.
  
##### Esame della richiesta di modifica
  
Una volta individuate le persone appropriate, è opportuno valutare i rischi e l'impatto dell'aggiornamento software sull'ambiente di produzione e stabilire se distribuirlo. Nel prendere questa decisione, è necessario considerare quanto segue:
  
-   Cos'altro sta accadendo nell'ambiente di produzione?
  
-   Qual è l'impatto dell'applicazione o della non applicazione dell'aggiornamento software?
  
-   Quali sono i costi previsti della distribuzione o della non distribuzione dell'aggiornamento software?
  
-   Quali azioni devono essere intraprese, eventualmente, per attenuare l'esposizione a una vulnerabilità della protezione o instabilità del sistema, durante la distribuzione dell'aggiornamento software?
  
-   Qual è l'impatto dei tempi di inattività dei computer? Sarà necessario confrontare e considerare i rischi del differimento della distribuzione di un aggiornamento software con i rischi nei quali si incorre causando l'inattività dei computer quando si distribuisce un aggiornamento software nell'ambiente.
  
-   Quale sarà il meccanismo migliore e più efficiente per la distribuzione dell'aggiornamento software?
  
-   L'aggiornamento software comporta altri problemi conosciuti o effetti collaterali o richiede il riavvio del sistema?
  
-   Le risorse disponibili sono sufficienti per distribuire l'aggiornamento software o affrontare qualsiasi altro problema riscontrato durante la distribuzione?
  
-   In che modo verranno risolte le dipendenze o i prerequisiti da rispettare prima della distribuzione dell'aggiornamento software?
  
Anche se la risposta migliore a una vulnerabilità software consiste nel distribuire l'aggiornamento software che risolve il problema, a volte potrebbe essere preferibile distribuire una contromisura a breve termine, ad esempio chiudere le porte di rete o l'accesso esterno ai sistemi, durante la distribuzione dell'aggiornamento software ai sistemi all'interno dell'ambiente di produzione. L'applicazione di contromisure può avere diversi benefici:
  
-   La maggior parte degli aggiornamenti software richiede il riavvio dei computer di destinazione prima del completamento dell'installazione e prima che il computer possa essere considerato protetto. Se non è possibile distribuire immediatamente un aggiornamento software nell'ambiente perché i riavvii dei computer sono limitati a specifici intervalli di manutenzione, l'implementazione delle contromisure consigliate può proteggere in maniera efficace i computer fino alla distribuzione dell'aggiornamento software. In alternativa, talvolta è possibile distribuire aggiornamenti della protezione ed eliminare il riavvio automatico. In questo caso, l'aggiornamento per la protezione potrebbe essere installato durante le ore normali e i computer potrebbero essere riavviati in un orario compatibile con l'intervallo di manutenzione.
  
-   Le contromisure possono avere un rischio inferiore e possono essere applicate più rapidamente e con un minor numero di test rispetto all'aggiornamento software. Potrebbe essere, ad esempio, molto più semplice disattivare le porte di rete oppure chiudere i servizi o i sistemi esposti a una particolare vulnerabilità della protezione e applicare l'aggiornamento software in seguito.
  
L'implementazione di contromisure di rafforzamento dei computer spesso può proteggerli da molte vulnerabilità comuni. Il blocco di certe porte di rete e la disattivazione dei servizi inutilizzati sono solo due delle contromisure che, quando implementate, possono proteggere in maniera efficiente i computer.
  
Per ulteriori informazioni sulle contromisure di rafforzamento dei computer, vedere la guida "Threats and Countermeasures" (in inglese) all'indirizzo <http://www.microsoft.com/downloads/details.aspx?displaylang=en&familyid=1b6acf93-147a-4481-9346-f93a4081eea8>
  
**Nota:** anche se vengono distribuite delle contromisure per ridurre l'esposizione a una vulnerabilità della protezione, è comunque sempre opportuno pianificare la distribuzione dell'aggiornamento della protezione.
  
Se, ad esempio, i sistemi rimangono non aggiornati e in rete viene introdotto un computer infettato da un worm o da un virus, l'infezione si diffonderà rapidamente a tutti i sistemi non protetti. La distribuzione delle contromisure dovrebbe semplicemente abbassare la priorità della richiesta di modifica, non rimuovere la richiesta di aggiornamento software.
  
##### Decisione sulla scelta del responsabile della distribuzione dell'aggiornamento software
  
Una volta raggiunto l'accordo sulla distribuzione dell'aggiornamento software e sull'utilizzo delle contromisure (se appropriate), è necessario scegliere su chi ricadrà la responsabilità dell'attuazione di queste modifiche. Il responsabile dovrà:
  
-   Sviluppare un piano per effettuare le modifiche richieste.
  
-   Stabilire e ottenere le risorse richieste.
  
-   Provvedere allo sviluppo degli script, degli strumenti e della documentazione necessari per la distribuzione delle modifiche.
  
-   Accertarsi che vengano condotti i test adeguati.
  
-   Controllare che le modifiche siano distribuite nella produzione.
  
-   Valutare il successo o il fallimento della distribuzione.
  
Senza la nomina di un responsabile che presieda alle attività summenzionate, esiste il rischio che l'aggiornamento software non venga distribuito. Il responsabile designato in genere ricopre il ruolo di Release Manager, a cui si fa riferimento nella SMF Gestione del rilascio all'indirizzo: <http://technet.microsoft.com/en-us/library/cc543211.aspx>.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Pianificazione del rilascio
  
Con pianificazione del rilascio si intende il processo di definizione della modalità di rilascio dell'aggiornamento software nell'ambiente di produzione.
  
La pianificazione del rilascio di un nuovo aggiornamento software è fondamentalmente articolata in tre fasi:
  
-   Individuazione delle risorse da aggiornare.
  
-   Identificazione dei problemi e dei vincoli principali.
  
-   Generazione del piano di rilascio.
  
#### Individuazione delle risorse da aggiornare
  
Per individuare le risorse da aggiornare è necessaria una conoscenza accurata e aggiornata delle risorse presenti nell'ambiente.
  
In un ambiente WSUS, gli amministratori potrebbero dover effettuare un'altra analisi utilizzando Microsoft Baseline Security Analyzer (MBSA) per stabilire quali sono i sistemi che richiedono l'aggiornamento software. Se SMS è distribuito, le informazioni recuperate dagli strumenti di inventario e dagli agenti client possono essere utilizzate per individuare le macchine in cui installare l'aggiornamento.
  
Per ulteriori informazioni su questi strumenti, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) e [http://technet.microsoft.com/en-us/library/cc181833.aspx](http://www.microsoft.com/technet/sms/2003/library/default.mspx) (in inglese).
  
#### Identificazione dei problemi e dei vincoli principali
  
Potrebbero esservi numerosi problemi e vincoli che impongono i passaggi necessari per distribuire pienamente l'aggiornamento software nella produzione. Ad esempio, il responsabile della distribuzione dell'aggiornamento software dovrà considerare quanto segue:
  
-   Quanto tempo concedere agli utenti prima che l'aggiornamento software venga installato automaticamente? Il tempo concesso dipenderà da numerosi fattori, inclusi i ruoli e le responsabilità degli utenti e la natura dell'instabilità del sistema o della vulnerabilità della protezione che l'aggiornamento software è destinato a risolvere.
  
-   Nella Figura 2 è riportato un esempio di tempi di distribuzione di un aggiornamento software (un contratto di servizio SLA, Service Level Agreement) che indica che i server devono essere aggiornati entro sette giorni dall'arrivo di un aggiornamento software che non viene considerato critico per l'attività dell'azienda. Gli amministratori sono autorizzati ad avviare l'aggiornamento entro sette giorni, ma devono essere consapevoli che i computer verranno forzatamente aggiornati o disconnessi dalla rete alla scadenza di questo intervallo di tempo.
  
    [![](images/Cc700840.secmod196figure2-0(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700840.secmod196figure2-0_big(it-it,technet.10).gif)
  
    **Figura 2. Esempio di SLA di distribuzione degli aggiornamenti per i server**
  
Un intervallo analogo può essere applicato alle workstation dell'ambiente, anche se i tempi di risposta e le azioni specifiche varieranno.
  
-   Alcuni aggiornamenti software richiedono diritti amministrativi sul computer nel quale vengono installati. La maggior parte degli utenti finali non disporrà di diritti amministrativi locali, pertanto lo strumento utilizzato per installare l'aggiornamento software dovrà poter acquisire diritti e privilegi elevati per l'installazione dell'aggiornamento software nei computer client.
  
-   Se l'installazione dell'aggiornamento software richiede una certa quantità di spazio sul disco o se l'aggiornamento deve essere messo nella cache prima dell'installazione, è necessario controllare la quantità di spazio disponibile in ogni computer client.
  
-   Se l'aggiornamento software è di grandi dimensioni, ad esempio di diversi megabyte, il download sui client mobili potrebbe richiedere un po' di tempo. Se l'aggiornamento software non è classificato come emergenza, potrebbe essere appropriato differire l'installazione nei client finché non sono fisicamente connessi alla rete.
  
-   I computer critici per l'attività dell'azienda potrebbero essere vincolati a orari specifici per il riavvio o le modifiche (intervalli di interruzione). La distribuzione di un aggiornamento software e qualsiasi riavvio del sistema richiesti dovranno essere pianificati in modo da aver luogo entro questi intervalli di interruzione.
  
-   Se i computer client sono bloccati per l'utilizzo di certe impostazioni di Criteri di gruppo, l'installazione dell'aggiornamento software potrebbe non avvenire correttamente.
  
-   Se il prodotto da aggiornare è stato distribuito tramite Windows Installer, l'applicazione potrebbe richiedere l'accesso ai file di installazione originali. In caso di installazione automatica dell'aggiornamento software, i file devono trovarsi nello stesso percorso in cui si trovavano quando è stato originariamente installato il prodotto. Se il prodotto è stato originariamente installato da un supporto fisico, ad esempio un'unità CD, Windows Installer cercherà di trovare i file originali nel CD inserito correntemente.
  
-   Se per l'installazione originale di un prodotto Microsoft Office è stata utilizzata un'immagine amministrativa, ad esempio, sarà necessario eseguire un'installazione amministrativa dell'aggiornamento software nell'immagine, piuttosto che applicarla direttamente al client. Ulteriori informazioni sui problemi riguardanti l'aggiornamento di un'immagine amministrativa sono reperibili all'indirizzo [/technet/prodtechnol/sms/sms2/depopt/smsoffxp.mspx](http://www.microsoft.com/technet/prodtechnol/sms/sms2/depopt/smsoffxp.mspx) (in inglese).
  
-   Se esistono delle applicazioni che sono state installate in base all'utente e non in base al computer per tutti gli utenti, è necessario reinstallarle in base al computer, quindi applicare l'aggiornamento software alla nuova installazione.
  
Se si utilizza SUS e si desidera evitare la distribuzione al di fuori degli intervalli di interruzione, sarà necessario utilizzare oggetti Criteri di gruppo (GPO, Group Policy Objects) per specificare che gli aggiornamenti devono essere scaricati ma non installati. Una volta a conoscenza che un aggiornamento è stato scaricato, è opportuno accedere a ogni server critico per l'attività dell'azienda e avviare l'installazione entro l'intervallo di interruzione consentito. Nel caso delle workstation, esiste anche un'impostazione GPO per accertarsi che i computer che hanno perso un'installazione pianificata (ad esempio perché il computer client era spento) la ripianifichino automaticamente per quando verrà avviato il servizio Aggiornamenti automatici. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di stima e pianificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx), mentre per informazioni su come utilizzare SMS per pianificare la distribuzione, vedere [http://technet.microsoft.com/en-us/library/cc181833.aspx](http://www.microsoft.com/technet/sms/2003/library/default.mspx) (in inglese).
  
##### Richiesta di modifica di emergenza
  
Se si ha una richiesta di modifica che indica che l'aggiornamento software è un'emergenza, tenere in considerazione i seguenti fattori:
  
-   Potrebbe essere richiesta la distribuzione dell'aggiornamento software in un lasso di tempo molto inferiore al normale. Potrebbe essere prevista, ad esempio, una distribuzione completa entro 24 ore dall'approvazione della richiesta di modifica.
  
    Nella Figura 3 è riportato uno SLA relativo ai tempi di distribuzione di un aggiornamento software. I tempi indicano che tutti i server devono essere aggiornati entro otto ore dall'arrivo della notifica di un aggiornamento software critico.
  
    [![](images/Cc700840.secmod196figure3-0(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700840.secmod196figure3-0_big(it-it,technet.10).gif)
  
    **Figura 3. Esempio di SLA di distribuzione di emergenza entro otto ore**
  
    Nell'esempio precedente, una volta che l'organizzazione è stata messa al corrente dell'aggiornamento software, l'aggiornamento dei server critici per l'attività dell'azienda deve iniziare entro due ore (le 12:00, come indicato) e il 98 percento di tutti i server deve risultare conforme entro le 18:00. I server restanti devono risultare conformi entro le 22:00; in caso contrario vengono disconnessi dalla rete. Tempi di conformità simili devono essere applicati per le workstation presenti nell'ambiente, anche se l'intervallo di tempo e la velocità di risposta possono variare a seconda dell'organizzazione.
  
-   Gli intervalli di interruzione dai quali dipende il momento di aggiornamento o riavvio di certi sistemi critici per l'attività dell'azienda dovranno essere ignorati per permettere la distribuzione dell'aggiornamento software entro il lasso di tempo concordato.
  
-   Sarà necessario applicare l'aggiornamento software a tutti i sistemi interessati, a prescindere dalla loro connessione alla rete.
  
Se si utilizza WSUS, è possibile utilizzare i Criteri di gruppo per forzare i client a installare un aggiornamento software prima dell'intervallo di manutenzione regolarmente pianificato. Prima, sarà anche necessario accertarsi che venga forzata la replica su qualsiasi server figlio WSUS, normalmente pianificata per sincronizzare gli aggiornamenti nei tempi di scarso traffico di rete, utilizzando l'opzione Synchronize Now nella pagina relativa all'amministrazione server di WSUS. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di stima e pianificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).
  
In un ambiente SMS, è necessario configurare i mittenti tra i siti SMS per permettere la replica delle transazioni di annuncio/pacchetto ad alta priorità in tutte le ore del giorno. È importante che l'impostazione di priorità elevata sia utilizzata solo per i pacchetti e gli annunci relativi all'aggiornamento software. Per ulteriori informazioni sull'uso di SMS nella fase di stima e pianificazione, vedere [http://technet.microsoft.com/en-us/library/cc181833.aspx](http://www.microsoft.com/technet/sms/2003/library/default.mspx) (in inglese).
  
#### Generazione di un piano di rilascio
  
A questo punto è necessario pianificare e definire l'ordine in cui effettuare la distribuzione dell'aggiornamento software nei computer dell'ambiente di produzione. Qui di seguito sono elencati alcuni punti da tenere in considerazione nella fase di generazione di un piano di rilascio:
  
-   Se l'aggiornamento software si applica a tutti i server all'interno dell'ambiente di produzione, è opportuno aggiornare per primi quelli con SMS, WSUS o con gli strumenti di controllo?
  
    L'aggiornamento dell'infrastruttura di gestione, come prima operazione, assicura che gli amministratori possano utilizzare questi servizi per monitorare l'andamento della distribuzione.
  
-   Esistono delle ragioni commerciali per aggiornare una parte dell'ambiente di produzione prima di un'altra?
  
    Potrebbero esservi dei buoni motivi per applicare l'aggiornamento software ai computer a rischio di vulnerabilità della protezione o di una potenziale instabilità del sistema e successivamente continuare la distribuzione sugli altri.
  
-   Qual è l'impatto della larghezza di banda di rete disponibile tra i siti sull'ordine di distribuzione?
  
    Limitazioni della larghezza di banda della rete potrebbero rendere difficile distribuire l'aggiornamento software con la stessa rapidità in tutti i siti. L'aggiornamento software può essere distribuito più rapidamente nei siti con una buona connettività di rete, rispetto a quelli con una disponibilità di rete limitata.
  
Infine, è necessario stabilire come e quando comunicare agli utenti, all'azienda e al servizio di assistenza le informazioni sull'aggiornamento software, la sua gravità, il suo impatto e i passaggi richiesti per la distribuzione.
  
##### Richiesta di modifica di emergenza
  
Nel caso in cui la richiesta di modifica sia un'emergenza, è necessario considerare quanto segue:
  
-   Se è necessario aggiornare anche i componenti dell'architettura di gestione, ad esempio i server del sito WSUS e SMS 2003 e Microsoft Operations Manager (MOM), potrebbe essere opportuno pianificare per questi computer un aggiornamento manuale a cura degli amministratori locali per assicurare che questi server non vengano riavviati durante la distribuzione dell'aggiornamento software agli altri computer all'interno dell'ambiente di produzione.
  
-   Se un sito o un gruppo di computer è già stato colpito da una violazione della protezione o dall'instabilità del sistema risolta dall'aggiornamento software, l'aggiornamento dovrebbe essere applicato per primo a questi computer (ad esempio, rimozione virus, ecc..).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Generazione del rilascio
  
Una volta in atto un piano di rilascio, il passaggio successivo del processo consiste nello sviluppo degli script, degli strumenti e delle procedure che gli amministratori utilizzeranno per distribuire l'aggiornamento software nell'ambiente di produzione. Le attività da svolgere in questa fase dipenderanno essenzialmente dalla possibilità di distribuire l'aggiornamento software utilizzando WSUS o SMS 2003.
  
Se si utilizza WSUS, tenere presente che gli aggiornamenti vengono scaricati direttamente dai server Microsoft Update pubblici e che sono già disponibili in pacchetto in un formato eseguibile (exe), pertanto non sono necessarie ulteriori azioni per riassemblarli in pacchetto per la distribuzione. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di stima e pianificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).
  
Se si utilizza SMS, la generazione del rilascio è più semplice se l'aggiornamento può essere distribuito utilizzando Distribute Software Updates Wizard di SMS 2003. Tramite questa procedura guidata è possibile creare automaticamente il pacchetto SMS e il programma richiesto per distribuire e installare l'aggiornamento software. Tutti gli aggiornamenti per la protezione che si applicano a una specifica combinazione di prodotto e service pack possono essere combinati in un pacchetto di rollup di protezione, il che semplifica la gestione e l'amministrazione e riduce significativamente il numero di riavvii dei computer richiesti. Se gli aggiornamenti non possono essere distribuiti utilizzando Distribute Software Updates Wizard di SMS 2003, è necessario utilizzare procedure di distribuzione del software standard di SMS per creare un pacchetto e un annuncio, specificare il file batch, il file Microsoft Installer (MSI) o un eseguibile che verrà eseguito nel computer client e, se l'aggiornamento non è fornito con un eseguibile del programma di installazione, sarà anche necessario generare un eseguibile tramite gli strumenti di creazione MSI. Per ulteriori informazioni sull'uso di SMS nella fase di stima e pianificazione, vedere [http://technet.microsoft.com/en-us/library/cc181833.aspx](http://www.microsoft.com/technet/sms/2003/library/default.mspx) (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Test di accettabilità
  
Fino a questo punto della procedura, i test avevano lo scopo di controllare il corretto funzionamento dell'aggiornamento software e del pacchetto di rilascio all'interno di un ambiente di sviluppo.
  
I test di accettazione permettono agli sviluppatori e ai rappresentanti delle aziende di controllare che gli aggiornamenti funzionino in un ambiente che riflette molto da vicino la produzione e che i sistemi critici per l'attività dell'azienda continuino a venir eseguiti correttamente dopo la distribuzione dell'aggiornamento software. Gli amministratori e i rappresentanti delle aziende devono definire una serie di test da eseguire nel caso in cui un aggiornamento software sia considerato critico per l'azienda e una serie più dettagliata di test da utilizzare nel caso in cui l'aggiornamento abbia una priorità più bassa.
  
Tuttavia, a prescindere dal livello di criticità dell'aggiornamento software, è sempre opportuno effettuare una serie minima di test per controllare che:
  
-   Una volta terminata l'installazione, il computer si riavvii correttamente.
  
-   L'aggiornamento software, se è rivolto a computer connessi tramite connessioni di rete lente o non affidabili, possa essere scaricato attraverso questi collegamenti e, al termine, possa venire installato correttamente.
  
-   L'aggiornamento software sia fornito con una routine di disinstallazione che può essere utilizzata per rimuoverlo correttamente.
  
-   I servizi e i sistemi critici per l'attività dell'azienda continuino a essere eseguiti dopo l'installazione dell'aggiornamento software.
  
Prima di distribuire l'aggiornamento software nella produzione, è importante raccogliere le informazioni sui passaggi, le procedure e gli strumenti di risoluzione dei problemi utilizzati durante i test e metterli a disposizione del personale dell'assistenza e del team delle operazioni.
  
I test dovrebbero condurre alla creazione di:
  
-   Articoli interni di Knowledge Base, in cui vengono descritti i passaggi standard di individuazione dei problemi e le relative soluzioni.
  
-   Un elenco di contatti e un percorso di escalation.
  
-   Script, regole e informazioni (quali contatori, eventi e limiti) che permettano al personale delle operazioni di monitorare in maniera efficiente il rilascio nella produzione.
  
A prescindere dal numero di test effettuati, la distribuzione di un aggiornamento software nella produzione spesso ha effetti che non possono mai essere previsti o replicati in un ambiente di laboratorio. Per evitare impatti potenzialmente negativi su un gran numero di computer client, prima della distribuzione all'intera organizzazione gli amministratori dovrebbero valutare la distribuzione dell'aggiornamento software a un piccolo numero di computer campione e controllare che i sistemi e le applicazioni critiche per l'attività dell'azienda continuino a venire eseguiti correttamente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Qui di seguito sono riportati i punti chiave da ricordare in merito alla fase di stima e pianificazione:
  
-   È necessario un processo formale per stabilire se è opportuno, per l'azienda, distribuire l'aggiornamento software.
  
-   È necessario nominare un responsabile che si faccia carico della distribuzione.
  
-   Quando si ha un aggiornamento software approvato, è necessario pianificarne la modalità di distribuzione nella produzione.
  
-   È necessario testare il pacchetto in laboratorio e, se opportuno, condurre dei test pilota in un ambiente di produzione per accertarsi che non comprometta le applicazioni LOB.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Passaggio alla fase di distribuzione
  
È possibile passare alla fase di distribuzione del processo di gestione degli aggiornamenti quando:
  
-   Il pacchetto è pronto per la distribuzione nella produzione.
  
-   Si è ricevuta l'approvazione per la distribuzione dell'aggiornamento software nell'ambiente di produzione. Per informazioni più dettagliate sulla fase di distribuzione, vedere il modulo "[Fase 4 del processo di gestione degli aggiornamenti - Distribuzione](http://technet.microsoft.com/it-it/library/cc700833.aspx)".
  
[](#mainsection)[Inizio pagina](#mainsection)
