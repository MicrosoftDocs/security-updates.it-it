---
TOCTitle: 'Per attivare l''amministrazione remota di RMS'
Title: 'Per attivare l''amministrazione remota di RMS'
ms:assetid: '00f17054-5f5d-47e2-89c1-7a593b930bb3'
ms:contentKeyID: 18824503
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720181(v=WS.10)'
---

Per attivare l'amministrazione remota di RMS
============================================

È necessario installare Internet Explorer 6.0 o versione successiva sul computer utilizzato per l'amministrazione remota di RMS.

Abilitazione dell'amministrazione remota di RMS
-----------------------------------------------

#### Per attivare l'amministrazione remota di RMS

1.  Accedere al server che si desidera amministrare in remoto.

2.  Da **Strumenti di amministrazione**, aprire lo snap-in **Gestione Internet Information Services (IIS)**.

3.  Espandere l'elemento che rappresenta il sito Web in cui è stato eseguito il provisioning di RMS.

4.  Fare clic con il pulsante destro del mouse sulla cartella **\_wmcs** e scegliere **Proprietà**. Nel gruppo **Comunicazione protetta** della scheda **Protezione directory,** scegliere **Modifica**, **Richiedi canale protetto** e **OK**. In questo modo, la protezione SSL (Secure Sockets Layer) verrà applicata ai servizi Web di RMS. Per ulteriori informazioni sulla gestione dei siti Web tramite IIS, vedere la Guida in linea di IIS.

    | ![](images/Cc720181.Important(WS.10).gif)Importante                                                                                                                                                                                                             |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | È possibile proteggere i servizi Web RMS con SSL per garantire una maggiore protezione e per abilitare l'accesso HTTP remoto alle pagine Web di amministrazione di RMS. Se si prevede di abilitare SSL per i servizi Web di RMS, ottenere e installare un certificato server Web SSL valido. |

5.  Fare clic con il pulsante destro del mouse sulla cartella **Admin** e scegliere **Proprietà**. Nel gruppo **Limitazioni sull'indirizzo IP e sul nome di dominio** della scheda **Protezione directory,** scegliere **Modifica** e, nel gruppo **Limitazioni di accesso basate sull'indirizzo IP,** scegliere **Consentito** per consentire a tutti i computer di richiedere una connessione a questo sito Web.
