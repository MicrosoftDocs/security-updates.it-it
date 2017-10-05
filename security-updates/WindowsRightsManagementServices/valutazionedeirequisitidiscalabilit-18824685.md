---
TOCTitle: Valutazione dei requisiti di scalabilità
Title: Valutazione dei requisiti di scalabilità
ms:assetid: '89f0138c-946d-47d7-a286-041d4d9606a8'
ms:contentKeyID: 18824685
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747663(v=WS.10)'
---

Valutazione dei requisiti di scalabilità
========================================

Per decidere se distribuire un singolo server o più server, determinare quanti utenti utilizzeranno la distribuzione RMS e quanti file dovranno essere protetti.

Questo fornisce i requisiti medi di utilizzo. Pianificare i requisiti massimi di utilizzo, che probabilmente saranno circa tre volte i requisiti medi.

Considerare anche gli standard aziendali di tolleranza d'errore e di disponibilità del servizio.

Per stabilire una misura di valutazione campione, RMS è stato testato utilizzando un server con due processori Pentium 4 da 2,4 GHz e 1 GB di RAM. In questa configurazione, il server RMS ha consegnato circa 50 licenze al secondo.

Per valutare i requisiti di utilizzo di un sistema RMS, è possibile utilizzare i valori riportati di seguito durante la pianificazione della capacità.

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
<th style="border:1px solid black;" >Transazione</th>
<th style="border:1px solid black;" >Ricorrenza</th>
<th style="border:1px solid black;" >Utilizzo larghezza di banda da client a server (KB)</th>
<th style="border:1px solid black;" >Utilizzo larghezza di banda da server a client (KB)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Richiesta di licenza</td>
<td style="border:1px solid black;">Ripetuta per ogni utente e per ogni parte di contenuto</td>
<td style="border:1px solid black;">64</td>
<td style="border:1px solid black;">18</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificazione account con diritti</td>
<td style="border:1px solid black;">Solo traffico di inizializzazione RMS</td>
<td style="border:1px solid black;">12</td>
<td style="border:1px solid black;">16</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registrazione dei client</td>
<td style="border:1px solid black;">Solo traffico di inizializzazione RMS</td>
<td style="border:1px solid black;">17</td>
<td style="border:1px solid black;">16</td>
</tr>
</tbody>
</table>
  
È inoltre possibile che il traffico di query di Active Directory influisca sulla velocità effettiva della rete. Tuttavia, questo non è di solito un problema se i server RMS sono distribuiti in prossimità dei server di catalogo globale. Vi sarebbe un'eccezione se un malfunzionamento di tutti i server di catalogo globali in un sito causasse un failover su un altro sito su una connessione che non è in grado di supportare la stessa capacità.
  
La seguente tabella fornisce i dati di base sull'utilizzo della banda larga delle transazioni RMS, utilizzarbili per valutare l'effetto del traffico di richieste Active Directory sulla rete dell'organizzazione.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Transazione</th>
<th style="border:1px solid black;" >Uso della banda larga da RMS al catalogo globale (byte)</th>
<th style="border:1px solid black;" >Uso della banda larga dal catalogo globale a RMS (byte)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Istituzione di una connessione RMS (ldap_bind)</td>
<td style="border:1px solid black;">1600</td>
<td style="border:1px solid black;">200</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Valutazione dell'appartenenza al gruppo RMS (ldap_search)</td>
<td style="border:1px solid black;">200</td>
<td style="border:1px solid black;">100</td>
</tr>
</tbody>
</table>
  
Quando si utilizzano queste tabelle di riferimento, assicurarsi di applicare i numeri relativi al contenuto della distribuzione. Ad esempio, se l'utente appartiene a 15 gruppi, sarebbero richiesti 200  byte per la richiesta di ricerca da RMS e 1500  byte (100  byte x 15) per la risposta del catalogo globale.
  
La pianificazione della capacità dovrebbe essere basata sull'anticipazione dei carichi di richieste di licenze per il contenuto, poiché tali carichi rappresentano la maggior parte delle operazioni eseguite da RMS. La velocità di input/output e il rendimento dell'unità disco non sono fattori critici per RMS, poiché le richieste di licenza non fanno uso intensivo di dati e possono basarsi completamente sulle informazioni memorizzate nella cache.
  
L'utilizzo della CPU è la variabile più importante da considerare quando si definisce la velocità effettiva del server, quindi la scelta del processore appropriato è essenziale. I requisiti di memoria sui server RMS aumentano quando il carico sul server aumenta e supera il rendimento massimo del server. Quando si verifica tale problema, le richieste in arrivo vengono accodate da Internet Information Services (IIS) fino a quando il server non sarà in grado di elaborarle. In base al limite della coda configurato in IIS, l'accodamento delle richieste viene interrotto e le richieste vengono respinte quando la coda raggiunge la lunghezza massima specificata.
  
I requisiti di memoria RMS (set di lavoro) per uno schema di carico dovrebbero rientrare completamente nei limiti della dimensione fisica della memoria. La dimensione complessiva della memoria è influenzata principalmente dalle necessità di inserimento nella cache dell'espansione di gruppi. Per ogni server che esegue RMS, è consigliabile almeno 1 GB di RAM.
  
Ogni server RMS è in grado di gestire un numero di richieste client in un dato periodo di tempo (approssimativamente da 30 a 50 licenze al secondo). L'aggiunta lineare di server comporta quindi un aumento della capacità complessiva di emissione di licenze di un cluster e offre inoltre una maggiore affidabilità. È quindi consigliabile regolare l'aggiunta di server in base ai singoli server e al numero di server distribuiti. I seguenti esempi di configurazione mostrano come è possibile utilizzare queste valutazioni per calcolare i requisiti di scala per la distribuzione RMS.
  
-   Configurazione per utilizzo non intensivo  
    Alcune organizzazioni hanno requisiti di utilizzo abbastanza bassi per il supporto di RMS. Ad esempio, un'organizzazione che ha circa 5.000 utenti, con il 10 per cento di utenti che utilizza regolarmente RMS per proteggere il contenuto della posta elettronica, può prevedere che un utente medio protegga 3 messaggi di posta elettronica all'ora. In base a tali requisiti, i server RMS dovrebbero consegnare 1500 licenze all'ora, corrispondenti a 0,42 licenze al secondo. Questi sono i requisiti di utilizzo medio. Se si moltiplica tale valore per 3 si ottiene il valore relativo all'utilizzo massimo, pari a 1,25 licenze al secondo.  
    Questo calcolo indica un utilizzo moderato. Per questa organizzazione sarebbe quindi adatto un singolo server RMS.  
-   Configurazione per utilizzo medio  
    In molte organizzazioni sono disponibili gruppi di utenti abbastanza grandi con requisiti di utilizzo moderati. Ad esempio, un'organizzazione che ha circa 40000 utenti, e 50 per cento degli utenti che utilizza regolarmente RMS per proteggere i contenuti, potrebbe prevedere che un utente medio protegga ogni ora 7 messaggi di posta elettronica e un documento o altro file. In base a questi requisiti, i server RMS dovrebbero consegnare 160000 licenze all'ora, corrispondenti a 44,4 licenze al secondo. Questi sono quindi i requisiti di utilizzo medio. Se si moltiplica tale valore per 3 si ottiene il valore relativo all'utilizzo massimo, pari a 133,3 licenze al secondo.  
    In base a tale calcolo, l'utilizzo previsto è moderatamente elevato e per le esigenze attuali degli utenti saranno sufficienti 3 server RMS, ma per soddisfare le esigenze attuali degli utenti e consentire un'eventuale crescita saranno necessari 6 server RMS.  
-   Configurazione per utilizzo elevato  
    Nelle organizzazioni di grandi dimensioni sono spesso disponibili gruppi molto grandi con requisiti di utilizzo elevati. Ad esempio, un'organizzazione che ha circa 150.000 utenti, e 70 per cento degli utenti che utilizza regolarmente RMS per proteggere i contenuti, potrebbe prevedere che un utente medio protegga ogni ora 15 messaggi di posta elettronica e un documento o altro file. In base a questi requisiti, i server RMS dovrebbero consegnare 1890000 licenze all'ora, corrispondenti a 525 licenze al secondo. Questi sono quindi i requisiti di utilizzo medio. Se si moltiplica tale valore per 3 si ottiene il valore relativo all'utilizzo massimo, pari a 1575 licenze al secondo.  
    In base a tale calcolo, l'utilizzo previsto è estremamente elevato e per le esigenze attuali degli utenti saranno sufficienti 32 server RMS, ma per soddisfare le esigenze attuali degli utenti e consentire un'eventuale crescita saranno necessari 51 server RMS.
  
Se i calcoli effettuati indicano la necessità di emettere un numero di licenze compreso tra le 30 e le 50 licenze al secondo, è solitamente necessario aggiungere un altro server RMS.
