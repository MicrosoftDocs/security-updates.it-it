---
TOCTitle: Protezione durante il provisioning
Title: Protezione durante il provisioning
ms:assetid: '9f1282c5-5642-4870-a9a4-c3a485f8ff76'
ms:contentKeyID: 18824717
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747616(v=WS.10)'
---

Protezione durante il provisioning
==================================

È possibile utilizzare il sito Web Amministrazione di RMS per eseguire il provisioning delle risorse RMS in un sito Web esistente. Durante il provisioning, nel sito Web vengono creati directory virtuali e pool di applicazioni, mentre sul server database vengono creati e configurati database RMS. Facoltativamente, se è connesso a Internet, il server può essere registrato con il Servizio di Enrollment Microsoft durante il processo di provisioning.

In questa fase, RMS utilizza gli account illustrati nella seguente tabella.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Account</th>
<th style="border:1px solid black;" >Scopo</th>
<th style="border:1px solid black;" >Autorizzazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Account dell'utente connesso</td>
<td style="border:1px solid black;">Crea directory virtuali e pool di applicazioni. IIS richiede l'autenticazione di Windows, mentre RMS rappresenta l'utente connesso che deve essere connesso localmente.</td>
<td style="border:1px solid black;">Controllo completo (l'utente connesso deve essere un amministratore locale).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Account di sistema</td>
<td style="border:1px solid black;">Crea l'assembly temporaneo per la serializzazione.</td>
<td style="border:1px solid black;">Autorizzazioni di lettura e scrittura per la cartella temporanea di Windows, C:\Windows\Temp.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Account di ASPNET</td>
<td style="border:1px solid black;">Crea l'assembly temporaneo dei file *.aspx.</td>
<td style="border:1px solid black;">Accesso alla directory della cache dell'assembly temporaneo, per impostazione predefinita C:\Windows\Microsoft.NET\Framework\v1.1.4322\Temporary ASP.NET Files.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Account Servizio di rete</td>
<td style="border:1px solid black;">Registra il punto di connessione del servizio in Active Directory.</td>
<td style="border:1px solid black;"><ul>
<li>Autorizzazioni di sola lettura per il sito del provisioning (in genere C:\Inetpub\Wwwroot\Provisioning).<br />
<br />
</li>
<li>Autorizzazioni in lettura e scrittura per la chiave del Registro di sistema <strong>DRMS</strong>. Le autorizzazioni vengono concesse dal programma di installazione di RMS, il quale crea anche la chiave del Registro di sistema che segue.<br />
<br />
Su computer in cui è in esecuzione la versione a 32 bit di Windows Server 2003:<br />
<br />
<code>HKEY_LOCAL_MACHINE\Software\Microsoft\DRMS\1.0</code><br />
<br />
Su computer in cui è in esecuzione la versione a 64 bit di Windows Server 2003:<br />
<br />
<code>HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\DRMS\1.0</code><br />
<br />
</li>
</ul></td>
</tr>
</tbody>
</table>
 

Durante il provisioning, RMS esegue le seguenti operazioni:

-   Sul server database:
    -   Crea i database di configurazione, dei servizi di directory e di registrazione attività.
    -   Assegna le autorizzazioni di accesso al gruppo del servizio RMS.
    -   Installa le stored procedure nei database e assegna le autorizzazioni di esecuzione al gruppo del servizio RMS.
    -   Esegue query sul database master.
-   Aggiunge il gruppo del servizio RMS al gruppo IIS\_WPG.
-   In C:\\Inetpub\\Wwwroot\\\_wmcs, crea una gerarchia di directory virtuali, file e pool di applicazioni per i servizi Web e il sito Web Amministrazione.
-   Imposta elenchi DACL per directory virtuali, file e pool di applicazioni.
-   Concede al gruppo del servizio RMS l'accesso alla cartella temporanea.
-   Quando l'utente specifica la protezione della chiave software, crittografa la chiave privata del concessore di licenze server prima di memorizzarla nel database. Durante il provisioning, RMS richiede una password e ottiene l'accesso alla DPAPI a livello di computer.
-   Installa il servizio listener per la registrazione attività.
-   Crea una coda di messaggi per la registrazione attività.
-   Se il provisioning riguarda il server di certificazione principale, imposta il punto di connessione del servizio in Active Directory.
