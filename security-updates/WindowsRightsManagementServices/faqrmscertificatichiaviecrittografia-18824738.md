---
TOCTitle: 'FAQ - RMS: Certificati, chiavi e crittografia'
Title: 'FAQ - RMS: Certificati, chiavi e crittografia'
ms:assetid: 'ad8cc088-1dea-44c2-be68-9091129f0f12'
ms:contentKeyID: 18824738
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747725(v=WS.10)'
---

FAQ - RMS: Certificati, chiavi e crittografia
=============================================

FAQ - Certificati, chiavi e crittografia di RMS
-----------------------------------------------

-   [Quali algoritmi di crittografia sono utilizzati in RMS?](#bkmk_10)
-   [RMS utilizza la crittografia certificata FIPS?](#bkmk_11)
-   [Per le licenze di pubblicazione o i modelli che concedono autorizzazioni a un elenco di distribuzione invece che a utenti singoli, le licenze d'uso sono gestite diversamente per la valutazione dinamica dei membri?](#bkmk_12)
-   [Quando si utilizza RMS da una postazione ad accesso pubblico, viene emesso un certificato per account con diritti (RAC) temporaneo. Quali sono le differenze fra un RAC temporaneo e un RAC standard? Come riesce RMS a rilevare l'utilizzo da una postazione ad accesso pubblico?](#bkmk_13)
-   [Quando viene utilizzato un RAC temporaneo?](#bkmk_14)
-   [RMS emette certificati X.509v3?](#bkmk_15)
-   [Dove vengono memorizzati i certificati XrML?](#bkmk_16)
-   [Dove viene memorizzata la coppia di chiavi privata/pubblica del computer?](#bkmk_17)
-   [Dove viene memorizzata la coppia di chiavi privata/pubblica del client?](#bkmk_18)
-   [AES è un algoritmo simmetrico. Come si possono trasferire in modo protetto le chiavi tra il server e l'utente?](#bkmk_19)

<span id="BKMK_10"></span>
#### Quali algoritmi di crittografia sono utilizzati in RMS?

RMS utilizza chiavi RSA a 2048 bit per il server RMS e chiavi RSA a 1024 bit per le coppie di chiavi dell'utente e del computer.

<span id="BKMK_11"></span>
#### RMS utilizza la crittografia certificata FIPS?

In RMS con Service Pack 1 e versioni successive, gli archivi protetti generati dall'applicazione client RMS utilizzano crittografia AES certificata FIPS quando il client viene installato su un computer che esegue Windows XP o Windows Server 2003. Tuttavia, se il client RMS viene installato su computer che eseguono Windows 2000, non viene installata una libreria AES certificata FIPS, quindi i relativi archivi protetti non sono compatibili FIPS.

<span id="BKMK_12"></span>
#### Per le licenze di pubblicazione o i modelli che concedono autorizzazioni a un elenco di distribuzione invece che a utenti singoli, le licenze d'uso sono gestite diversamente per la valutazione dinamica dei membri?

Le licenze d'uso vengono sempre emesse per singoli utenti. Se in una licenza di pubblicazione o modello viene citato un gruppo, RMS valuterà l'appartenenza a tale gruppo al momento dell'emissione della licenza d'uso. Se l'utente che richiede la licenza è un componente del gruppo, verrà emessa una licenza d'uso basata sull'identità dell'utente.

<span id="BKMK_13"></span>
#### Quando si utilizza RMS da una postazione ad accesso pubblico, viene emesso un certificato per account con diritti (RAC) temporaneo. Quali sono le differenze fra un RAC temporaneo e un RAC standard? Come riesce RMS a rilevare l'utilizzo da una postazione ad accesso pubblico?

L'applicazione abilitata per RMS deve determinare se il client RMS deve richiedere un RAC temporaneo o standard per l'utente. Non esiste alcun metodo di rilevazione per questa situazione. Microsoft Office 2003 è un esempio di applicazione abilitata per RMS che consente all'utente di selezionare il RAC appropriato.

La differenza principale fra un RAC temporaneo e un RAC standard è la presenza dell'identificativo di protezione dell'utente e della specifica del periodo di validità. I RAC temporanei non includono il SID dell'utente e specificano un periodo di validità di alcuni minuti. Il periodo di validità predefinito di un RAC temporaneo è 15 minuti. I RAC standard, invece, includono il SID dell'utente e specificano un periodo di validità di molti giorni. Il periodo di validità predefinito per un RAC standard è di 365 giorni.

<span id="BKMK_14"></span>
#### Quando viene utilizzato un RAC temporaneo?

Un RAC temporaneo è progettato per consentire a un utente di utilizzare il contenuto protetto con RMS su computer che soddisfano uno qualunque dei seguenti criteri:

-   Un computer che non fa parte dello stesso insieme di strutture dell'installazione RMS da cui il RAC è stato ottenuto.
-   Un computer che non fa parte dello stesso insieme di strutture in cui è situato l'account utente.
-   Non è detto che l'utente utilizzi in seguito lo stesso computer.

Esempi di computer che si adattano a questi criteri possono essere trovati nei terminal aeroportuali, nelle biblioteche pubbliche e negli Internet café.

<span id="BKMK_15"></span>
#### RMS emette certificati X.509v3?

No. RMS emette certificati XrML intesi a rappresentare gli utenti e l'espressione di criteri che non rientrano nell'ambito dei certificati X.509v3.

<span id="BKMK_16"></span>
#### Dove vengono memorizzati i certificati XrML?

Un sistema RMS utilizza i certificati e le licenze di pubblicazione riportati di seguito che vengono salvati in XrML sul computer client.

-   Certificato computer
    Nome del file: CERT-Machine.drm
    Percorso: %USERPROFILE%\\Impostazioni locali\\Dati applicazioni\\Microsoft\\DRM\\
-   Certificato per account con diritti
    Prefisso del nome di file: GIC
    Percorso: %USERPROFILE%\\&gt;Impostazioni locali\\Dati applicazioni\\Microsoft\\DRM
-   Certificato concessore di licenze client
    Prefisso del nome di file: CLC
    Percorso: %USERPROFILE%\\&gt;Impostazioni locali\\Dati applicazioni\\Microsoft\\DRM
-   Licenza d'uso
    Prefisso del nome di file: EUL
    Percorso: %USERPROFILE%\\&gt;Impostazioni locali\\Dati applicazioni\\Microsoft\\DRM

| ![](images/Cc747725.note(WS.10).gif)Nota                                                                              |
|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Un account utente ha un unico certificato computer, un file GIC e un file CLC, ma più file EUL, uno per ogni sezione di contenuto a cui si accede. |

| ![](images/Cc747725.note(WS.10).gif)Nota                                       |
|-------------------------------------------------------------------------------------------------------------|
| Per il client RMS integrato in Windows Vista®, il percorso è %USERPROFILE%\\AppData\\Local\\Microsoft\\DRM. |

<span id="BKMK_17"></span>
#### Dove viene memorizzata la coppia di chiavi privata/pubblica del computer?

La chiave privata del computer è registrata in modo protetto, salvaguardata da chiavi crittografiche correlate alle credenziali di accesso dell'utente e alla configurazione del computer.

<span id="BKMK_18"></span>
#### Dove viene memorizzata la coppia di chiavi privata/pubblica del client?

La coppia di chiavi di un account di utente è memorizzata nel certificato dell'account con diritti.

<span id="BKMK_19"></span>
#### AES è un algoritmo simmetrico. Come si possono trasferire in modo protetto le chiavi tra il server e l'utente?

Nel sistema vengono utilizzate sia chiavi simmetriche, sia chiavi pubbliche/private. Il contenuto è crittografato con una chiave simmetrica, ma le altre chiavi del sistema (utente, computer e server) sono chiavi pubbliche/private RSA. La chiave del contenuto simmetrica è crittografata sempre nelle diverse licenze di pubblicazione, nella chiave pubblica RSA del server RMS nella licenza di pubblicazione o nella chiave pubblica RSA dell'utente nella licenza d'uso.
