---
TOCTitle: Pianificazione degli utenti RMS esterni
Title: Pianificazione degli utenti RMS esterni
ms:assetid: '107e1338-4dcf-4ed5-a49d-e875cc883db1'
ms:contentKeyID: 18824506
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720190(v=WS.10)'
---

Pianificazione degli utenti RMS esterni
=======================================

Questa sezione descrive le topologie che si possono implementare per consentire all'organizzazione e agli utenti esterni di condividere in Internet il contenuto protetto con RMS.

I cluster RMS possono essere distribuiti per uso interno ed esterno utilizzando una delle seguenti opzioni:

-   Impostare l'URL del cluster di certificazione a un URL accessibile da Internet. Assicurarsi che tale URL sia risolto in Intranet ai server RMS per lo stesso cluster. Quando si esegue questa operazione, l'URL della licenza di pubblicazione che i computer degli utenti finali utilizzano per l'acquisizione delle licenze funziona sia in Intranet, sia in Internet.
-   Installare un cluster RMS separato specificatamente per la pubblicazione in Internet. È consigliabile pubblicare in questo cluster eventuale contenuto che necessita di licenze da Internet. Se è necessario che il contenuto sia disponibile internamente ed esternamente è consigliabile pubblicarlo in entrambi i percorsi. In alternativa è necessario che gli utenti siano in grado di contattare il server Internet.

Utenti esterni
--------------

Nell'installazione RMS si possono includere utenti esterni creando per loro degli account interni e concedendo loro l'accesso alla rete aziendale tramite una rete privata virtuale (VPN). L'account può avere una cassetta postale interna o un indirizzo di posta che rimanda a una cassetta postale esterna.

Se si utilizza una cassetta postale interna, gli autori interni devono specificare l'indirizzo di posta associato alla cassetta postale interna (anziché un indirizzo di posta che l'utente esterno ha al di fuori dall'organizzazione) quando pubblicano il contenuto protetto con RMS. Se si utilizza una cassetta postale esterna, gli autori interni devono assicurarsi di specificare l'indirizzo di posta esterno dell'account quando pubblicano il contenuto protetto con RMS.

Per garantire la protezione della rete anche quando viene supportato l'accesso da parte di utenti esterni, è possibile creare un insieme di strutture Active Directory separato per gli account dei partner. Con questa topologia, si può creare un cluster di certificazione principale separato per la parte del sistema RMS che si interfaccia a Internet. In questo modo gli utenti esterni sono in grado di ricevere il certificato computer RMS e il certificato per account con diritti dal cluster di certificazione principale che si interfaccia a Internet, quando ottengono per la prima volta l'accesso al contenuto protetto con RMS.

Se si decide di implementare un insieme di strutture separato per i partner esterni che conterrà gli account dei partner, RMS deve essere installato in quell'insieme di strutture. Si potrà quindi utilizzare la funzione dominio di pubblicazione trusted di RMS per stabilire i metodi di trust tra i due server RMS. È anche necessario che i record DNS esterni identifichino l'URL del cluster esterno dell'installazione RMS dell'insieme di strutture creato per i partner esterni. La creazione di questa relazione di trust consentirebbe al server RMS esterno di rilasciare le licenze d'uso per tutto il contenuto emesso dal sistema RMS interno e viceversa.

Come alternativa all'impostazione di un server RMS nell'insieme di strutture esterno, si potrebbe utilizzare un server come ISA server per filtrare il traffico in ingresso e reinviare le richieste di licenza proxy RMS al server RMS interno.

Utilizzo dei certificati esterni
--------------------------------

Si può permettere agli utenti esterni di ottenere l'accesso al contenuto protetto con RMS configurando un server RMS separato come server di gestione licenze interfacciato a Internet, pubblicando il contenuto di quel server di gestione licenze e quindi specificando le relazioni di trust su quel server.

La parte della distribuzione RMS che si interfaccia a Internet è un server di gestione licenze separato, dedicato per l'utilizzo interfacciato a Internet. Tale server fa parte dello stesso cluster dell'installazione di gestione licenze interna e utilizza lo stesso database e lo stesso URL dell'installazione di gestione licenze interna. Si tratta dell'unico server in grado di accettare traffico Internet in arrivo.

Quando gli utenti esterni richiedono una licenza d'uso a questo server licenze RMS, devono utilizzare un certificato per account con diritti di un altro servizio di certificazione RMS che abbia una relazione di trust con il server licenze.

#### Trust dei certificati per account con diritti basati su Passport

La propria organizzazione può scegliere se considerare attendibili i certificati per account con diritti basati sulle credenziali Microsoft .NET Passport. Questi certificati per account richiedono che gli utenti ottengano direttamente i certificati per account con diritti dal servizio di certificazione Microsoft in Internet.

In questo modello, gli utenti esterni ricevono da Microsoft i certificati computer RMS e i certificati per account con diritti. Quando il contenuto viene pubblicato, l'account Microsoft .NET Passport deve essere citato come destinatario della licenza di pubblicazione.

L'account Microsoft® .NET Passport deve corrispondere all'account .NET Passport utilizzato quando l'utente ha scaricato da Microsoft il certificato per account con diritti. L'autore deve specificare questo account quando aggiunge i destinatari nell'applicazione abilitata per RMS. Se gli account non corrispondono, non sarà possibile utilizzare il contenuto.

#### Trust di altri certificati esterni

Se anche nella società dell'utente esterno esiste una distribuzione RMS, si può scegliere di impostare una relazione di trust con quella società. A tal fine, richiedere che la società esporti il proprio certificato concessore di licenze server RMS e lo invii. Si può quindi importare il certificato utilizzando la console di amministrazione RMS per il proprio server di gestione licenze interfacciato a Internet.
