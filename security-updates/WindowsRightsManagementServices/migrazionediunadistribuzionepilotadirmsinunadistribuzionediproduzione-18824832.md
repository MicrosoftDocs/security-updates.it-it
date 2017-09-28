---
TOCTitle: Migrazione di una distribuzione pilota di RMS in una distribuzione di produzione
Title: Migrazione di una distribuzione pilota di RMS in una distribuzione di produzione
ms:assetid: 'ea151946-22fb-4cba-a3ef-fd7a4bf0d292'
ms:contentKeyID: 18824832
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747789(v=WS.10)'
---

Migrazione di una distribuzione pilota di RMS in una distribuzione di produzione
================================================================================

Molte organizzazioni scelgono di distribuire RMS in una distribuzione pilota prima di implementare la tecnologia in tutta l'organizzazione. Il programma pilota ha normalmente un numero limitato di utenti e il server può essere gestito localmente da un amministratore dedicato, anziché far parte di un centro di elaborazione dati gestito da un gruppo IT. Quando l'organizzazione implementa RMS nel centro di elaborazione dati per tutti i client, dopo che il progetto pilota è stato completato, sono distribuiti nuovi server RMS per supportare il maggior numero possibile di utenti.

Tuttavia, il contenuto protetto con RMS è legato al server RMS utilizzato per crearlo, quindi se un server viene rimosso o sostituito, si deve eseguire una procedura perché il contenuto crittografato con i server RMS pilota possa essere decrittografato e concesso in licenza utilizzando i server RMS di produzione.

Se si è distribuito RMS come programma pilota e si desidera spostare il server RMS nell'ambiente di produzione dell'organizzazione, conservando l'integrità del contenuto che era stato protetto utilizzando il server RMS pilota, si dovrebbe creare un piano di migrazione che assicuri una transizione senza ostacoli e consenta di tornare al programma pilota, se necessario, per recuperare i dati.

I seguenti passaggi sono forniti come esempio di alcuni degli elementi che il piano di migrazione dovrebbe includere; la propria distribuzione potrebbe comunque avere requisiti aggiuntivi.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Server</th>
<th>Passaggio</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Pilota</td>
<td style="border:1px solid black;">Backup del database di configurazione RMS.</td>
<td style="border:1px solid black;">Questo permette di ripristinare il server pilota se necessario.
Il database di configurazione include la chiave privata di RMS.
Assicurarsi di conoscere la password della chiave privata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pilota</td>
<td style="border:1px solid black;">Se si è utilizzato un dispositivo di protezione hardware (HSM) per proteggere la chiave privata RMS, eseguire il backup della configurazione dell'HSM come indicato dal produttore.</td>
<td style="border:1px solid black;">L'HSM verrà ripristinato sul nuovo server.
Assicurarsi di avere tutti i componenti necessari per installare e configurare l'HSM disponibile.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pilota</td>
<td style="border:1px solid black;">Esportare il file del dominio di pubblicazione trusted.</td>
<td style="border:1px solid black;">Questo permette a un altro server RMS di decrittografare le licenze di pubblicazione create da questo server e di emettere licenze d'uso per il contenuto protetto.
Il dominio di pubblicazione trusted include il certificato concessore di licenze server, la chiave privata RMS e qualsiasi modello di criteri per i diritti stabilito sul server.
Il file del dominio di pubblicazione trusted è un file XML crittografato da una password complessa specificata al momento della creazione del file. È necessario avere anche questa password per importare il file del dominio di pubblicazione trusted.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pilota</td>
<td style="border:1px solid black;">Esportazione del dominio utente trusted.</td>
<td style="border:1px solid black;">Questo permette a un altro server RMS di concedere licenze d'uso agli utenti i cui certificati per account con diritti (RAC) sono stati concessi dal server RMS pilota.
Il dominio di utente trusted viene stabilito importando il certificato concessore di licenze server di questo server nell'altro server RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Preparare il nuovo server in modo che sia il server di certificazione principale.</td>
<td style="border:1px solid black;">Assicurarsi che possa accedere al server di database e che siano installati IIS e Accodamento messaggi.
Se possibile, per questo server utilizzare lo stesso nome.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Se si utilizza un HSM, installare l'HSM e ripristinare la sua configurazione dal backup creato sul server pilota.</td>
<td style="border:1px solid black;">Fornire le credenziali richieste per decrittografare la chiave RMS privata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Installare RMS.</td>
<td style="border:1px solid black;">RMS verificherà che tutti i servizi indispensabili siano installati e configurati correttamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Eseguire il provisioning di RMS utilizzando una nuova chiave privata. Se si utilizza la registrazione in linea, il server sarà registrato durante il processo di provisioning, utilizzando Internet per collegarsi ai Servizi Microsoft Enrollment. Se non si ha una connessione Internet dal server, è necessario utilizzare la registrazione fuori linea.</td>
<td style="border:1px solid black;">Se il nome del server è diverso dal nome del server pilota, è possibile modificare l'impostazione dell'URL del cluster in modo che abbia lo stesso URL del server pilota.
In caso contrario, sarà necessario configurare un reindirizzamento di URL dall'URL del cluster precedente all'URL del nuovo cluster, per permettere agli utenti con contenuto preesistente di ottenere le licenze d'uso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Se si utilizza la registrazione fuori linea, completare il processo di registrazione manuale per il nuovo server RMS. Per ulteriori informazioni, vedere “Per registrare manualmente un server di certificazione principale” in “Utilizzo di un server RMS”, in questa documentazione.</td>
<td style="border:1px solid black;">Il server RMS non può essere utilizzato fino a quando non è stato registrato.
Inoltre, non è possibile accedere alle pagine di amministrazione RMS fino a quando il server non è stato registrato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Importare il file del dominio di pubblicazione trusted esportato nel passaggio 3.</td>
<td style="border:1px solid black;">L'account di servizio RMS deve avere autorizzazioni di lettura sull'ubicazione in cui è memorizzato il file per poter importare il file con successo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Firmare di nuovo ogni modello che era stato importato con il dominio di pubblicazione trusted.</td>
<td style="border:1px solid black;">I modelli sono firmati con la chiave privata server. Poiché questo server ha una nuova chiave privata, i modelli devono essere firmati per essere validi. Per ulteriori informazioni, vedere “Per firmare di nuovo un modello di criteri per i diritti” in “Utilizzo di un server RMS”, in questa documentazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Ridistribuire i modelli sui computer client che hanno partecipato al progetto pilota.</td>
<td style="border:1px solid black;">I vecchi modelli devono essere rimossi e sostituiti con i modelli firmati da questo server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produzione</td>
<td style="border:1px solid black;">Importare il file del dominio utente trusted esportato nel passaggio 4.</td>
<td style="border:1px solid black;">Permette di utilizzare i vecchi certificati concessori di licenze client e RAC.
Se gli account utente vengono spostati fra gli insiemi di strutture in seguito alla migrazione, si osservi che gli account devono avere proxy SMTP corrispondenti.</td>
</tr>
</tbody>
</table>
 

Una volta terminata la configurazione del server di produzione, verificare che gli utenti pilota possano ancora creare e leggere la posta precedentemente protetta. È possibile quindi aggiungere al cluster tanti server RMS quanti sono necessari per supportare il numero di utenti dell'organizzazione.
