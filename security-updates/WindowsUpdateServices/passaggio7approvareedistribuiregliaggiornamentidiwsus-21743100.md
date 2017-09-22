---
TOCTitle: 'Passaggio 7: Approvare e distribuire gli aggiornamenti di WSUS'
Title: 'Passaggio 7: Approvare e distribuire gli aggiornamenti di WSUS'
ms:assetid: 'c4e58e17-d5e3-4194-8f26-b459e0c03b86'
ms:contentKeyID: 21743100
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd939909(v=WS.10)'
---

Passaggio 7: Approvare e distribuire gli aggiornamenti di WSUS
==============================================================

In questo passaggio approvare un aggiornamento per ciascun computer del gruppo di test di Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2). Durante le 24 ore successive i computer del gruppo contatteranno automaticamente il server di WSUS. È possibile utilizzare la funzionalità per la gestione dei rapporti di WSUS per verificare se tali aggiornamenti siano stati distribuiti sui computer di test. Una volta che i test avranno dato esito positivo, sarà possibile approvare gli aggiornamenti per i gruppi di computer applicabili all'interno dell'organizzazione.

Procedure del passaggio 7
-------------------------

-   Approvare e distribuire un aggiornamento.
-   Controllare lo stato di un aggiornamento.

**Per approvare e distribuire un aggiornamento**
1.  Nella console di amministrazione WSUS fare clic su **Aggiornamenti**. Viene visualizzato un riepilogo dello stato degli aggiornamenti per **Tutti gli aggiornamenti**, **Aggiornamenti ad alta priorità**, **Aggiornamenti della protezione** e **Aggiornamenti di WSUS**.

2.  Nella sezione **Tutti gli aggiornamenti** fare clic su **Aggiornamenti necessari per i computer**.

3.  Nell'apposito elenco selezionare gli aggiornamenti per i quali si desidera approvare l'installazione nel gruppo di computer per il test. Nel riquadro inferiore dell'area Aggiornamenti sono disponibili informazioni su un aggiornamento selezionato. Per selezionare più aggiornamenti contigui, tenere premuto **MAIUSC** durante la selezione. Per selezionare più aggiornamenti non contigui, tenere premuto **CTRL** durante la selezione.

4.  Fare clic con il pulsante destro del mouse sulla selezione e quindi scegliere **Approva**.

5.  Nella finestra di dialogo **Approva aggiornamenti** selezionare il gruppo di test e fare clic sulla freccia GIÙ.

6.  Fare clic su **Approvato per l'installazione** e quindi su **OK**.

7.  Viene visualizzata la finestra Stato approvazione che indica lo stato di avanzamento delle attività che influiscono sull'approvazione degli aggiornamenti. Una volta completato il processo di approvazione, fare clic su **Chiudi**.

Dopo 24 ore, è possibile utilizzare la funzionalità per la gestione dei rapporti di WSUS per verificare se gli aggiornamenti sono stati distribuiti sui computer del gruppo di test.

**Per controllare lo stato di un aggiornamento**
1.  Nel riquadro di spostamento della console di amministrazione WSUS, fare clic su **Rapporti**.

2.  Nella pagina **Rapporti** selezionare il rapporto **Riepilogo stato aggiornamenti**. Sarà visualizzata la finestra **Rapporto aggiornamenti**.

3.  Per filtrare l'elenco degli aggiornamenti, selezionare i criteri che si desidera utilizzare, ad esempio **Includi aggiornamenti in queste classificazioni**, quindi fare clic su **Esegui rapporto** sulla barra degli strumenti della finestra.

4.  Verrà visualizzato il riquadro **Rapporto aggiornamenti**. È possibile verificare lo stato dei singoli aggiornamenti selezionando l'aggiornamento nella sezione sinistra del riquadro. L'ultima sezione del riquadro dei rapporti consente di visualizzare un riepilogo dello stato dell'aggiornamento.

5.  È possibile salvare o stampare tale rapporto facendo clic sull'icona appropriata presente sulla barra degli strumenti.

6.  Dopo aver testato gli aggiornamenti, sarà possibile approvare l'installazione degli aggiornamenti nei gruppi di computer applicabili all'interno dell'organizzazione.

Risorse aggiuntive
------------------

[Guida dettagliata a Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)

Per ulteriori informazioni sull'utilizzo di WSUS 3.0 SP2, vedere:

Guida alla distribuzione di WSUS alla pagina [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832).

Guida operativa di WSUS alla pagina [http://go.microsoft.com/fwlink/?LinkId=139838](http://go.microsoft.com/fwlink/?linkid=139838).
