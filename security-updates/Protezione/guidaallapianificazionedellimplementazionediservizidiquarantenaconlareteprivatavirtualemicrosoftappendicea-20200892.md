---
TOCTitle: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Appendice A'
Title: 'Guida alla pianificazione dell''implementazione di servizi di quarantena con la rete privata virtuale Microsoft - Appendice A'
ms:assetid: '618966e7-d672-48c8-b94c-3f72e69e508b'
ms:contentKeyID: 20200892
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536293(v=TechNet.10)'
---

Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft
==============================================================================================================

### Appendice A - Esempi di script di quarantena

Aggiornato: 24 maggio 2005

##### In questa pagina

[](#ecaa)[Esempi di script di quarantena](#ecaa)  
[](#ebaa)[Componenti di accesso remoto](#ebaa)  
[](#eaaa)[Avvio dello script di Windows Update](#eaaa)

### Esempi di script di quarantena

Nella sezione seguente vengono illustrati alcuni script di esempio disponibili per il download dal sito Web Microsoft. Gli script sono contenuti in un file eseguibile autoestraente denominato VPN Quarantine Sample Scripts.exe. Nel file è incluso un file readme.txt e documentazione aggiuntiva relativa a ogni script.

Per ulteriori informazioni sugli script di connessione VPN in quarantena (Rete privata virtuale), vedere la pagina relativa agli [esempi di script di connessione VPN in quarantena per la verifica di configurazioni di integrità del client](http://www.microsoft.com/downloads/details.aspx?familyid=a290f2ee-0b55-491e-bc4c-8161671b2462&displaylang=en) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=a290f2ee-0b55-491e-bc4c-8161671b2462&displaylang=en (informazioni in lingua inglese)

Poiché si tratta di esempi, gli script potrebbero richiedere alcune modifiche per essere applicati all'ambiente in uso. Nella seguente tabella vengono elencati gli script e viene descritto lo scopo di ognuno.

**Tabella A.1. Esempi di script di quarantena**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome script</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Qsamples.cmd</td>
<td style="border:1px solid black;">Si tratta del file di livello principale che viene richiamato come azione di post-connessione dal profilo di Connection Manager e che avvia gli altri script.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AV.Bat</td>
<td style="border:1px solid black;">Controlla se la versione del software antivirus del client è quella più recente e include i file delle impronte digitali dei virus più recenti. Questo script esegue la convalida solo di software antivirus di tipo eTrust. Per ulteriori informazioni sullo sviluppo di uno script simile per altri pacchetti software antivirus, contattare il proprio fornitore.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CheckHotFixes.vbs</td>
<td style="border:1px solid black;">Controlla la presenza di aggiornamenti critici nel computer client. L'amministratore deve fornire un elenco degli aggiornamenti obbligatori.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ICS.vbs</td>
<td style="border:1px solid black;">Controlla se è attivata la Condivisione connessione Internet e, se necessario, la disattiva.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Passwd.vbs</td>
<td style="border:1px solid black;">Controlla la password in base ai criteri aziendali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ScrSaver.vbs</td>
<td style="border:1px solid black;">Controlla le impostazioni dello screen saver relative all'utente corrente e verifica che sia attivato e protetto da password.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WF.vbs</td>
<td style="border:1px solid black;">Controlla che Windows Firewall sia attivato in tutte le interfacce di rete e, se necessario, lo attiva.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Componenti di accesso remoto
  
Nella seguente sezione viene descritta la sintassi relativa a due componenti di quarantena per accesso remoto.
  
#### Sintassi del servizio Agente quarantena accesso remoto (RQS, Remote Access Quarantine Agent Service)
  
Per avviare il servizio Agente quarantena accesso remoto, digitare quanto segue dalla riga di comando:
```
Net start rqs  
```  
Per arrestare il servizio agente di quarantena per accesso remoto, digitare quanto segue dalla riga di comando:
```  
Net stop rqs  
```  
#### Sintassi dell'agente Client quarantena accesso remoto (RQC)
  
RQC presenta la seguente sintassi:
```  
rqc ConnName TunnelConnName Port Domain UserName String  
```  
Nella seguente tabella vengono elencati i parametri dell'agente Client quarantena accesso remoto e la relativa descrizione.
  
**Tabella A.2 Parametri agente RQC**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Parametro</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>ConnName</strong></td>
<td style="border:1px solid black;">Specifica il nome della connessione server di accesso remoto nell'host. Il valore del parametro può essere ereditato dalla variabile %DialRasEntry% del profilo di Connection Manager.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>TunnelConnName</strong></td>
<td style="border:1px solid black;">Specifica il nome della connessione di tunneling al server di accesso remoto nell'host. Il valore del parametro può essere ereditato dalla variabile %TunnelRasEntry% del profilo di Connection Manager.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Port</strong></td>
<td style="border:1px solid black;">Specifica la porta a cui viene inviata la stringa di quarantena. La porta predefinita utilizzata dall'Agente quarantena accesso remoto (RQS, Remote Access Quarantine Agent Service) sul server di accesso remoto è la porta TCP 7250. Specificare un diverso numero di porta per RQC solo se in RQS viene utilizzato un numero di porta differente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Domain</strong></td>
<td style="border:1px solid black;">Specifica il dominio dell'utente che stabilisce la connessione. Il valore del parametro può essere ereditato dalla variabile %Domain% del profilo di Connection Manager.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>UserName</strong></td>
<td style="border:1px solid black;">Specifica il nome dell'utente che stabilisce la connessione. Il valore del parametro può essere ereditato dalla variabile %UserName% del profilo di Connection Manager.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>String</strong></td>
<td style="border:1px solid black;">Specifica una stringa di testo contenente la versione dello script creato dall'amministratore. Vengono accettati tutti i caratteri a eccezione della sequenza di caratteri /0.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Avvio dello script di Windows Update
  
Il codice riportato di seguito viene utilizzato con lo script CheckHotFixes.vbs per indirizzare l'utente al sito Microsoft® Windows® Update, in cui è possibile eseguire l'installazione degli aggiornamenti della protezione più recenti:
```
Prog = """C:\Programmi\Internet Explorer\iexplore.exe""" 
WUSite= " http://windowsupdate.microsoft.com" 
Set WshShell = CreateObject("Wscript.Shell") 
WshShell.Run(prog & WUsite),1,TRUE
```  
##### Download
  
[![](images/Dd536293.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale Microsoft](http://go.microsoft.com/fwlink/?linkid=41308)
  
[](#mainsection)[Inizio pagina](#mainsection)
