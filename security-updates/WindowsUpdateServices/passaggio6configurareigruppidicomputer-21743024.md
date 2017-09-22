---
TOCTitle: 'Passaggio 6: Configurare i gruppi di computer'
Title: 'Passaggio 6: Configurare i gruppi di computer'
ms:assetid: '70518732-2179-4e41-9609-7f9999867f41'
ms:contentKeyID: 21743024
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd939860(v=WS.10)'
---

Passaggio 6: Configurare i gruppi di computer
=============================================

I gruppi di computer rappresentano una parte molto importante della distribuzione di Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2), in quanto consentono di testare e distribuire gli aggiornamenti a computer specifici. Sono disponibili due gruppi di computer predefiniti, ovvero Tutti i computer e Computer non assegnati. Per impostazione predefinita, un computer client che contatta il server di WSUS per la prima volta viene aggiunto da quest'ultimo a ciascun gruppo.

È possibile creare tutti i gruppi di computer personalizzati necessari alla gestione degli aggiornamenti all'interno della propria organizzazione. È consigliabile creare almeno un gruppo di computer per il test degli aggiornamenti, prima di procedere alla distribuzione sugli altri computer dell'organizzazione.

Procedure del passaggio 6
-------------------------

1.  Creare un gruppo di computer per il test.
2.  Spostare almeno un computer nel gruppo per il test.

**Per creare un gruppo per il test**
1.  Nella console di amministrazione WSUS espandere **Computer** e selezionare **Tutti i computer**.

2.  Fare clic con il pulsante destro del mouse su **Tutti i computer** e scegliere **Aggiungi gruppo di computer**.

3.  Nella finestra di dialogo **Aggiungi gruppo di computer** specificare il **nome** del nuovo gruppo per il test e fare clic su **Aggiungi**.

Utilizzare la procedura seguente per assegnare un computer client al gruppo per il test. Un computer per il test è un qualsiasi computer che dispone dei requisiti software e hardware corrispondenti alla maggior parte dei computer client della rete, non ancora assegnato a un ruolo importante. Una volta che i test avranno dato esito positivo, sarà possibile approvare gli aggiornamenti per i computer dei gruppi desiderati.

**Per assegnare un computer a un gruppo per il test**
1.  Nella console di amministrazione WSUS fare clic su **Computer**.

2.  Selezionare il gruppo di computer al quale si desidera assegnare il gruppo per il test.

3.  Nell'elenco di computer scegliere i computer che si desidera assegnare al gruppo per il test.

4.  Fare clic sul pulsante destro del mouse su **Modifica appartenenza**.

5.  Nella finestra di dialogo **Imposta appartenenza a gruppi di computer** selezionare il gruppo per il test creato in precedenza, quindi fare clic su **OK**.

Ripetere queste due procedure, ovvero, creare un gruppo e assegnargli uno o più computer, per creare tutti i gruppi di computer necessari alla gestione degli aggiornamenti del sito.

Passaggio successivo
--------------------

[Passaggio 7: Approvare e distribuire gli aggiornamenti di WSUS](https://technet.microsoft.com/c4e58e17-d5e3-4194-8f26-b459e0c03b86).

Risorse aggiuntive
------------------

[Guida dettagliata a Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)
