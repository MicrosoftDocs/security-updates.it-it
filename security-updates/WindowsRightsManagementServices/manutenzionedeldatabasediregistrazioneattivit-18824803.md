---
TOCTitle: Manutenzione del database di registrazione attività
Title: Manutenzione del database di registrazione attività
ms:assetid: 'de55058b-0d1a-4997-8a45-e14678ddd13f'
ms:contentKeyID: 18824803
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747691(v=WS.10)'
---

Manutenzione del database di registrazione attività
===================================================

Le voci di registrazione attività includono anche copie delle licenze di pubblicazione emesse per diverse operazioni RMS, come la registrazione degli utenti e l'assegnazione di licenze d'uso. Nello scenario peggiore, in cui ogni voce di registrazione attività è una registrazione utente avvenuta con successo o un tentativo avvenuto con successo di acquisire una licenza d'uso, ogni voce di registrazione attività aggiungerà circa 200 KB alla dimensione del database di registrazione attività.

Ad esempio, si presuma che sia stato inviato un messaggio di posta elettronica protetto con RMS a tutti i dipendenti di una società che ha 50000 utenti e che ogni dipendente lo apra. Se ogni dipendente avesse aperto questo messaggio di posta elettronica nell'arco di una giornata, il database di registrazione attività sarebbe cresciuto di 10 GB. È possibile configurare il servizio ricevente in modo che non registri i dati XrML effettivi, riducendo la quantità delle informazioni registrate.

È consigliabile creare script per archiviare le informazioni le più vecchie dal database di registrazione attività in un database secondario. Esempi di script per le registrazioni sono disponibili nel Toolkit di RMS, disponibile per il download gratuito dal [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=26724) (http://go.microsoft.com/fwlink/?LinkId=26724).

Variabili che influenzano la crescita del database di registrazione attività
----------------------------------------------------------------------------

Previsione delle dimensioni del database di registrazione attività in funzione del proprio ambiente. È possibile prevedere numerose voci “iniziali” nel registro attività, fra cui:

-   Registrazione del server RMS
-   Registrazione utenti (un'unica richiesta per ogni computer utilizzato da ciascun utente)
-   Richieste automatizzate di certificati di pubblicazione fuori linea da parte degli utenti

La massa delle voci del database di registrazione attività dopo l'avvio iniziale sono correlate all'emissione di licenze d'uso per il contenuto protetto. Molte condizioni influiscono sulla crescita di questo database::

-   Richiesta di una nuova licenza ogni volta che un utente accede al contenuto protetto. Questo non è il metodo predefinito per i documenti protetti, ma è un'impostazione facoltativa. Se si sceglie di implementare questo requisito, i database cresceranno con maggiore rapidità.
-   Numero previsto di messaggi di posta elettronica protetti, inviati ogni giorno a ciascuna persona.
-   Numero previsto di utenti univoci che leggeranno i messaggi di posta elettronica protetti.
-   Destinatari previsti dei documenti Microsoft Office 2003 (Word, PowerPoint ed Excel) protetti, prodotti ogni giorno da ciascuna persona.
-   Destinatari previsti dei documenti protetti.

La dimensione iniziale del database di registrazione attività sarà di circa 1.7 MB, inclusa la richiesta di un certificato dal server RMS. Ogni volta che un nuovo utente si registra, il nuovo utente ottiene un certificato per account con diritti (RAC) e un certificato concessore di licenze client (CLC). Queste due azioni sono registrate e aumentano il database di 0,06 MB. Ogni volta che un utente acquisisce con successo una licenza di pubblicazione per il contenuto protetto, il database crescerà di 0,19 MB.

Per valutare come funziona questa stima, si consideri che un'organizzazione con 5000 utenti distribuisce RMS per l'utilizzo da parte di tutti. Ogni utente ha un computer e l'organizzazione utilizza due server RMS. Dopo la distribuzione ogni utente, in media, crea ogni giorno almeno un messaggio di posta elettronica protetto con RMS, inviato a cinque altri utenti. Ogni utente crea ogni giorno anche un documento protetto con RMS, a cui accedono tre altri utenti. La seguente tabella stima l'aumento della dimensione del database di registrazione attività in seguito a queste azioni.

###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Azione</th>
<th>Crescita del file di registrazione</th>
<th>Dimensione globale delle registrazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Il provisioning del server RMS è stato eseguito con successo</p></td>
<td style="border:1px solid black;"><p>1,7 MB</p></td>
<td style="border:1px solid black;"><p>1,7 MB</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Registrazione di 5000 dipendenti (5000*0,06)</p></td>
<td style="border:1px solid black;"><p>300 MB</p></td>
<td style="border:1px solid black;"><p>301,7 MB</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Accesso a messaggi di posta elettronica protetti (25000*0,19)</p></td>
<td style="border:1px solid black;"><p>4750 MB</p></td>
<td style="border:1px solid black;"><p>5051,7 MB</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Accesso a documenti protetti (15000*0,19)</p></td>
<td style="border:1px solid black;"><p>2850 MB</p></td>
<td style="border:1px solid black;"><p>7901,7 MB</p></td>
</tr>
</tbody>
</table>
  
In tal modo, dopo la registrazione, il database di registrazione attività ha una dimensione statica di circa 300 MB. Tuttavia, la crescita giornaliera in questo esempio è di 7,6 GB, prossima quindi al limite di 8 GB dell'installazione predefinita di Accodamento messaggi. Se il database di registrazione attività diviene non disponibile per più di un giorno, le voci di registrazione attività inizierebbero a perdersi.
  
Controllo della dimensione del database di registrazione attività  
-----------------------------------------------------------------
  
Il piano di distribuzione deve includere un metodo per la gestione del database di registrazione attività. Quelli che seguono sono gli approcci più comuni.
  
-   **Eliminazione e archiviazione**  
    Questo metodo implica l'utilizzo di procedure SQL Server per archiviare in un database secondario una selezione di informazioni del database di registrazione attività, una volta che le voci di registrazione raggiungono una certa durata. Questo implica anche un filtro sui database per segnalare le informazioni irrilevanti, in modo da non sprecare spazio.  
-   **Limitazione delle informazioni registrate**  
    Il database di registrazione attività è composto da tre tabelle principali. Una di queste è **DRMS\_Log\_Filter**, che identifica quale campo della tabella principale deve essere registrato quando il filtro è abilitato.  
    Le voci on/off sulla tabella indicano quali campi della tabella principale sono in effetti registrati dal servizio listener registrazione sul server RMS. Due di questi campi (relativi a XrML) sono stati già impostati a 0 per disabilitare la registrazione, poiché questi due campi costituiscono almeno il 99% della dimensione di ogni riga di richiesta di licenza.  
    Un'altra tabella del database **DRMS\_Config\_ServerName\_Port**, chiamata **DRMS\_ClusterPolicies**, contiene un **PolicyName** di **LoggingFiltering**. **LoggingFiltering** non è abilitato per impostazione predefinita. Se si modifica il valore di **LoggingFiltering** a 1 e si riavvia il servizio listener registrazione, la crescita giornaliera del database nell'esempio precedente diminuirebbe drasticamente dai 7,6 GB giornalieri a circa 160 MB.  
-   **Spostamento del database di registrazione attività**  
    Un'altra opzione per la gestione di un database di registrazione attività in continua crescita è semplicemente spostarlo su un server con più spazio su disco. Il database di registrazione può esistere su un server di database diverso dal database di configurazione. Per spostare il database su un altro server, seguire questi passaggi:  
    1.  Arrestare il servizio listener registrazione su ogni server RMS.  
    2.  Copiare il database (o crearne uno nuovo) su un altro server.  
    3.  Modificare il database RMS **DRMS\_Config\_ServerName\_Port** selezionando la tabella **DRMS\_ClusterPolicies** e modificando i valori di **LoggingDatabaseName** (nome del server di database) **LoggingDatabaseServer** (nome del database).  
    4.  Riavviare IIS eseguendo IISRESET.exe dalla riga di comando.
