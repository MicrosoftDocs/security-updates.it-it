---
TOCTitle: Configurazione di SMS o Criteri di gruppo per supportare la distribuzione dei client
Title: Configurazione di SMS o Criteri di gruppo per supportare la distribuzione dei client
ms:assetid: '9e37c27b-8cc1-40c6-adb7-0937aa64c8db'
ms:contentKeyID: 18824716
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747703(v=WS.10)'
---

Configurazione di SMS o Criteri di gruppo per supportare la distribuzione dei client
====================================================================================

Il client RMS è incorporato nel sistema operativo Windows Vista® e non deve più essere installato separatamente. Nei sistemi operativi precedenti a Microsoft Windows Vista è necessario reinstallare il software client RMS, quindi attivarlo.

Il processo di attivazione crea un archivio protetto e un certificato del computer per l'utente attualmente connesso. L'attivazione è un processo locale e non richiede una connessione di rete. Una volta eseguita con successo l'attivazione, la prima richiesta di licenza d'uso da parte di un'applicazione abilitata per RMS farà ottenere all'utente un certificato utente. Il client RMS può essere installato su ciascun computer client dell'organizzazione utilizzando Criteri di gruppo, Windows Update o uno script di amministrazione.

| ![](images/Cc747703.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Indipendentemente dal metodo di distribuzione del client utilizzato, il client RMS utilizza una porta per comunicare con il server RMS, per impostazione predefinita la porta 80 o 443. Accertarsi che il computer client sia in grado di inviare richieste ai cluster della directory principale e di sola licenza RMS su tali porte. |

**Utilizzo di Criteri di gruppo**

Se la propria organizzazione distribuisce il software per mezzo dei Criteri di gruppo, questo metodo consente di distribuire il client RMS utilizzando l'elevazione dei privilegi. Se il client RMS viene distribuito in questo modo, l'utente non necessita di privilegi amministrativi e può installare il client RMS utilizzando **Installazione applicazioni** nel **Pannello di controllo** o aprendo un contenuto protetto con RMS mediante un'applicazione abilitata per RMS.

**Utilizzo di Windows Update**

Windows Update fornisce il metodo più semplice per installare il client RMS su un computer. Il vantaggio di questo metodo è che utilizza un meccanismo familiare agli utenti, ma richiede che l'utente che installa il client RMS abbia diritti amministrativi locali sul computer.

**Utilizzo dell'installazione gestita da script**

Per ottenere il massimo livello di controllo sul processo di installazione dei client, è possibile ottenere il software e convalidarne l'integrità in ogni fase del processo di installazione per mezzo di uno script. È possibile creare questo script e aggiungerlo a un oggetto Criteri di gruppo (GPO) come script di avvio. Con questo metodo non è necessario che l'utente sia un amministratore locale sul computer e il client RMS viene installato automaticamente al riavvio del sistema.

Di seguito è riportato uno script di esempio:

```
Set objShell = Wscript.CreateObject("Wscript.Shell")  
objShell.run "WindowsRightsManagementServicesSP2-KB917275-Client-ENU.exe -override 1 /I MsDrmClient.msi REBOOT=ReallySuppress /q -override 2 /I RmClientBackCompat.msi REBOOT=ReallySuppress /q"
```

Per informazioni di base sulla distribuzione del client RMS utilizzando Criteri di gruppo, vedere [Configurazione di SMS o Criteri di gruppo per supportare la distribuzione dei client](https://technet.microsoft.com/9e37c27b-8cc1-40c6-adb7-0937aa64c8db), più avanti in questo argomento.

Per istruzioni sulle procedure di distribuzione del client RMS, vedere [Come distribuire il client RMS](https://technet.microsoft.com/c84f1724-cf71-4385-9003-ff68bc23c927), più avanti in questo argomento.
