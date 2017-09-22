---
TOCTitle: Rimozione delle autorizzazioni dai server RMS
Title: Rimozione delle autorizzazioni dai server RMS
ms:assetid: '11badb02-62c1-455c-96b7-935bbcb496bc'
ms:contentKeyID: 18824525
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720200(v=WS.10)'
---

Rimozione delle autorizzazioni dai server RMS
=============================================

Quando si rimuovono le autorizzazioni da RMS, il comportamento del server RMS cambia affinché tramite il server sia possibile ottenere una chiave che consenta di decrittografare il contenuto protetto con RMS pubblicato in precedenza. Grazie a questa chiave, il contenuto può essere salvato senza la protezione RMS. Ciò può risultare utile se si è deciso di non utilizzare più la protezione RMS nell'organizzazione.

Il server da cui sono state rimosse le autorizzazioni deve essere eseguito per un tempo sufficiente a consentire agli utenti di salvare i contenuti senza protezione RMS e agli amministratori della rete e del sistema di disattivare eventuali client abilitati per RMS in modo che non venga più utilizzato il servizio.

È possibile attivare la rimozione delle autorizzazioni tramite la pagina Web **Impostazioni di protezione** del sito Web di amministrazione. Dopo avere attivato la rimozione delle autorizzazioni, non sarà più possibile ripristinare il server in una configurazione server RMS standard. Se nell'installazione erano stati inclusi domini di pubblicazione trusted, verranno inoltre rimosse le autorizzazioni da tali domini.

Dopo avere attivato la rimozione delle autorizzazioni, nel sito Web di amministrazione sarà presente solo la pagina **Informazioni sul server da cui sono state rimosse le autorizzazioni** e non saranno supportate ulteriori operazioni di amministrazione. Per completare il processo di rimozione delle autorizzazioni dal server, effettuare le seguenti operazioni.

1.  Concedere al **gruppo di servizi RMS** le autorizzazioni di lettura ed esecuzione per la directory principale virtuale Decommissioning.
2.  Aggiungere il gruppo **Everyone** al DACL del file decommissioning.asmx concedendo le autorizzazioni di lettura.
3.  Informare gli utenti del sistema che si stanno rimuovendo le autorizzazioni dell'installazione di RMS e invitarli a connettersi al server per salvare i loro contenuti senza la protezione RMS.
4.  Configurare tutte le applicazioni abilitate per RMS dell'organizzazione in modo che si connettano alla pagina decommissioning.asmx. A seconda dell'applicazione abilitata per RMS, questa può essere controllata da un'impostazione della chiave del Registro di sistema o dei Criteri di gruppo.
5.  Se nell'organizzazione vengono utilizzate applicazioni abilitate per RMS tramite le quali l'installazione viene automaticamente utilizzata per la pubblicazione, utilizzare i criteri di gruppo per impostare una voce del registro nei computer affinché il server da cui sono state rimosse le autorizzazioni possa essere utilizzato da tali applicazioni.
6.  Quando si ritiene che la protezione sia stata rimossa da tutti i contenuti, eseguire una copia di backup della chiave privata del server e quindi disinstallare RMS dal server.
