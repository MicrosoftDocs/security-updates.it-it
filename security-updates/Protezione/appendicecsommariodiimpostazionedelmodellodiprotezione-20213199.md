---
TOCTitle: 'Appendice C: Sommario di impostazione del modello di protezione'
Title: 'Appendice C: Sommario di impostazione del modello di protezione'
ms:assetid: '80d2b596-9608-4ae0-8095-81238a707002'
ms:contentKeyID: 20213199
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163104(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Appendice C: Sommario di impostazione del modello di protezione

Aggiornato: 27/12/05

La cartella di lavoro Microsoft Excel "Windows* *Server* *2003 Security Guide Settings.xls" (allegata a questa guida) documenta le impostazioni di criteri e servizi per tutti i ruoli e gli ambienti contenuti in questa guida. Questa cartella di lavoro contiene dieci fogli di lavoro, uno per ogni ruolo nella guida:

-   Il foglio di lavoro **Domain** (Dominio) contiene le impostazioni dei criteri di gruppo che configurano gli oggetti Criteri di gruppo a livello di dominio come descritto nel Capitolo 3, "Criteri di dominio".

-   Il foglio di lavoro **Member Server Baseline** (Criteri di base dei server membro) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano l'MSBP come descritto nel Capitolo 4, "Criterio di base per un server membro".

-   Il foglio di lavoro **Domain Controller** (Controller di dominio) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano il DCBP come descritto nel Capitolo 5, "Criterio di base per un controller di dominio".

-   Il foglio di lavoro **Infrastructure Server** (Server infrastruttura) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del server dell'infrastruttura come descritto nel Capitolo 6, "Ruolo di server dell'infrastruttura".

-   Il foglio di lavoro **File Server** contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del file server come descritto nel Capitolo 7, "Ruolo del file server".

-   Il foglio di lavoro **Print Server** (Server di stampa) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del server di stampa come descritto nel Capitolo 8, "Ruolo del server di stampa".

-   Il foglio di lavoro **Web Server** (Server Web) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del server IIS Web come descritto nel Capitolo 9, "Ruolo del server Web."

-   Il foglio di lavoro **IAS Server** (Server IAS) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del server IAS come descritto nel Capitolo 10, "Ruolo del server IAS".

-   Il foglio di lavoro **CA Server** (Server CA) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri del server Servizi certificati come descritto nel Capitolo 11, "Ruolo del server servizi certificati".

-   Il foglio di lavoro **Bastion Host** (Host Bastion) contiene le impostazioni dei Criteri di gruppo e del servizio SCW che configurano i criteri di host Bastion come descritto nel Capitolo 12, "Ruolo di host Bastion".

Ogni foglio di lavoro ha le seguenti colonne:

-   La colonna H, **Policy Setting Name in User Interface** (Nome dell'impostazione dei criteri nell'interfaccia utente), è il nome dell'impostazione così come appare nello Snap-in Editor criteri di gruppo di Windows* *Server* *2003.

-   La colonna J, **Legacy Client**, è il valore consigliato per quell'impostazione nell'ambiente LC.

-   La colonna J, **Enterprise Client** (Client di organizzazione), è il valore consigliato per quell'impostazione nell'ambiente EC.

-   La colonna L, **SSLF** (Specialized Security – Limited Functionality, Protezione Specializzata – Funzionalità Limitata) è il valore consigliato per quell'impostazione nell'ambiente SSLF.

Per facilitare la lettura del foglio di calcolo, sono state utilizzate ulteriori colonne che illustrano la gerarchia di oggetti all'interno dell'Editor Criteri di gruppo. Le colonne da A a G sono state utilizzate per rappresentare ognuna un diverso livello della gerarchia. Per esempio, la voce **Computer Configuration** (Configurazione computer) appare nella colonna A e la colonna Security Settings (**Impostazioni di protezione)** nella colonna C. Per facilitare la leggibilità è stata anche inserita la colonna I.

**Download**

[Utilizzo della Guida per la protezione di Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=14846)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)

[](#mainsection)[Inizio pagina](#mainsection)
