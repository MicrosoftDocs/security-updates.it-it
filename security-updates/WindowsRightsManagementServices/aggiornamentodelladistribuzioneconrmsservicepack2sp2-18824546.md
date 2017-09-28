---
TOCTitle: 'Aggiornamento della distribuzione con RMS Service Pack 2 (SP2)'
Title: 'Aggiornamento della distribuzione con RMS Service Pack 2 (SP2)'
ms:assetid: '27ee06a1-f467-4a6c-b662-45ddb5f8c13e'
ms:contentKeyID: 18824546
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720225(v=WS.10)'
---

Aggiornamento della distribuzione con RMS Service Pack 2 (SP2)
==============================================================

In questa sezione vengono fornite informazioni per l'installazione di Microsoft® Windows® Rights Management Services (RMS) con Service Pack 2 (SP2) in un'organizzazione con una distribuzione di RMS esistente. Solo le organizzazioni che hanno già distribuito RMS devono aggiornare la relativa distribuzione con RMS SP2. Le organizzazioni che distribuiscono RMS per la prima volta possono distribuire RMS con SP2 seguendo le indicazioni riportate nella sezione relativa alla pianificazione di una distribuzione RMS ([http://go.microsoft.com/fwlink/?LinkId=74999](http://go.microsoft.com/fwlink/?linkid=74999)) e nella sezione relativa alla distribuzione di un sistema RMS ([http://go.microsoft.com/fwlink/?LinkID=75000](http://go.microsoft.com/fwlink/?linkid=75000)) in questa documentazione.

È possibile installare RMS con SP2 senza rimuovere l'installazione di RMS con SP1 esistente. Il programma di installazione per RMS con SP2 rileva che RMS con SP1 è installato e aggiunge le funzionalità e le impostazioni necessarie.

| ![](images/Cc720225.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Non è supportato un percorso di aggiornamento dal server RMS senza Service Pack a RMS con SP2. Se si utilizza il server RMS senza Service Pack, è necessario eseguire l'aggiornamento a RMS con SP1 prima di effettuare l'aggiornamento a RMS con SP2. È possibile aggiornare il client RMS da qualsiasi versione precedente del client RMS. |

**In questo argomento**

-   [Preparazione per l'aggiornamento a RMS con SP2](#bkmk_preparingforsp2update)
-   [Esecuzione dell'aggiornamento a RMS con SP2](#bkmk_performingsp2update)
-   [Aggiornamento di cluster](#bkmk_updateclusters)
-   [Aggiornamento dei client RMS](#bkmk_updateclients)
-   [Interoperabilità con RMS versione 1.0](#bkmk_interop)
-   [Rimozione di RMS con SP2](#bkmk_removingrms)

<span id="bkmk_PreparingForSP2Update"></span>
Preparazione per l'aggiornamento a RMS con SP2
----------------------------------------------

L'aggiornamento a RMS con SP2 ha lo scopo di consentire di continuare a eseguire RMS senza interruzione. Tuttavia, prima di aggiornare il cluster RMS, è consigliabile effettuare le seguenti operazioni:

-   Eseguire il backup del database di configurazione e della chiave privata RMS. Per ulteriori informazioni, vedere la sezione relativa ai backup di sistema per RMS ([http://go.microsoft.com/fwlink/?LinkId=75001](http://go.microsoft.com/fwlink/?linkid=75001)) in questa documentazione.
-   Se si utilizza una chiave privata basata su software, assicurarsi di disporre della password per la chiave privata RMS.
-   Eseguire il backup del database di registrazione se si desidera mantenere le statistiche registrate in precedenza.
-   Assicurarsi di disporre degli aggiornamenti critici e degli aggiornamenti della protezione più recenti per il sistema operativo installato nei client e nei server in uso. Per verificare se si dispone di tutti gli aggiornamenti critici e della protezione, fare clic su **Start**, scegliere **Windows Update**, quindi seguire le istruzioni visualizzate.

<span id="bkmk_PerformingSP2Update"></span>
Esecuzione dell'aggiornamento a RMS con SP2
-------------------------------------------

Dopo aver rilevato l'installazione di RMS, l'Installazione guidata di Windows Rights Management Services con Service Pack 2 esamina l'installazione corrente di RMS con SP1 e aggiunge semplicemente nuovi file o sostituisce i file che occorre modificare per RMS con SP2. Se RMS è già installato, dopo aver installato RMS con SP2, non è necessario ripetere il provisioning o eseguire configurazioni aggiuntive per continuare a eseguire RMS.

<span id="bkmk_UpdateClusters"></span>
Aggiornamento di cluster
------------------------

Se si è installato RMS in una configurazione cluster, è consigliabile pianificare l'aggiornamento dei cluster per ridurre al minimo l'impatto dell'aggiornamento sull'installazione. Quando si determina la strategia più appropriata per implementare RMS con SP2 nella propria organizzazione, prendere in considerazione i seguenti suggerimenti:

-   Per rendere più prevedibile l'aggiornamento del cluster e ridurre la possibilità che si verifichi un peggioramento delle prestazioni dei servizi durante l'aggiornamento, è consigliabile installare RMS con SP2 su una porzione di cluster per volta.
-   Se si dispone di più cluster RMS, è opportuno eseguire prima l'aggiornamento dei cluster di certificazione principali e successivamente l'aggiornamento dei cluster licenze registrati in modo subordinato.
-   Se si utilizza l'espansione di gruppi tra insiemi di strutture, è possibile aggiornare i cluster negli insiemi di strutture in modo indipendente, senza influire sulla capacità dei server RMS di espandere l'appartenenza ai gruppi tra gli insiemi di strutture.
-   RMS con SP2, RMS con SP1 e il server RMS versione 1.0 possono coesistere e interoperare solo se risiedono in insiemi di strutture di Active Directory differenti. Non è consigliabile disporre di versioni differenti del server RMS nello stesso cluster.
-   È inoltre possibile utilizzare il pacchetto di installazione di RMS con SP2 per installare una nuova distribuzione di RMS con SP2 su un server; non è necessario che RMS con SP1sia installato.

<span id="bkmk_UpdateClients"></span>
Aggiornamento dei client RMS
----------------------------

In Windows Update e nell'Area download Microsoft è disponibile un nuovo client RMS con SP2. Il pacchetto di installazione del client RMS con SP2 può essere utilizzato anche per installare una nuova versione del client RMS con SP2 in un computer; non è necessario che il client RMS versione 1.0 sia installato. Il client RMS con SP2 include una funzionalità per la compatibilità con le versioni precedenti in modo che possa essere utilizzato con applicazioni abilitate per RMS che richiedono RMS versione 1.0.

Per ulteriori informazioni sull'aggiornamento e sull'installazione del client RMS, vedere la sezione relativa alla distribuzione del client RMS ([http://go.microsoft.com/fwlink/?LinkId=75070](http://go.microsoft.com/fwlink/?linkid=75070)).

<span id="bkmk_InterOp"></span>
Interoperabilità con RMS versione 1.0
-------------------------------------

Poiché RMS con SP2 fornisce numerosi miglioramenti e livelli più elevati di prestazioni, è consigliabile installarlo durante il successivo ciclo di aggiornamento. Sebbene i client e i server RMS che eseguono RMS con SP2 garantiscano un'interoperabilità completa con i client e i server RMS che non eseguono RMS con SP2, tenere presenti le differenze nella modalità di funzionamento di tali server in un ambiente misto descritte di seguito:

-   Solo i server che eseguono RMS con SP1 e versioni successive supportano la registrazione non in linea.
-   Solo i client che eseguono RMS con SP1 e versioni successive sono ad attivazione automatica.
-   Nella seguente tabella vengono illustrate le funzionalità supportate per gli ambienti misti:

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Versione del server RMS</th>
<th>Funzionalità supportate con i client versione 1</th>
<th>Funzionalità supportate con i client SP2</th>
<th>Funzionalità supportate in ambienti client misti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">1.0</td>
<td style="border:1px solid black;">Tutte le funzionalità precedenti.
Registrazione non in linea del server non supportata. Il server deve eseguire la registrazione su Internet.
Nessun client ad attivazione automatica.</td>
<td style="border:1px solid black;">Tutte le funzionalità precedenti.
Registrazione non in linea del server non supportata.
Client ad attivazione automatica.</td>
<td style="border:1px solid black;">Tutte le funzionalità precedenti.
Per la versione SP2, i client sono ad attivazione automatica.
Per la versione 1, i client devono eseguire l'attivazione su Internet.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SP2</td>
<td style="border:1px solid black;">Tutte le funzionalità precedenti.
Registrazione non in linea del server.
Nessun client ad attivazione automatica.</td>
<td style="border:1px solid black;">Tutte le funzionalità SP1.
Registrazione non in linea del server.
Client ad attivazione automatica.
Archivio protetto del server.
Microsoft SQL Server™ 2005 è supportato per impostazione predefinita.</td>
<td style="border:1px solid black;">Tutte le funzionalità precedenti, più le funzionalità SP2.
Registrazione non in linea del server.
Per la versione SP2, i client sono ad attivazione automatica.
Per la versione 1, i client devono eseguire l'attivazione su Internet.</td>
</tr>
</tbody>
</table>
 

<span id="bkmk_RemovingRMS"></span>
Rimozione di RMS con SP2
------------------------

Per ripristinare la configurazione precedente del server RMS dopo aver installato RMS con SP2, è possibile utilizzare **Installazione applicazioni** nel **Pannello di controllo** per rimuovere RMS con SP2.
