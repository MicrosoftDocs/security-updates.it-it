---
TOCTitle: 'Preparazione dell''installazione del server di certificazione principale'
Title: 'Preparazione dell''installazione del server di certificazione principale'
ms:assetid: 'ed51605e-8b17-4155-8d83-f6777f499b7b'
ms:contentKeyID: 18824831
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747726(v=WS.10)'
---

Preparazione dell'installazione del server di certificazione principale
=======================================================================

Nell'installazione di verifica esemplificativa è stato utilizzato un solo server di certificazione principale. Se lo si desidera, è possibile configurare server aggiuntivi come parte di un cluster di certificazione principale, oppure come cluster di server licenze separato. La configurazione dell'infrastruttura di tutti i server di questo tipo è la stessa e sarà pertanto necessario seguire la procedura specificata in questo argomento in tutti questi server.

Dopo aver installato il controller di dominio e configurato i server di database (come descritto nella sezione precedente) e aver completato i passaggi della tabella seguente, si sarà pronti per installare RMS.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Il componente infrastruttura</th>
<th>Per preparare il server per l'installazione di RMS</th>
<th>Note per la distribuzione in un ambiente di produzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Sistema operativo</td>
<td style="border:1px solid black;">Su un computer che soddisfa i requisiti hardware di RMS, ma che non è ancora collegato a una rete, installare il sistema operativo Windows Server 2003 e utilizzare il file system NTFS per la partizione.</td>
<td style="border:1px solid black;">È consigliabile installare sempre il service pack e le patch più recenti. Utilizzare partizioni formattate con NTFS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Connessione a Internet
(facoltativo)</td>
<td style="border:1px solid black;">Creare una connessione Ethernet a una rete che fornisce la connettività Internet ma è isolata dall'ambiente di produzione. Se si utilizzerà la registrazione in linea per registrare il server RMS come parte del processo di provisioning, il server deve disporre di connettività Internet.</td>
<td style="border:1px solid black;">Se si utilizza la registrazione in linea, assicurarsi che la connessione Internet disponga di un firewall appropriato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Indirizzo IP</td>
<td style="border:1px solid black;">Assegnare un indirizzo IP statico a questo computer.</td>
<td style="border:1px solid black;">Utilizzare sempre indirizzi IP statici per i server.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Aggiunta del computer al dominio</td>
<td style="border:1px solid black;">Accedere al computer come amministratore locale. Fare clic sul pulsante <strong>Start</strong>, fare clic con il pulsante destro del mouse su <strong>Risorse del computer</strong>, scegliere <strong>Proprietà</strong>, selezionare la scheda <strong>Nome computer</strong>, quindi fare clic su <strong>Cambia</strong>.</td>
<td style="border:1px solid black;">Utilizzare lo stesso dominio per tutti i server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Lasciare inalterato il nome di computer, fare clic su <strong>Dominio</strong>, quindi digitare il nome del dominio, ad esempio Industrieharper.com, e scegliere <strong>OK</strong>. Specificare le credenziali dell'utente che consentono di aggiungere il computer al dominio, scegliere <strong>OK</strong>, quindi riavviare il computer quando richiesto. Dopo il riavvio del computer e la richiesta delle credenziali di accesso, specificare il dominio, il nome utente e la password appropriati.</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Utente e accesso</td>
<td style="border:1px solid black;">Fare clic con il pulsante destro del mouse su <strong>Risorse del computer</strong>, scegliere <strong>Gestione</strong>, espandere <strong>Utenti e gruppi locali</strong>, fare clic su <strong>Gruppi</strong> e quindi doppio clic su <strong>Administrators</strong>.
Fare clic su <strong>Aggiungi</strong>, specificare il nome dell'account utente da aggiungere, ad esempio Zaffaroni@industrieharper.com, quindi scegliere <strong>OK</strong>. Assegnare all'account utente i privilegi di amministratore. Quando vengono richieste le credenziali, specificare i dati appropriati, ad esempio Industrieharper\Administrator.
Accedere al computer come utente del dominio con privilegi di amministratore.</td>
<td style="border:1px solid black;">I diritti di amministratore sono necessari per aggiungere componenti a questo computer. Alcuni passaggi dell'installazione non possono essere completati utilizzando l'account di amministratore locale. È necessario che almeno un utente del dominio in questo server sia un amministratore. Inoltre, SQL Server richiede i diritti di amministratore del sistema per la creazione di nuovi database.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Connessione a Internet
(facoltativo)</td>
<td style="border:1px solid black;">Utilizzando un browser Internet, accedere all'indirizzo http://uddi.microsoft.com/ per verificare l'accesso a Internet. Su computer che eseguono Windows Server 2003, è possibile che i file Lmhosts e Hosts debbano essere modificati in modo da includere il controller di dominio.</td>
<td style="border:1px solid black;">Connettersi al sito http://uddi.microsoft.com per verificare l'accesso a Internet.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Attivazione di Windows</td>
<td style="border:1px solid black;">Per attivare Windows presso Microsoft, è possibile utilizzare l'attivazione guidata utilizzando una connessione Internet oppure attivare Windows mediante contatto telefonico. Per ulteriori informazioni sull'attivazione del prodotto Windows Server 2003, vedere Guida in linea e supporto tecnico di Windows Server 2003.</td>
<td style="border:1px solid black;">Windows Server 2003 deve essere attivato entro 14 giorni dall'installazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aggiornamenti del software</td>
<td style="border:1px solid black;">Assicurarsi di aver installato gli ultimi aggiornamenti del software installato sul computer.</td>
<td style="border:1px solid black;">Installare gli ultimi aggiornamenti software.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione di Internet Explorer</td>
<td style="border:1px solid black;">RMS utilizza un'interfaccia Web per l'amministrazione. Alcune delle impostazioni di protezione predefinite possono impedire la corretta visualizzazione delle pagine. Alcune pagine nel sito Amministrazione Web RMS utilizzano finestre popup per alcune opzioni di configurazione.</td>
<td style="border:1px solid black;"> </td>
</tr>
</tbody>
</table>
  
Una volta terminati tutti i passaggi precedenti su entrambi i server, si è pronti per installare RMS ed eseguirne il provisioning sui server.
