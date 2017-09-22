---
TOCTitle: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Appendice B'
Title: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Appendice B'
ms:assetid: '397b7ba0-cbb5-40c8-b4ab-5b23fe439876'
ms:contentKeyID: 20200893
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536294(v=TechNet.10)'
---

Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft
==============================================================================================================

### Appendice B - Parametri dei servizi di quarantena per accesso remoto

Aggiornato: 24 maggio 2005

L'installazione del Servizio quarantena accesso remoto prevede la creazione di alcune voci nel Registro di sistema che consentono di modificare gli elementi elencati di seguito.   

**Nota:** se si utilizza l'editor del Registro di sistema in modo non corretto, è possibile che si verifichino gravi problemi che potrebbero richiedere la reinstallazione del sistema operativo. Microsoft non può garantire la risoluzione dei problemi generati dall'uso improprio dell'editor del Registro di sistema. L'editor del Registro di sistema verrà quindi utilizzato a proprio rischio esclusivo.

Il percorso completo per configurare i parametri del Registro di sistema è il seguente:

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\rqs

I parametri che è possibile configurare sono:

-   **AllowedSet**. Il parametro AllowedSet consente di impostare la versione dello script che viene accettata dal server di connessione VPN in quarantena di accesso remoto.
        ```

L'elenco delle stringhe che verranno accettate dal servizio allo scopo di rimuovere la quarantena è il seguente:

-   **Port (REG\_DWORD)**. Il parametro Port specifica la porta TCP su cui il servizio RQS resterà in attesa. Se non viene specificata alcuna porta, verrà utilizzata la porta 7250.

-   **Authenticator (REG\_SZ)**. Specifica il modulo da chiamare per la rimozione della quarantena. Il modulo predefinito è mprapi.dll.

    Se si crea una DLL personalizzata per implementare la rimozione della funzionalità di filtro quarantena, sarà necessario esporre la funzione seguente:
        ```

<!-- -->

-   **Validator (REG\_SZ)**. Specifica il modulo che verifica se la stringa della firma inviata da RQC è accettabile o meno. Per impostazione predefinita, RQS.exe eseguirà il confronto delle stringhe AllowedSet. La DLL di autenticazione personalizzata deve esporre la funzione seguente:
        ```

    dove lpwsString contiene la stringa da autenticare.

##### Download

[![](images/Dd536294.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft](http://go.microsoft.com/fwlink/?linkid=41308)

[](#mainsection)[Inizio pagina](#mainsection)
