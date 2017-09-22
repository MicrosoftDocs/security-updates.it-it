---
TOCTitle: Utilizzo dei contatori prestazioni
Title: Utilizzo dei contatori prestazioni
ms:assetid: '096c3b17-c082-46c4-939c-4373af0c9dec'
ms:contentKeyID: 18824495
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720180(v=WS.10)'
---

Utilizzo dei contatori prestazioni
==================================

In RMS, sono presenti gruppi di contatori e oggetti prestazioni che possono essere utilizzati con Monitor di sistema per eseguire il monitoraggio dell'attività dei servizi RMS. I contatori prestazioni sono specifici per ogni oggetto prestazioni di RMS e includono gli oggetti riportati di seguito.

-   RMS: contatori prestazioni per il servizio proxy di attivazione per le richieste proxy di attivazione
-   RMS: contatori prestazioni per il servizio di certificazione per le richieste di certificazione account
-   RMS: contatori prestazioni per i servizi di directory per le ricerche Active Directory
-   RMS: contatori prestazioni per il servizio di registrazione per le richieste di registrazione secondaria
-   RMS: contatori prestazioni per il servizio di gestione licenze per le richieste di licenze d'uso e di pubblicazione
-   RMS: contatori prestazioni per il servizio di registrazione attività per le operazioni di registrazione

Questi contatori prestazioni vengono installati automaticamente durante il provisioning, ma è necessario aggiungerli al registro per avviare il monitoraggio.

Per aggiungere un contatore prestazioni, attenersi alla seguente procedura.

1.  Fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Prestazioni**.
2.  Nella finestra di dialogo **Prestazioni,** fare clic con il pulsante destro del mouse in un'area bianca del riquadro dettagli e scegliere **Aggiungi contatori**.
3.  Nell'elenco oggetti **Prestazioni** della finestra di dialogo **Aggiungi contatori,** selezionare il contatore desiderato e scegliere **Aggiungi**.

È possibile utilizzare le opzioni **Registri di prestazioni e avvisi**, disponibili nella finestra di dialogo **Prestazioni**, per monitorare e gestire i file di registro. Per ulteriori informazioni sui contatori prestazioni disponibili in RMS, vedere “[Contatori prestazioni per RMS](https://technet.microsoft.com/a2f4e30d-3c6f-4e74-bd11-8f2103f88b0c)”, più avanti in questo argomento. Per informazioni generali sui contatori prestazioni, vedere la Guida in linea di Monitor di sistema.
