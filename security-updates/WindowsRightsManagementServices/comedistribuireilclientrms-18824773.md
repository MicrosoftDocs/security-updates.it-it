---
TOCTitle: Come distribuire il client RMS
Title: Come distribuire il client RMS
ms:assetid: 'c84f1724-cf71-4385-9003-ff68bc23c927'
ms:contentKeyID: 18824773
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747749(v=WS.10)'
---

Come distribuire il client RMS
==============================

Se si utilizza Microsoft Windows XP o Microsoft Windows 2000, è necessario installare il client di Servizi Rights Management (RMS) per poter utilizzare qualsiasi funzione RMS, ad esempio Information Rights Management in Microsoft® Office System 2003 o il componente aggiuntivo Rights Management per Internet Explorer. Il client RMS è integrato in Windows Vista®.

In molte organizzazioni si preferisce tenere sotto controllo la distribuzione del software client all'interno dell'organizzazione stessa. È possibile utilizzare Systems Management Server (SMS) o Criteri di gruppo per distribuire il client RMS con Service Pack 2 (SP2).

Prima di iniziare la distribuzione, scaricare il client RMS all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=67736](http://go.microsoft.com/fwlink/?linkid=67736).

| ![](images/Cc747749.Important(WS.10).gif)Importante                                   |
|--------------------------------------------------------------------------------------------------------------------|
| Il client RMS è stato integrato in Microsoft Windows Vista, quindi non è più necessaria un'installazione separata. |

Estrazione dei file di installazione
------------------------------------

Dopo avere scaricato il file WindowsRightsManagementServicesSP2-KB917275-Client-ENU.exe, è necessario estrarre i file di Microsoft® Windows® Installer dal pacchetto eseguibile.

Per farlo, è possibile utilizzare la seguente riga di comando dal prompt dei comandi:

`WindowsRightsManagementServicesSP2-KB917275-Client-ENU.exe /x <path>`

dove &lt;percorso&gt; è la directory di destinazione in cui si desiderano collocare i file estratti.

Eseguendo questo comando verranno estratti i seguenti file nella directory di destinazione specificata:

-   Bootstrap.exe
    File wrapper utilizzato dal file eseguibile per installare gli altri file inclusi. Non viene utilizzato quando si installa il client RMS con SP2 mediante SMS o Criteri di gruppo.
-   MSDrmClient.msi
    File di installazione per il client RMS con SP2. Con questa installazione verrà disinstallata qualsiasi precedente versione del client RMS presente sul computer. Questo programma deve essere installato per primo sui computer client.
-   RMClientBackCompat.msi
    File di installazione che identifica il nuovo client RMS con SP2 per le applicazioni abilitate per RMS (come Microsoft Office Professional 2003 o 2007 Microsoft Office System) che dipendono dalla versione precedente del client RMS, in modo che venga sostituito dal client RMS con SP2. Questo programma deve essere installato sui computer client al termine dell'installazione di MSDrmClient.msi.

| ![](images/Cc747749.note(WS.10).gif)Nota                                                                                                                                                                                  |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Indipendentemente dal metodo di installazione scelto, occorre assicurarsi che entrambi i file di Windows Installer siano installati. Se si verifica un errore che impedisce l'installazione di MSDrmClient.msi, non installare RMClientBackCompat.msi. |

Distribuzione del client RMS mediante installazione automatica
--------------------------------------------------------------

Non è obbligatorio estrarre i file per installare i file di Windows Installer. È anche possibile distribuire il client RMS utilizzando un metodo di installazione automatico. Per farlo, è possibile utilizzare la seguente riga di comando dal prompt dei comandi:

`WindowsRightsManagementServicesSP2-KB917275-Client-ENU.exe -override 1 /I MsDrmClient.msi REBOOT=ReallySuppress /q -override 2 /I RmClientBackCompat.msi REBOOT=ReallySuppress /q`

Questo comando avvia l'installazione automatica del client RMS.

| ![](images/Cc747749.note(WS.10).gif)Nota                                                                                                                                        |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Poiché si tratta di un'installazione automatica, il programma di installazione non avvisa del suo completamento. Normalmente le installazioni automatiche vengono eseguite da un file batch o da uno script. |

Distribuzione del client RMS mediante SMS
-----------------------------------------

**Per distribuire il client RMS utilizzando SMS**
1.  Aprire la console di amministrazione di SMS.

2.  Espandere il database del sito da utilizzare.

3.  Nel riquadro di sinistra, fare clic con il pulsante destro del mouse su **Pacchetti**, scegliere **Nuovo**, quindi **Pacchetto da definizione**.

4.  Creare i pacchetti dai file MSDRMClient.msi e RMClientBackCompat.msi. I pacchetti dovrebbero avere le seguenti proprietà:

    **Generale**:

    -   Per **Riga di comando**, immettere:
        `msiexec.exe /q ALLUSERS=2 /m MSIDGHOG /i "<file_name>.msi"`
        | ![](images/Cc747749.note(WS.10).gif)Nota                                                                     |
        |-------------------------------------------------------------------------------------------------------------------------------------------|
        | MSIDGHOG è un valore casuale. Sostituire &lt;nome\_file&gt; con il nome del file di Windows Installer che verrà installato dal pacchetto. |

    -   Per **Esegui**, selezionare l'opzione **Nascosto**.
    -   Per **Dopo l'esecuzione**, selezionare l'opzione **Nessuna azione richiesta**.
    -   Per **Categoria**, selezionare l'opzione **Software amministrativo**.

    **Requisiti:**

    -   Per **Spazio su disco stimato**, immettere **445 KB**.
    -   Per **Tempo esecuzione massimo consentito**, selezionare **Sconosciuto**.
    -   Selezionare la casella di controllo **Esecuzione del programma su qualsiasi piattaforma**.

    **Ambiente:**

    -   Per **Requisiti per esecuzione programma**, selezionare l'opzione **Indipendentemente dalla connessione degli utenti**.
    -   Per **Modalità di esecuzione**, selezionare l'opzione **Esecuzione con diritti amministrativi**.
    -   Per **Modalità unità**, selezionare l'opzione **Esecuzione con nome UNC**.

    **Avanzate:**

    -   Deselezionare la casella di controllo **Esegui prima un altro programma**.
    -   Deselezionare la casella di controllo **Ometti notifica programma** in **Quando il programma è assegnato a un computer**.
    -   Deselezionare la casella di controllo **Disattivare il programma nei computer in cui è annunciato**.

5.  Impostare **Account di accesso e punti di distribuzione** nel modo appropriato per la propria organizzazione.

6.  Creare un annuncio per la documentazione appropriata. In una distribuzione SMS, si raccomanda di utilizzare il programma **Per-system unattended**.

7.  Pianificare l'annuncio in funzione delle esigenze della propria organizzazione.

Distribuzione del client RMS mediante Criteri di gruppo
-------------------------------------------------------

Per distribuire il client RMS sui computer di destinazione, è possibile utilizzare la funzionalità Installazione e manutenzione software di Criteri di gruppo.

Criteri di gruppo è il metodo raccomandato per gestire in modo attivo la distribuzione dei client RMS nelle organizzazioni di piccole e medie dimensioni e in quelle che non utilizzano già una soluzione di gestione degli aggiornamenti come Systems Management Server 2003.

Quando si utilizza Criteri di gruppo per distribuire un programma, è possibile assegnare il programma ai computer. Il programma viene installato all'avvio del computer ed è disponibile per tutti gli utenti che accedono al computer. Per ulteriori informazioni su Criteri di gruppo, vedere Creazione di un'infrastruttura di Criteri di gruppo (<http://go.microsoft.com/fwlink/?linkid=24328>). In questa procedura si presume che venga utilizzata la console GPMC (Group Policy Management Console). Per scaricare GPMC, vedere Console Gestione Criteri di gruppo con Service Pack 1 all'indirizzo <http://go.microsoft.com/fwlink/?linkid=21813>).

Gli amministratori che non hanno dimestichezza con la distribuzione del software basata su Criteri di gruppo troveranno alcune indicazioni utili nella procedura illustrata di seguito. I passaggi possono essere modificati per soddisfare le esigenze della propria organizzazione.

**Per distribuire il client RMS con Criteri di gruppo**
1.  Su un controller di dominio, aprire lo snap-in MMC (Microsoft Management Console) **Utenti e computer di Active Directory**.

2.  Creare una nuova unità organizzativa (OU) o selezionare una OU esistente.

    Se è stata creata una nuova OU, aggiungere i computer su cui si intende installare il client RMS.

3.  Fare clic con il pulsante destro del mouse sulla OU e scegliere **Proprietà**.

4.  Selezionare la scheda **Criteri di gruppo**.

5.  Fare clic su **Nuovo** per creare un nuovo oggetto Criteri di gruppo (GPO).

6.  Fare clic su **Modifica** per modificare il nuovo oggetto Criteri di gruppo.

7.  Nella struttura della console, espandere **Configurazione computer, Impostazioni del software**, quindi selezionare **Installazione software**.

8.  Fare clic con il pulsante destro del mouse nel riquadro dei dettagli, scegliere **Nuovo**, quindi **Pacchetto**.

9.  Fornire un percorso per il file MSDRMclient.msi in una cartella di rete condivisa a cui possano accedere i computer client.

10. Fare clic su **OK** per assegnare il pacchetto.

11. Ripetere i passaggi da 5 a 10 per creare un oggetto Criteri di gruppo con il quale installare il file RMClientBackCompat.msi.

| ![](images/Cc747749.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Questi passaggi sono stati indicati solo per gli utenti che non hanno dimestichezza nell'utilizzo di Criteri di gruppo. Gli amministratori esperti di Criteri di gruppo possono eseguire le procedure operative consuete per la distribuzione del pacchetto MSDrmClient.msi. Inoltre, poiché questi passaggi sono validi per un controller di dominio Windows Server 2003, la procedura e la terminologia potrebbero essere diversi per un dominio Windows 2000. |

Aggiornamento da una versione precedente
----------------------------------------

        ```
| ![](images/Cc747749.note(WS.10).gif)Nota                                          |
|----------------------------------------------------------------------------------------------------------------|
| Questo script non funziona con Microsoft Windows Vista poiché il client RMS è integrato nel sistema operativo. |
