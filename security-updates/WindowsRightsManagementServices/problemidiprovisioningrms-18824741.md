---
TOCTitle: Problemi di provisioning RMS
Title: Problemi di provisioning RMS
ms:assetid: 'b0e6ef48-ab38-4426-be5b-811cf64c45c0'
ms:contentKeyID: 18824741
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747638(v=WS.10)'
---

Problemi di provisioning RMS
============================

Quando si esegue il provisioning di RMS, i file di risorse e le connessioni tra i vari componenti su cui si basa RMS vengono configurati e messi in funzione. Se si verifica un errore mentre RMS sta cercando di configurare una risorsa, il provisioning fallisce e appare un errore. In questa sezione vengono illustrati le cause più comuni di questi errori, per aiutare a risolvere i problemi sorti in situazioni impreviste e che impediscono il completamento del provisioning RMS.

Cannot Provision the Root Certification Server
----------------------------------------------

Potrebbe essere impossibile eseguire il provisioning un server di certificazione principale poiché non appaiono le pagine di provisioning corrette. Questo comportamento può verificarsi quando si fa clic su Effettua il provisioning di RMS su questo sito Web per eseguire il provisioning del primo server di certificazione principale dalla pagina Amministrazione globale. Invece delle pagine di provisioning per un server di certificazione principale, appaiono invece le pagine che permettono di eseguire il provisioning di un server licenze.

Questo problema si verifica quando non si annulla il provisioning dell'ultimo server di certificazione principale dell-insieme di strutture Active Directory prima di disinstallare RMS e quindi si tenta di eseguire il provisioning di un server di certificazione principale. Quando voi annulla il provisioning dell'unico server di certificazione principale in un insieme di strutture Active Directory, si rimuove il punto di connessione del servizio da Active Directory. Se non si annulla il provisioning dell'ultimo server di certificazione principale dell'insieme di strutture prima di disinstallare RMS, non sarà possibile rieseguire il provisioning di un server di certificazione principale dell'insieme di strutture se prima non si rimuove manualmente il punto di connessione del servizio da Active Directory.

Se appaiono le pagine di provisioning per un server di licenze quando si prova ad eseguire il provisioning del primo server di certificazione principale di un insieme di strutture Active Directory, rimuovere il punto di connessione del servizio da Active Directory, come segue:

**Per rimuovere punto di connessione del servizio RMS**
1.  Se necessario, installare Windows Server Support Tools:

    Per Windows Server 2003, nella cartella \\Support\\Tools del CD di installazione eseguire Suptools.msi.

    Per Windows 2000 Server, nella cartella \\Support Tools del CD di installazione, eseguire Setup.exe.

2.  Accedere al controller del dominio a cui appartiene il server di certificazione principale, utilizzo un account che sia membro del gruppo Domain Admins.

3.  Al prompt dei comandi digitare il comando seguente e quindi premere INVIO:

    **ldp**

4.  Fare clic su **Connessione** e quindi su **Connetti**.

5.  Premere INVIO. Non digitare alcuna informazione.

6.  Fare clic su **Connessione** e quindi su **Associa**.

7.  Premere INVIO. Non digitare alcuna informazione.

8.  Fare clic su **Visualizza** e quindi su **Struttura**.

9.  Premere INVIO. Non digitare alcuna informazione.

    Nel riquadro di sinistra verrà visualizzato **dc=YourDomain,dc=com**.

10. Espandere **dc=YourDomain,dc=com**.

11. Espandere **Configurazione**.

12. Espandere **Servizi**.

13. Eliminare **RightsManagementServices**.

oppure

1.  Scaricare e installare l'RMS Administration Toolkit. Il toolkit può essere scaricato dal [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=33841).
2.  Aprire il prompt dei comandi facendo clic su **Start**, **Esegui**. Nella finestra di dialogo **Esegui**, digitare **cmd**, quindi fare clic su **OK**.
3.  Al prompt dei comandi, digitare il seguente comando:
    **ADSCPRegister.exeunregisterscp** &lt;*URLperAnnullRegistraz*&gt;
4.  Al posto di &lt;*URLperAnnullRegistraz*&gt; digitare l'URL del punto di connessione del servizio RMS, ad esempio https://mio\_dominio/\_wmcs/Certification.

Al termine di questi passaggi, sarà possibile eseguire il provisioning del server di certificazione principale.

Cannot Generate SSPI Context
----------------------------

Durante il provisioning potrebbe apparire il messaggio d'errore "Cannot generate SSPI context" se l'account del servizio RMS non è autenticato quando si esegue la registrazione del server di certificazione principale presso i servizi di Enrollment Microsoft.

Se viene visualizzato questo messaggio di errore, verificare che l'account di RMS sia un account di dominio valido. Se l'account è un account di gruppo, verificare che l'appartenenza al gruppo sia valida, che sia possibile risolvere tutti gli account utente nel gruppo del dominio e che gli account abbiano le autorizzazioni per i database SQL.
