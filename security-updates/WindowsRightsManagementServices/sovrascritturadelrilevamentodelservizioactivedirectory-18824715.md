---
TOCTitle: Sovrascrittura del rilevamento del servizio Active Directory
Title: Sovrascrittura del rilevamento del servizio Active Directory
ms:assetid: '9d97e7fb-5b05-4853-ad7b-6cc82b9729f0'
ms:contentKeyID: 18824715
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747614(v=WS.10)'
---

Sovrascrittura del rilevamento del servizio Active Directory
============================================================

Per individuare le posizioni dei servizi, i client e i servizi RMS eseguono prima una ricerca nel Registro di sistema locale. Se determinate chiavi nel Registro di sistema non contengono alcun valore, i servizi e i client RMS ricercano in Active Directory il punto di connessione del servizio (SCP). Questo significa che, se si immettono specifiche chiavi nel Registro di sistema server o client, sarà possibile eseguire l'override dell'impostazione di individuazione predefinita di Active Directory.

| ![](images/Cc747614.note(WS.10).gif)Nota                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se il cluster radice di RMS viene configurato in modo che il punto di connessione del servizio non venga pubblicato in Active Directory, sarà possibile utilizzare queste chiavi per indirizzare i client RMS verso la posizione corretta. |

In questa sezione vengono descritte le voci del Registro di sistema e vengono fornite informazioni dettagliate su come crearle.

Override dell'individuazione di servizi per la registrazione secondaria dei cluster utilizzati esclusivamente per la gestione delle licenze
-------------------------------------------------------------------------------------------------------------------------------------------

Se si esegue il provisioning di un cluster utilizzato esclusivamente per la gestione delle licenze e si desidera eseguirne la registrazione secondaria con un altro cluster radice rispetto al cluster radice distribuito nell'insieme di strutture di Active Directory del cluster utilizzato esclusivamente per la gestione delle licenze, è necessario eseguire l'override dell'individuazione dei servizi di registrazione secondaria e di certificazione account.

#### Descrizioni delle voci del Registro di sistema

Le voci del Registro di sistema riportate di seguito vengono utilizzate per eseguire l'override dei servizi di registrazione secondaria e di certificazione account.

-   **SubEnrollmentURL**. Questa voce specifica il percorso del cluster radice utilizzato dal server licenze durante la richiesta del relativo certificato concessore di licenze.
-   **GicURL**. Questa voce specifica il percorso del servizio di certificazione account per il cluster utilizzato esclusivamente per la gestione delle licenze.

#### Dettagli sulle voci

Sui computer che eseguono la versione a 32 bit di Windows Server 2003, il percorso completo delle sottochiavi del Registro di sistema delle voci di individuazione del servizio per la registrazione secondaria dei cluster utilizzati esclusivamente per la gestione delle licenze è:

**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DRMS\\1.0**

Sui computer che eseguono la versione a 64 bit di Windows Server 2003, il percorso completo delle sottochiavi del Registro di sistema delle voci di individuazione del servizio per la registrazione secondaria dei cluster utilizzati esclusivamente per la gestione delle licenze è:

**HKEY\_LOCAL\_MACHINE\\SoftwareWOW6432Node\\Microsoft\\DRMS\\1.0**

Nella tabella riportata di seguito vengono elencate le voci che è possibile aggiungere per eseguire l'override dell'individuazione dei servizi.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SubEnrollmentURL</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">http(o https)://<em>nome_server</em>/_wmcs/certification/subenrollservice.asmx</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GicURL</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">http(o https)://<em>nome_server</em>/_wmcs/certification/certification.asmx</td>
</tr>
</tbody>
</table>
  
Override dell'individuazione di servizi sul lato client per la pubblicazione  
----------------------------------------------------------------------------
  
Se gli utenti intendono pubblicare il contento dai relativi computer, è opportuno eseguire l'override delle posizioni dei server utilizzati per la pubblicazione, a seconda della topologia utilizzata nell'azienda. Le posizioni dei server utilizzati per la pubblicazione vengono in genere individuate dal client mediante Active Directory. Aggiungendo le chiavi del Registro di sistema appropriate sui computer client, i client ignoreranno tali metodi e utilizzeranno gli URL specificati nel valore delle voci del Registro di sistema.
  
| ![](images/Cc747614.note(WS.10).gif)Nota                                                                                                                                       |  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Gli override sul lato client elencati in questa sezione devono essere creati come chiavi e non come singole voci. È opportuno creare il valore per queste chiavi nella voce predefinita di ciascuna chiave. |
  
#### Descrizioni delle chiavi del Registro di sistema
  
Le chiavi del Registro di sistema riportate di seguito possono essere utilizzate per eseguire l'override del rilevamento automatico del cluster RMS.
  
-   **Activation**. Questa chiave del Registro di sistema definisce l'URL del sevizio di attivazione del computer. Se si esegue il client RMS con Service Pack 1 o versione successiva, questa voce del Registro di sistema non verrà più utilizzata.  
-   **EnterprisePublishing**. Questa chiave del Registro di sistema definisce l'URL di un'installazione di RMS che si desidera venga utilizzata dal client per la richiesta di licenze.  
-   **CloudPublishing**. Questa chiave del Registro di sistema definisce l'URL del servizio di gestione licenze ospitato in Microsoft, che è possibile utilizzare se il client non dispone dell'accesso a un'installazione di RMS ma dispone dell'accesso a Internet.
  
#### Dettagli sulle chiavi
  
Il percorso completo delle sottochiavi del Registro di sistema per le voci di individuazione di servizi sul lato client per la pubblicazione è:
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSDRM\\ServiceLocation\\**
  
Nella tabella riportata di seguito vengono elencate le voci del Registro di sistema che è possibile aggiungere su un computer client RMS per eseguire l'override dell'individuazione dei servizi.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Activation</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">http (o https)://<em>nome_cluster_RMS</em>/_wmcs/Certification dove <em>nome_cluster_RMS</em> rappresenta il nome del cluster RMS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">EnterprisePublishing</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">http (o https)://<em>nome_cluster_RMS</em>/_wmcs/Licensing dove <em>nome_cluster_RMS</em> rappresenta il nome del cluster RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CloudPublishing</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">http (o https)://<em>nome_cluster_FQDN</em>/_wmcs/Licensing dove <em>nome_cluster_FQDN</em> rappresenta il nome di dominio completo del cluster RMS.</td>
</tr>
</tbody>
</table>
  
Per assicurarsi che tutti i client nell'azienda utilizzino i server di pubblicazione corretti, è consigliabile implementare queste chiavi del Registro di sistema utilizzando Systems Management Server o Criteri di gruppo.
  
| ![](images/Cc747614.Caution(WS.10).gif)Attenzione                                                                                                                                                  |  
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| La modifica non corretta del Registro di sistema può danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è necessario effettuare il backup di tutti i dati rilevanti presenti nel computer. |
  
Per importare le chiavi del Registro di sistema corrette in ciascun server del cluster RMS, è possibile utilizzare un file del Registro di sistema di esempio (.reg).
  
**Per importare le chiavi del Registro di sistema corrette in ciascun server del cluster RMS**  
1.  Copiare il file del Registro di sistema di esempio riportato di seguito nel Blocco note.
  
    `Windows Registry Editor Version 5.00`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation]`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation]`
  
    `@="http://<RMS_cluster_name>/_wmcs/certification"`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing]`
  
    `@="http://<RMS_cluster_name>/_wmcs/licensing"`
  
2.  Sostituire &lt;nome\_cluster\_RMS&gt; con il nome del cluster RMS.
  
3.  Salvare il file con l'estensione del nome di file .reg.
  
4.  Fare doppio clic sul nome del file in Esplora risorse.
  
5.  Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata a scegliere **Continua**.. Quando viene visualizzato un messaggio in cui viene chiesto se si desidera aggiungere le informazioni al Registro di sistema, fare clic su **Sì**.
