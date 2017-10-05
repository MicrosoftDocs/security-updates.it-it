---
TOCTitle: Installazione del server RMS dal prompt dei comandi
Title: Installazione del server RMS dal prompt dei comandi
ms:assetid: 'b55b1e2a-dd14-4168-a37f-9cdedbec660b'
ms:contentKeyID: 18824748
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747733(v=WS.10)'
---

Installazione del server RMS dal prompt dei comandi
===================================================

È possibile installare RMS con Service Pack 2 (SP2) dal prompt dei comandi, rendendo automatico il processo di installazione. L'installazione automatica può essere effettuata in due modi: utilizzando il client EXE scaricato in automatico o utilizzando i file MSI estratti dal file EXE scaricato per installare il client RMS. Per effettuare l'installazione dal file EXE, utilizzare la sintassi seguente:

**WindowsRightsManagementServicesSP2-KB917275-Client-ENU.exe -override 1 /I MsDrmClient.msi REBOOT=ReallySuppress /q -override 2 /I RmClientBackCompat.msi REBOOT=ReallySuppress /q**

Per installare utilizzando i file Windows® Installer (.msi) è necessario per prima cosa estrarre i file .msi dal file eseguibile di RMS con SP2. Utilizzare il seguente comando dal prompt dei comandi per estrarre i file msdrmclient.msi e RmClientBackCompat.msi:

**WindowsRightsManagementServiceSP2-KB917275-Server-ENU.exe /X:C:\\***Install\_Location*

Dopo avere estratto i file .msi, utilizzare i seguenti comandi per installare RMS:

**msiexec.exe /I MSDrmClient.msi /qn ALLUSERS=2 /m MSIDHOG /lei logfile.log DISPLYPAGE="NO" TARGETDIR=c:\\***Install\_Location*

**msiexec.exe /I RMClientBackCompat.msi /qn ALLUSERS=2 /m MSIDHOG /lei logfile.log DISPLYPAGE="NO" TARGETDIR=c:\\***Install\_Location*

Nella tabella seguente è illustrata la sintassi di ogni comando.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Parametro</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>/I MSDrmClient.msi</strong> o <strong>/I RMClientBackCompat.msi</strong></td>
<td style="border:1px solid black;">Obbligatorio. Consente di specificare il prodotto da installare.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/qn</strong></td>
<td style="border:1px solid black;">Facoltativo. Consente di impostare l'esecuzione di un'installazione invisibile all'utente, ovvero che non richiede alcuna interazione da parte dell'utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/lei</strong> <em>logfile.log</em></td>
<td style="border:1px solid black;">Facoltativo. Consente di specificare il file in cui registrare i messaggi di stato e di errore.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>DISPLAYPAGE=”NO”</strong></td>
<td style="border:1px solid black;">Facoltativo. Consente di specificare di non visualizzare la pagina <strong>Amministrazione globale</strong> al termine dell'installazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>TARGETDIR=c:\</strong><em>Install_Location</em></td>
<td style="border:1px solid black;">Facoltativo. Consente di specificare la directory in cui installare Windows RMS con Service Pack 2. Se non si specifica alcun percorso, viene utilizzato il percorso di installazione predefinito.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc747733.note(WS.10).gif)Nota                                                                                                                                                                                        |  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Indipendentemente dal metodo di installazione scelto, occorre assicurarsi che entrambi i file .msi siano stati installati. Se si verifica un errore che impedisce l'installazione di MSDrmClient.msi, si consiglia di non installare RMClientBackCompat.msi. |
