---
TOCTitle: 'Appendice A: Versioni di Windows supportate'
Title: 'Appendice A: Versioni di Windows supportate'
ms:assetid: '792a6efa-3232-4fb8-a233-523f9103aae7'
ms:contentKeyID: 21736321
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd920329(v=TechNet.10)'
---

Appendice A: Versioni di Windows supportate
===========================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

### Introduzione

La tabella inclusa in questa appendice mostra lo stato delle diverse versioni del sistema operativo Microsoft® Windows® di client e server. La tabella illustra il ruolo del sistema nella soluzione *Protezione delle reti LAN senza fili con Servizi certificati*, le versioni del sistema operativo utilizzabili in tale ruolo, nonché indica se il sistema operativo è supportato o meno. L'ultima colonna della tabella contiene avvisi o note aggiuntive.

Le informazioni sul supporto di ciascun ruolo del server sono classificate come riportato di seguito:

-   **Supportato e testato** - La versione del sistema operativo è stata usata nel laboratorio MSS (Microsoft Solutions for Security) per la creazione della soluzione ed è stata testata con la soluzione.

-   **Supportato** - La versione del sistema operativo non è stata testata con la soluzione, ma Microsoft supporta il suo uso in questo ruolo. Oltre a seguire le istruzioni incluse in questa soluzione, può essere necessaria una configurazione o una personalizzazione supplementare.

-   **Non supportato** - La versione del sistema operativo non funziona nella soluzione così descritta. Potrebbe essere possibile configurare il sistema non supportato in modo che funzioni correttamente, ma questo richiederebbe molto lavoro.

-   **Sconosciuto** - La versione del sistema operativo potrebbe funzionare in questo ruolo, in quanto non sussistono controindicazioni di natura tecnica, ma è necessario eseguire verifiche e test.

Se la versione di un sistema operativo non è visualizzata accanto al ruolo, significa che non funziona (**Non supportato**) oppure non si sa se funziona (**Sconosciuto**).

**Tavola A.1. Supporto delle versioni del sistema operativo nella soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Ruolo</th>
<th style="border:1px solid black;" >Versione del sistema operativo</th>
<th style="border:1px solid black;" >Status</th>
<th style="border:1px solid black;" >Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Client senza fili</td>
<td style="border:1px solid black;">- Windows XP Professional
- Windows XP Professional Tablet Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Microsoft Windows 2000</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;">Necessario procurarsi il client 802.1X da Microsoft.com.
I certificati utente sono distribuiti manualmente o tramite script.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">- Microsoft Windows NT® versione 4.0
- Windows 9<em>x</em></td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;">È necessario procurarsi il client 802.1X tramite Premier Support.
I certificati sono distribuiti manualmente o tramite script.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Altre piattaforme</td>
<td style="border:1px solid black;">Sconosciuto</td>
<td style="border:1px solid black;">I client devono supportare 802.1X e il protocollo EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).
I certificati sono distribuiti manualmente o tramite script.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autorità di certificazione (CA) principale</td>
<td style="border:1px solid black;">Microsoft Windows Server™ 2003, Standard Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">- Windows Server 2003, Enterprise Edition
- Windows 2000 Server</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Autorità di certificazione di terze parti</td>
<td style="border:1px solid black;">Sconosciuto</td>
<td style="border:1px solid black;">Deve supportare la revoca.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CA di emissione</td>
<td style="border:1px solid black;">Windows Server 2003, Enterprise Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">- Altre versioni Windows Server
- Autorità di certificazione di terze parti</td>
<td style="border:1px solid black;">Non supportate</td>
<td style="border:1px solid black;">Possono essere generati certificati utilizzabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server RADIUS</td>
<td style="border:1px solid black;">Windows Server 2003, Standard Edition o Enterprise Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;">L'edizione Standard supporta non più di 50 punti di accesso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;">Il Servizio autenticazione Internet (IAS) di Windows 2000 può essere utilizzato per 802.1X senza fili con la perdita di alcune funzionalità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Altre piattaforme</td>
<td style="border:1px solid black;">Non supportate</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controller di dominio</td>
<td style="border:1px solid black;">Windows Server 2003, Standard Edition o Enterprise Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;">Il servizio directory Active Directory® deve disporre di uno schema Windows 2003 e un dominio nella modalità nativa Windows 2000 o versioni successive.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;">Active Directory® deve disporre di uno schema Windows 2003 e un dominio nella modalità nativa Windows 2000 o versioni successive.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server Web</td>
<td style="border:1px solid black;">Internet Information Service (IIS): Windows Server 2003</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">IIS: Windows 2000</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Altre piattaforme</td>
<td style="border:1px solid black;">Non supportate</td>
<td style="border:1px solid black;">La maggior parte dei server Web funzionano con la pubblicazione di certificati CA ed elenchi di revoche di certificati (CRL). È necessario il supporto delle pagine ASP (Active Server Pages) per le pagine di registrazione CA.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server infrastruttura, quali DNS (Domain Name System) e DHCP (Dynamic Host Configuration Protocol)</td>
<td style="border:1px solid black;">Windows Server 2003, Standard Edition o Enterprise Edition</td>
<td style="border:1px solid black;">Supportato e testato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Supportato</td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Altre piattaforme</td>
<td style="border:1px solid black;">Sconosciuto</td>
<td style="border:1px solid black;">DNS, le soluzioni di gestione e DHCP di terze parti dovrebbero funzionare con questa soluzione, purché siano soddisfatti i requisiti di base per i client Windows e Active Directory.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
