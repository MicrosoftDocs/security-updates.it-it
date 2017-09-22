---
TOCTitle: 'FAQ - RMS: Accesso interno ed esterno'
Title: 'FAQ - RMS: Accesso interno ed esterno'
ms:assetid: '59c2c51f-6c20-450c-a334-0e1486292074'
ms:contentKeyID: 18824611
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747577(v=WS.10)'
---

FAQ - RMS: Accesso interno ed esterno
=====================================

FAQ - Accesso interno ed esterno a RMS
--------------------------------------

-   [Quali modifiche si devono apportare al firewall per consentire ai client RMS all'esterno del firewall di accedere al server RMS?](#bkmk_37)
-   [Come funziona lo scenario Extranet?](#bkmk_38)
-   [Se un utente crea un contenuto protetto con RMS e lo passa a qualcuno che non ha accesso all'installazione RMS, il destinatario può utilizzare il contenuto?](#bkmk_39)
-   [Se si utilizza Outlook 2003 o Outlook 2007 per inviare posta elettronica protetta con RMS a un cliente, cosa deve utilizzare quest'ultimo per leggere la posta?](#bkmk_40)
-   [Se le organizzazioni dispongono di propri server RMS, come possono scambiarsi il contenuto protetto con RMS?](#bkmk_41)
-   [Quando si invia posta elettronica protetta con RMS a un'organizzazione esterna che non supporta Outlook, il destinatario della posta può rispondere a un messaggio di posta che è stato letto con il componente aggiuntivo Rights Management di Internet Explorer?](#bkmk_42)

<span id="BKMK_37"></span>
#### Quali modifiche si devono apportare al firewall per consentire ai client RMS all'esterno del firewall di accedere al server RMS?

Il firewall deve consentire ai computer esterni di eseguire richieste Simple Object Access Protocol (SOAP) al server RMS su HTTP (porta TCP 80) o HTTPS (porta TCP 443).

<span id="BKMK_38"></span>
#### Come funziona lo scenario Extranet?

La licenza di pubblicazione associata al contenuto contiene due URL. Uno è l'URL Intranet impostato quando è stato eseguito il provisioning del server RMS. Il secondo è un URL Extranet che può essere impostato dall'amministratore RMS. L'URL Extranet consente al client di ottenere licenze d'uso all'esterno del firewall. Non è possibile utilizzare l'URL Extranet per creare nuovo contenuto protetto con RMS. A tale scopo è necessario un override del Registro di sistema del client RMS.

<span id="BKMK_39"></span>
#### Se un utente crea un contenuto protetto con RMS e lo passa a qualcuno che non ha accesso all'installazione RMS, il destinatario può utilizzare il contenuto?

Se l'utente non dispone di una connessione all'installazione RMS quando il contenuto protetto viene aperto per la prima volta, l'utente non potrà utilizzare il contenuto.

Office 2003 e versioni successive ottengono automaticamente licenze personalizzabili per la posta elettronica protetta con RMS al momento della sincronizzazione, in modo che la posta elettronica possa essere letta senza una connessione di rete. Tuttavia, mentre Outlook 2003 e versioni successive memorizzano automaticamente nella cache le licenze d'uso di un messaggio di posta elettronica, i documenti Excel 2007, Excel 2003, Word 2007, Word 2003, PowerPoint 2007 e PowerPoint 2003 allegati al messaggio posta elettronica dispongono degli stessi diritti assegnati al messaggio di posta elettronica che li trasporta. Quando la posta elettronica viene scaricata, non avviene alcuna sincronizzazione automatica, quindi per ottenere una licenza d'uso i messaggi devono deve essere aperti individualmente quando il computer è collegato alla rete.

<span id="BKMK_40"></span>
#### Se si utilizza Outlook 2003 o Outlook 2007 per inviare posta elettronica protetta con RMS a un cliente, cosa deve utilizzare quest'ultimo per leggere la posta?

Il destinatario deve utilizzare Outlook 2003, Outlook 2007 o il componente aggiuntivo Rights Management di Internet Explorer. Se l'organizzazione del destinatario ha stabilito una relazione di trust tra la propria installazione RMS e quella del mittente, il destinatario potrà leggere la posta elettronica senza ulteriori operazioni. La relazione di trust viene stabilita scambiando i certificati concessori di licenze server RMS, che contengono le relative chiavi pubbliche.

Se l'organizzazione del destinatario non dispone di un'infrastruttura RMS o non è stata stabilita alcuna relazione di trust, sarà possibile chiedere al proprio cliente di stabilire un Windows Live ID e spedire la posta elettronica al destinatario specificando i diritti assegnati alle credenziali Windows Live ID del cliente. Questo approccio utilizza il servizio Microsoft IRM disponibile su Internet per ottenere una licenza d'uso. Il servizio IRM viene fornito gratuitamente per consentire alle persone di utilizzare IRM in prova ed è destinato solo al test di RMS. Se si sceglie di proteggere il contenuto utilizzando questo servizio, si ricordi che nel futuro potrebbe essere disattivato senza preavviso.

<span id="BKMK_41"></span>
#### Se le organizzazioni dispongono di propri server RMS, come possono scambiarsi il contenuto protetto con RMS?

RMS utilizza domini utente trusted, mentre per i certificati utente generati da un'installazione RMS viene stabilita una relazione di trust da un'altra.

<span id="BKMK_42"></span>
#### Quando si invia posta elettronica protetta con RMS a un'organizzazione esterna che non supporta Outlook, il destinatario della posta può rispondere a un messaggio di posta che è stato letto con il componente aggiuntivo Rights Management di Internet Explorer?

Il destinatario della posta elettronica può rispondere a un messaggio di posta elettronica protetto con RMS come a qualsiasi altro messaggio, ma il corpo originale della posta elettronica ricevuta rimarrà protetto con RMS per i destinatari originali. Il modo in cui viene assemblata la posta elettronica è determinato dall'applicazione client. Il messaggio di posta elettronica originale potrebbe essere collegato alla risposta come allegato crittografato o potrebbe essere rimosso completamente, come avviene ad esempio con Outlook 2003 o Outlook 2007.
