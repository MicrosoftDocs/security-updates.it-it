---
TOCTitle: 'Passaggio 2. Installare WSUS 3.0 nel server'
Title: 'Passaggio 2. Installare WSUS 3.0 nel server'
ms:assetid: '191e62a0-7671-41eb-9841-17c64313fa68'
ms:contentKeyID: 18132217
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720469(v=WS.10)'
---

Passaggio 2. Installare WSUS 3.0 nel server
===========================================

Dopo avere verificato che il server soddisfa i requisiti per l'installazione è possibile installare WSUS 3.0. È necessario accedere al server in cui si desidera installare WSUS 3.0 utilizzando un account membro del gruppo Administrators locale. Solo i membri di tale gruppo possono installare WSUS 3.0.

Nella procedura seguente vengono utilizzate le opzioni di installazione predefinite di WSUS che includono l'installazione di Windows Internal Database come software di database di WSUS 3.0, l'archiviazione locale degli aggiornamenti e l'utilizzo del sito Web predefinito IIS nella porta 80.

**Per installare WSUS 3.0**
1.  Fare doppio clic sul file di installazione **WSUSSetup.exe**.

2.  Nella pagina iniziale dell'installazioneguidata fare clic su **Avanti**.

3.  Nella pagina **Selezione della modalità di installazione** fare clic su **Installazione server completa inclusiva di console di amministrazione** se nel computer si desidera installare il server o su **Solo console di amministrazione** se si desidera installare solo la console di amministrazione.

4.  Nella pagina **Contratto di Licenza Microsoft** leggere attentamente i termini del Contratto di Licenza Microsoft, fare clic su **Accetto i termini del Contratto di Licenza Microsoft** e quindi su **Avanti**.

    ![](images/Cc720469.fa6ac6a6-6814-4b7e-96e8-e08af5e534b8(WS.10).gif)

5.  Nella pagina **Selezione origine aggiornamenti** dell'installazione guidata è possibile specificare l'origine degli aggiornamenti per i client. Se si seleziona la casella di controllo **Archivia aggiornamenti in locale**, gli aggiornamenti verranno archiviati nel server di WSUS 3.0 e sarà possibile selezionare una posizione di archiviazione nel file system. Se gli aggiornamenti non vengono archiviati in locale, i computer client si connettono a Microsoft Update per scaricare gli aggiornamenti approvati. Mantenere le opzioni predefinite e fare clic su **Avanti**.

    ![](images/Cc720469.c8bac396-ca39-4491-8b0c-742a0e470535(WS.10).gif)

6.  Nella pagina **Opzioni database** è possibile selezionare il software utilizzato per gestire il database di WSUS 3.0. Per impostazione predefinita, il programma di installazione di WSUS consente di installare Windows Internal Database se il computer utilizzato esegue Windows Server 2003.

7.  Se non si desidera utilizzare Windows Internal Database sarà necessario fare in modo che WSUS utilizzi un'istanza di SQL Server facendo clic su **Usa** **un server di database esistente nel computer** e digitando il nome dell'istanza nella casella. Il nome dell'istanza deve essere indicato come &lt;*nomeServer*&gt;\\&lt;*nomeIstanza*&gt;, dove*nomeServer* è il nome del server e *nomeIstanza* è il nome dell'istanza di SQL. Effettuare la selezione e fare clic su **Avanti**.

8.  Nella pagina **Connessione all'istanza di SQL Server in corso** WSUS tenta di stabilire una connessione all'istanza di SQL Server specificata. Dopo aver stabilito correttamente la connessione fare clic su **Avanti** per continuare.

    ![](images/Cc720469.36c6af0c-a61e-4151-ae50-c754a106cb1b(WS.10).gif)

9.  Nella pagina **Selezione sito Web** è possibile specificare il sito Web che verrà utilizzato da WSUS 3.0. Se si desidera utilizzare il sito Web predefinito IIS nella porta 80, selezionare la prima opzione. Se nella porta 80 è già configurato un sito Web, sarà possibile creare un sito alternativo nella porta 8530 selezionando la seconda opzione. Mantenere l'opzione predefinita e fare clic su **Avanti**.

10. Nella pagina **Inizio installazione di Microsoft Windows Server Update Services** verificare le selezioni e quindi fare clic su **Avanti**.

11. Nella pagina finale della procedura di installazione guidata saranno contenute indicazioni relative al completamento corretto o meno dell'installazione di WSUS 3.0. Dopo aver fatto clic su **Fine** verrà avviata la Configurazione guidata.
