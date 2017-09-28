---
TOCTitle: Requisiti software per RMS
Title: Requisiti software per RMS
ms:assetid: '17faf2ad-2366-4a92-98a5-766e20a0f741'
ms:contentKeyID: 18824512
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720201(v=WS.10)'
---

Requisiti software per RMS
==========================

Nella tabella seguente sono elencati i requisiti software per l'esecuzione dei server RMS.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Sistema operativo</td>
<td style="border:1px solid black;">Qualsiasi edizione di Microsoft Windows Server® 2003, ad eccezione di Web Edition.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">File system</td>
<td style="border:1px solid black;">Si consiglia il file system NTFS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Componenti del sistema operativo</td>
<td style="border:1px solid black;"><ul>
<li>Accodamento messaggi (noto anche come MSMQ) con l'integrazione del servizio directory di Active Directory® abilitata.<br />
<br />
</li>
<li>Internet Information Services (IIS) con ASP.NET abilitato.<br />
<br />
</li>
<li>Microsoft .NET Framework 1.1<br />
<br />
</li>
</ul></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizio directory Active Directory®</td>
<td style="border:1px solid black;">RMS deve essere installato in un dominio Active Directory in cui i controller di dominio eseguono Windows Server 2000 con Service Pack 3 (SP3) o versioni successive. Tutti gli utenti e i gruppi che utilizzano RMS per utilizzare e pubblicare contenuti devono avere un indirizzo di posta elettronica configurato in Active Directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server database</td>
<td style="border:1px solid black;">Per il funzionamento di RMS, sono richiesti database e stored procedure. È possibile utilizzare Microsoft SQL Server 2000 con SP3a o versione successiva o Microsoft SQL Server 2005. Per il testing o altre distribuzioni in un unico computer, è possibile utilizzare Microsoft SQL Server Desktop Engine (MSDE 2000) con SP3 o Microsoft SQL Server 2005 Express Edition.</td>
</tr>
</tbody>
</table>
  
Se si distribuisce RMS in un ambiente con più insiemi di strutture Active Directory, è necessario utilizzare i gruppi universali di Active Directory perché l'appartenenza ai gruppi venga replicata su tutti i cataloghi globali. Per creare gruppi universali, il livello di funzionalità del dominio deve essere impostato almeno sulla modalità nativa Windows 2000 e il livello di funzionalità dell'insieme di strutture deve essere innalzato a Windows Server 2003.
  
Si raccomanda di utilizzare MSDE 2000 o Microsoft SQL Server 2005 Express Edition per supportare i database di RMS solo negli ambienti di testing, poiché MSDE 2000 e Microsoft SQL Server 2005 Express Edition non supportano interfacce di rete. Inoltre, le condizioni per l'utilizzo di MSDE 2000 e Microsoft SQL Server 2005 Express Edition impediscono di utilizzare gli strumenti client di SQL Server per modificare un database di MSDE 2000 o Microsoft SQL Server 2005 Express Edition. A causa di questa limitazione, non sarà possibile visualizzare informazioni sulla registrazione attività né modificare dati memorizzati nel database di configurazione.
  
Se la versione 1.1 di ASP.NET non è installata sul server, il processo di installazione sarà differente a seconda che la versione di Windows Server 2003 di cui si dispone è a 32 bit o a 64 bit.
  
Se si esegue la versione a 32 bit di Windows Server 2003, eseguire la procedura descritta per installare e attivare ASP.NET versione 1.1:
  
1.  Aprire **Installazione applicazioni** nel **Pannello di controllo**, quindi fare clic su **Installazione componenti di Windows**.  
2.  Fare clic su **Server applicazioni**, quindi su **Dettagli**.  
3.  In Aggiunta guidata componenti di Windows, selezionare **ASP.NET** .  
4.  Se ASP.NET 1.1 è installato, ma non attivato come estensione del servizio Web IIS:  
    -   Aprire Gestione Internet Information Services.  
    -   Fare clic su **Estensioni servizio Web**, selezionare ASP.NET v1.1.4322 e fare clic su **Consenti**.
  
Se si esegue la versione a 64 bit di Windows Server 2003, eseguire la seguente procedura per installare e abilitare ASP.NET versione 1.1:
  
1.  Installare .NET Framework 1.1, che eseguirà l'installazione di ASP.NET 1.1. È possibile scaricare Microsoft .NET Framework Version 1.1 Redistributable Package dall'area download Microsoft all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=69985](http://go.microsoft.com/fwlink/?linkid=69985).  
2.  Aprire Gestione Internet Information Services.  
3.  Fare clic su Estensioni servizio Web, selezionare ASP.NET v1.1.4322 e fare clic su Consenti.
  
Se si esegue la versione a 64 bit di Windows Server 2003, attenersi alla seguente procedura per attivare l'interoperabilità tra IIS e RMS:
  
1.  Fare clic su **Start**, quindi su **Esegui**.  
2.  In **Apri**, digitare il seguente comando e premere INVIO:
  
**"cscript %SystemDrive%\\inetpub\\AdminScripts\\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 1"**
  
RMS non è progettato per .NET Framework versione 2.0. Benché sia supportata l'installazione combinata, è necessario assicurarsi che ASP.NET sia configurato in modo da utilizzare ASP.NET v1.1.4322. Vi sono due modi per garantire il funzionamento di un'installazione combinata:
  
-   Assicurarsi di installare .NET Framework versione 2.0 prima di installare il server RMS.  
-   Reimpostare la versione di ASP.NET su 1.1.4322 nel Sito Web predefinito in IIS eseguendo il seguente comando:
  
**"%SystemRoot%\\Microsoft.NET\\Framework\\v1.1.4322\\aspnet\_regiis -s w3svc/1/root"**
  
Per ulteriori informazioni su Active Directory, Accodamento messaggi e IIS, vedere Guida e supporto tecnico di Windows Server 2003.
  
| ![](images/Cc720201.Caution(WS.10).gif)Attenzione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |  
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| È possibile eseguire il provisioning del server RMS nel sito Web predefinito o in qualunque sito definito in precedenza in IIS. Per motivi di protezione, è consigliabile non utilizzare il server per eseguire altri siti o servizi, poiché ciò comporterebbe l'esecuzione di più applicazioni e servizi con lo stesso account di RMS, in particolare l'Account di sistema locale, che potrebbe esporre le chiavi private a operazioni non autorizzate. Non è consigliabile effettuare il provisioning del server RMS sullo stesso sito Web di Microsoft Office SharePoint Server 2007. Non è possibile utilizzare RMS con l'autenticazione Kerberos. Il provisioning del server RMS in un sito Web comporta la disattivazione dell'autenticazione Kerberos per tale server. Se RMS non è configurato in modo da utilizzare ASP.NET v1.1.4322, non vengono registrate informazioni nel database di registrazione, con conseguente perdita di dati. |
  
Vedere anche  
------------
  
####  
  
[Pianificazione dell'infrastruttura di server database](https://technet.microsoft.com/b12354bd-3143-4d1f-b5aa-450c4550653c)
