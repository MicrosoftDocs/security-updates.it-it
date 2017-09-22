---
TOCTitle: 'Passaggio 4: Sincronizzare il server'
Title: 'Passaggio 4: Sincronizzare il server'
ms:assetid: 'a5514e46-a50b-46a6-9e5b-33c87c5b7cef'
ms:contentKeyID: 18132526
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708523(v=WS.10)'
---

Passaggio 4: Sincronizzare il server
====================================

Dopo la configurazione della connessione di rete, è possibile scaricare gli aggiornamenti. Per impostazione predefinita, in WSUS vengono scaricati gli Aggiornamenti critici e gli Aggiornamenti della protezione relativi a tutti i prodotti Microsoft. Per scaricare gli aggiornamenti, è necessario *sincronizzare* il server di WSUS.

Durante la sincronizzazione, il server di WSUS contatta Microsoft Update. Dopo il contatto, WSUS verifica la disponibilità di nuovi aggiornamenti rispetto all'ultima sincronizzazione. Poiché si tratta della prima sincronizzazione del server di WSUS, tutti gli aggiornamenti risultano disponibili e pronti per essere installati.

| ![](images/Cc708523.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nel presente documento viene illustrata la sincronizzazione mediante le impostazioni predefinite. In WSUS sono tuttavia disponibili opzioni che consentono di ridurre al minimo la larghezza di banda utilizzata durante la sincronizzazione. Per ulteriori informazioni, vedere il white paper “Deploying Microsoft Server Windows Update Services” (informazioni in lingua inglese). |

**Per sincronizzare il server di WSUS**
1.  Sulla barra degli strumenti della console WSUS fare clic su **Opzioni** e quindi fare clic su **Opzioni di sincronizzazione**.

2.  In **Attività** fare clic su **Sincronizza**.

Al termine della sincronizzazione, fare clic su **Aggiornamenti** sulla barra degli strumenti della console WSUS per visualizzare l'elenco degli aggiornamenti.
