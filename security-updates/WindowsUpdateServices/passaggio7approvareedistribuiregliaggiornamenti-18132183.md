---
TOCTitle: 'Passaggio 7: Approvare e distribuire gli aggiornamenti'
Title: 'Passaggio 7: Approvare e distribuire gli aggiornamenti'
ms:assetid: '38db25a9-6702-4e43-b536-764e8814afc6'
ms:contentKeyID: 18132183
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720504(v=WS.10)'
---

Passaggio 7: Approvare e distribuire gli aggiornamenti
======================================================

Le informazioni disponibili in questo passaggio consentono di approvare un aggiornamento per i computer di prova appartenenti al gruppo Test. Durante le 24 ore successive i computer del gruppo comunicheranno con il server di WSUS. Dopo questo periodo, è possibile utilizzare la funzionalità per la gestione dei rapporti di WSUS per verificare che gli aggiornamenti siano stati distribuiti ai computer. Se i risultati del test sono soddisfacenti, è quindi possibile approvare gli stessi aggiornamenti per gli altri computer dell'organizzazione.

Nel passaggio 7 vengono illustrate le procedure seguenti:

-   Approvare e distribuire un aggiornamento.
-   Controllare il rapporto Stato degli aggiornamenti.

**Per approvare e distribuire un aggiornamento**
1.  Sulla barra degli strumenti della console WSUS fare clic su **Aggiornamenti**. Per impostazione predefinita, nell'elenco degli aggiornamenti vengono visualizzati solo gli Aggiornamenti critici e gli Aggiornamenti della protezione il cui rilevamento è stato approvato nei computer client. Per eseguire la procedura seguente, utilizzare il filtro predefinito.

2.  Nell'elenco degli aggiornamenti selezionare gli aggiornamenti dei quali si desidera approvare l'installazione. Nella scheda **Dettagli** sono disponibili informazioni su un aggiornamento selezionato. Per selezionare più aggiornamenti contigui, tenere premuto MAIUSC durante la selezione. Per selezionare più aggiornamenti non contigui, tenere premuto CTRL durante la selezione.

3.  In **Attività** fare clic su **Cambia approvazione**. Verrà visualizzata la finestra di dialogo **Approva aggiornamenti**.

4.  Nell'elenco **Impostazioni di approvazione del gruppo per gli aggiornamenti selezionati** selezionare **Installazione** nell'elenco della colonna **Approvazione** per il gruppo Test e quindi fare clic su **OK**.

| ![](images/Cc720504.note(WS.10).gif)Nota                                                                                                                                                                                                                                                           |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sono disponibili varie opzioni associate all'approvazione degli aggiornamenti, ad esempio l'impostazione di una scadenza, nonché la disinstallazione degli aggiornamenti. Per informazioni su tali opzioni, vedere il white paper “Microsoft Windows Server Update Services Operations Guide” (informazioni in lingua inglese). |

Dopo 24 ore, è possibile utilizzare la funzionalità per la gestione dei rapporti di WSUS per verificare che gli aggiornamenti siano stati distribuiti ai computer.

**Per controllare il rapporto Stato degli aggiornamenti**
1.  Sulla barra degli strumenti della console WSUS fare clic su **Rapporti**.

2.  Nella pagina **Rapporti** fare clic su **Stato degli aggiornamenti**.

3.  Per filtrare l'elenco degli aggiornamenti, in **Visualizzazione** selezionare i criteri desiderati e quindi fare clic su **Applica**.

4.  Se si desidera visualizzare lo stato di un aggiornamento in base al gruppo di computer e quindi in base al computer, espandere la visualizzazione dell'aggiornamento, se necessario.

5.  Se si desidera stampare il rapporto Stato degli aggiornamenti, fare clic su **Stampa rapporto** in **Attività**.

Se la distribuzione degli aggiornamenti al gruppo Test è stata completata correttamente, è possibile approvare gli stessi aggiornamenti per gli altri computer dell'organizzazione.
