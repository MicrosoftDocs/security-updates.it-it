---
TOCTitle: Gestione del criterio di esclusione
Title: Gestione del criterio di esclusione
ms:assetid: 'ee31e099-e095-4648-95da-0009fbeb48cb'
ms:contentKeyID: 18824828
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747730(v=WS.10)'
---

Gestione del criterio di esclusione
===================================

È possibile implementare nel server criteri di esclusione che consentano di rifiutare le richieste di licenze e di certificati basate sul certificato per account con diritti o sulla versione dell'archivio protetto. I criteri di esclusione consentono di rifiutare le richieste di nuovi certificati e licenze effettuate da entità compromesse ma, a differenza delle revoche, non invalidano le entità. Gli amministratori possono inoltre escludere le applicazioni compromesse o potenzialmente dannose in modo che non possano essere utilizzate per decrittografare i contenuti protetti con RMS. Gli amministratori possono inoltre escludere determinate versioni di sistemi operativi Windows, impedendo così che il contenuto protetto con RMS venga utilizzato in computer client in cui sono in esecuzione tali versioni di Windows.

Quando un'entità viene esclusa, nelle licenze d'uso create dal server RMS tale entità viene specificata negli elenchi di esclusione. Se, dopo un intervallo di tempo, si decide di eliminare un'entità che in precedenza era stata inclusa in un criterio di esclusione, è possibile eliminare tale entità dalla pagina Criteri di esclusione del sito Web Amministrazione. L'entità verrà così rimossa dall'elenco di esclusione. Tale entità non verrà considerata esclusa da eventuali nuove richieste di certificazione o di licenze.

A meno che un'entità non sia stata esclusa inavvertitamente, è consigliabile non rimuovere alcuna entità da un criterio di esclusione fino a quando non si è certi che tutti i certificati emessi prima della creazione del criterio di esclusione non siano scaduti. In caso contrario, sia i vecchi certificati che quelli nuovi consentiranno di decrittografare i contenuti, provocando problemi all'organizzazione.

In questo argomento, vengono presentate le informazioni relative alla gestione dei criteri di esclusione. Per istruzioni dettagliate sull'esclusione di entità, vedere “[Attivare i criteri di esclusione](https://technet.microsoft.com/bbb1ce50-bc11-41cf-b75b-a6756141908f)”, più avanti in questo argomento.

In questa sezione, vengono trattati gli argomenti seguenti:

-   [Esclusione di versioni dell'archivio protetto](https://technet.microsoft.com/e287f026-aab2-43ab-93bc-48087da82f36)
-   [Esclusione dei certificati per account con diritti](https://technet.microsoft.com/cba5e901-942c-4d06-9865-e6c4648c95e6)
-   [Esclusione di alcune versioni di Windows](https://technet.microsoft.com/8b8a184d-ac0e-4a43-822c-d2fae2faf484)
-   [Esclusione di applicazioni](https://technet.microsoft.com/b68ae4b2-b9ba-44ae-90cb-c88df600ec86)
