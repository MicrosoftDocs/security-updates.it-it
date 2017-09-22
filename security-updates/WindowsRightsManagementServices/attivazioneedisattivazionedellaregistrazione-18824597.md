---
TOCTitle: Attivazione e disattivazione della registrazione
Title: Attivazione e disattivazione della registrazione
ms:assetid: '50ccd827-2d39-41e7-a395-3d5f5836869b'
ms:contentKeyID: 18824597
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747565(v=WS.10)'
---

Attivazione e disattivazione della registrazione
================================================

È possibile attivare e disattivare la registrazione attività per il cluster o il server in uso dalla pagina **Impostazioni registrazione attività**. Se si disattiva la registrazione attività, i dati registrati non vengono più inviati dai servizi Web di RMS alla coda di messaggi di registrazione attività. Viene inoltre interrotto il servizio listener di registrazione attività. Non è possibile disattivare la registrazione attività tramite lo strumento di amministrazione dei servizi di Windows Server 2003.

I registri di RMS sono inviati al server database tramite l'Accodamento messaggi. Se non è presente una connessione al server database, l'Accodamento messaggi memorizza i registri in una cache locale fino al ripristino della connettività. Alla prima attivazione del servizio di registrazione attività, verificare che il server RMS disponga di una connessione al server database e che il servizio database sia stato avviato. Se si utilizza SQL Server come server database, è possibile verificare la scrittura dei registri sul database attenendosi alla seguente procedura.

-   In SQL Server Enterprise Manager, passare al database di registrazione attività, espandere **Database**, quindi espandere il database che include il database di registrazione attività di RMS.
-   Fare clic sul database di registrazione attività, scegliere **Tabelle**, fare clic con il pulsante destro del mouse su **DRMS\_log\_master** e scegliere **Apri tabella - Visualizza tutte le righe**. Se è in corso la creazione dei file di registro, vengono visualizzati uno o più file.
