---
TOCTitle: 'Passaggio 6. Creare un gruppo di computer per gli aggiornamenti'
Title: 'Passaggio 6. Creare un gruppo di computer per gli aggiornamenti'
ms:assetid: 'fe219654-eae8-45ca-a44b-c1e05c3c3e93'
ms:contentKeyID: 18132544
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708629(v=WS.10)'
---

Passaggio 6. Creare un gruppo di computer per gli aggiornamenti
===============================================================

I gruppi di computer rappresentano una parte molto importante della distribuzione di WSUS e consentono di distribuire gli aggiornamenti a computer specifici. Sono disponibili due gruppi di computer predefiniti, ovvero Tutti i computer e Computer non assegnati. Per impostazione predefinita, un computer client che contatta il server di WSUS per la prima volta viene aggiunto da quest'ultimo a entrambi i gruppi.

È possibile creare gruppi di computer personalizzati. La creazione dei gruppi di computer è utile poiché questi consentono di testare gli aggiornamenti prima di distribuirli in modo diffuso. Se i risultati del test sono soddisfacenti, gli aggiornamenti possono essere distribuiti al gruppo Tutti i computer. È possibile creare un numero illimitato di gruppi personalizzati.

**Per configurare gruppi di computer**
1.  Specificare la modalità di assegnazione dei computer ai gruppi di computer. Sono disponibili due opzioni: distribuzione degli aggiornamenti sul lato server e distribuzione degli aggiornamenti sul lato client. Se si utilizza la distribuzione degli aggiornamenti sul lato server, ogni computer dovrà essere aggiunto manualmente al proprio gruppo mediante WSUS. Se si utilizza la distribuzione degli aggiornamenti sul lato client, i client verranno aggiunti automaticamente mediante Criteri di gruppo o le chiavi del Registro di sistema.

2.  Creare il gruppo di computer in WSUS.

3.  Spostare i computer nei gruppi mediante la modalità scelta nel primo passaggio.

Questa sezione contiene istruzioni per l'utilizzo della distribuzione degli aggiornamenti sul lato server, nonché lo spostamento manuale dei computer nei gruppi mediante la console di amministrazione WSUS. Se si dispone di più computer client da assegnare ai gruppi, sarà possibile utilizzare la distribuzione degli aggiornamenti sul lato client che consente di automatizzare lo spostamento dei computer nei gruppi di computer.

È possibile utilizzare il passaggio 6 per configurare un gruppo Test contenente almeno un computer per il test.

**Nel passaggio 6 vengono illustrate le procedure seguenti:**

-   Creare un gruppo.
-   Aggiungere un computer a un gruppo.

**Per creare un gruppo**
1.  Nella console di amministrazione WSUS espandere **Computer** e selezionare **Tutti i computer**.

2.  Fare clic con il pulsante destro del mouse su **Tutti i computer** o accedere al riquadro **Azioni** e quindi fare clic su **Aggiungi gruppo di computer**.

3.  Verrà visualizzata la finestra di dialogo **Aggiungi gruppo di computer**. Specificare il nome del nuovo gruppo.

Utilizzare la procedura seguente per assegnare un computer client al gruppo Test. Un computer client appropriato è rappresentato da qualsiasi computer che dispone dei requisiti hardware e software comuni alla maggior parte dei computer della rete ma non svolge un ruolo importante. In questo modo, è possibile valutare l'impatto degli aggiornamenti approvati nei computer con caratteristiche analoghe a quelle del computer utilizzato per il test.

**Per aggiungere un computer a un gruppo**
1.  Nella console di amministrazione WSUS fare clic su **Computer**.

2.  Fare clic sul gruppo di computer che si desidera spostare.

3.  Nell'elenco dei computer selezionare il computer che si desidera spostare.

4.  Fare clic sul pulsante destro del mouse su **Modifica appartenenza**.

5.  Verrà visualizzata la finestra di dialogo **Imposta appartenenza a gruppi di computer** con un elenco di gruppi.

6.  Controllare il gruppo in cui si desidera spostare il computer e quindi fare clic su **OK**.
