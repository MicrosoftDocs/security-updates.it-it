---
TOCTitle: Definizione dei criteri di trust
Title: Definizione dei criteri di trust
ms:assetid: 'e8d78300-4b26-4f15-9e4f-5ae9eb827ef9'
ms:contentKeyID: 18824816
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747711(v=WS.10)'
---

Definizione dei criteri di trust
================================

Per definire i domini di pubblicazione e i domini utenti trusted, attenersi alla seguente procedura.

-   **Domini utenti trusted**. Quando si aggiunge un dominio utente, in RMS possono venire elaborate le richieste di licenze d'uso provenienti da utenti i cui certificati per account con diritti sono stati emessi da un'installazione di RMS presente in una struttura di Active Directory diversa, ovvero in un cluster di certificazione principale diverso. È possibile aggiungere un dominio utente trusted importando il certificato concessore di licenze server dell'installazione da considerare attendibile.
-   **Domini di pubblicazione trusted**. Tramite l'aggiunta di un dominio di pubblicazione, si consente a un server RMS di emettere licenze d'uso per le licenze di pubblicazione emesse da un server RMS diverso. È possibile aggiungere un dominio di pubblicazione trusted importando il certificato concessore di licenze server e la chiave privata del server da considerare attendibile.

Per ulteriori informazioni, vedere "[Aggiunta e rimozione di domini utente trusted](https://technet.microsoft.com/7c440b15-01c4-49f1-b43c-00f67f3388c1)" e "[Aggiunta e rimozione di domini di pubblicazione trusted](https://technet.microsoft.com/d87b502d-5497-4ccd-badf-f6807d587cee)", più avanti in questo argomento. Per le istruzioni dettagliate, vedere “[Definire i criteri di trust](https://technet.microsoft.com/6c2be3c2-1837-4de4-a72e-3ba3eec3321d)”, più avanti in questo argomento.
