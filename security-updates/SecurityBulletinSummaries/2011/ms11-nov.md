---
TOCTitle: 'MS11-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2011'
ms:assetid: 'ms11-nov'
ms:contentKeyID: 61240063
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2011
==================================================================

Data di pubblicazione: martedì 8 novembre 2011

**Versione:** 1.0

Il presente riepilogo elenca i bollettini sulla sicurezza rilasciati a novembre 2011.

Con il rilascio dei bollettini sulla sicurezza di novembre 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 3 novembre 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 9 novembre 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di novembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032487958). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

Riepiloghi
----------

<span></span>
La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato e percorsi per il download**.

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo del bollettino e riepilogo</th>
<th style="border:1px solid black;" >Livello di gravità massimo e impatto della vulnerabilità</th>
<th style="border:1px solid black;" >Necessità di riavvio</th>
<th style="border:1px solid black;" >Software interessato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=229071">MS11-083</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in TCP/IP può consentire l'esecuzione di codice in modalità remota (2588516)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia un flusso continuo di pacchetti UDP appositamente predisposti a una porta chiusa in un sistema di destinazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=229638">MS11- 085</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Mail e Windows Meeting Space può consentire l'esecuzione di codice in modalità remota (2620704)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo (come un file .eml o .wcinv) che si trova nella stessa directory di rete di una libreria di un file di collegamento dinamico (DLL) appositamente predisposto. Poi, durante l'apertura del file legittimo, Windows Mail o Windows Meeting Space può tentare di caricare il file DLL ed eseguire qualsiasi codice esso contenga. L'attacco è possibile solo se l'utente visita un file system remoto o una condivisione WebDAV di dubbia provenienza e apre un file legittimo (come un file .eml o .wcinv) da questa posizione che è poi caricato da un'applicazione vulnerabile.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=229253">MS11-086</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Active Directory può consentire l'acquisizione di privilegi più elevati (2630837)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Active Directory, in Active Directory Application Mode (ADAM) e in Active Directory Lightweight Directory Service (AD LDS). La vulnerabilità può consentire l'acquisizione di privilegi più elevati se Active Directory è configurato per utilizzare LDAP su SSL (LDAPS) e un utente malintenzionato acquisisce un certificato revocato che è associato a un domain account valido, quindi lo utilizza pe eseguire l'autenticazione nel dominio di Active Directory. Per impostazione predefinita, Active Directory non è configurato per utilizzare LDAP su SSL.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=229245">MS11-084</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei driver in modalità kernel di Windows può consentire un attacco di tipo Denial of Service (2617657)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente apre un file di caratteri TrueType appositamente predisposto come allegato di un messaggio di posta elettronica o se accede a una condivisione di rete o a un percorso WebDAV che contiene un file di caratteri TrueType appositamente predisposto. L'attacco è possibile solo se l'utente visita un file system remoto o una condivisione WebDAV di dubbia provenienza che contiene il file di caratteri TrueType appositamente predisposto o apre il file come allegato di un messaggio di posta elettronica. In tutti questi casi, comunque, non è in alcun modo possibile obbligare gli utenti ad eseguire queste azioni. Un utente malintenzionato deve invece persuadere gli utenti a compiere questa azione, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o in Instant Messenger.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Moderato</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
| ID bollettino                                              | Titolo della vulnerabilità                                                 | ID CVE                                                                           | Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software             | Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software            | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali |  
|------------------------------------------------------------|----------------------------------------------------------------------------|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------------|  
| [MS11-083](http://go.microsoft.com/fwlink/?linkid=229071)  | Vulnerabilità legata all'overflow del conteggio dei riferimenti            | [CVE-2011-2013](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2013) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | (Nessuna)         |  
| [MS11- 085](http://go.microsoft.com/fwlink/?linkid=229638) | Vulnerabilità legata al caricamento di librerie non sicure in Windows Mail | [CVE-2011-2016](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2016) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | Non applicabile                                                                  | (Nessuna)         |  
| [MS11-086](http://go.microsoft.com/fwlink/?linkid=229253)  | Vulnerabilità legata all'elusione dell'autenticazione LDAPS                | [CVE-2011-2014](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-2014) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | Non applicabile                                                                  | (Nessuna)         |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="7">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=8c7c21c5-677d-4a5d-8f2b-8ca7691b6b00)  
(KB2616310)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=989cca2d-cce1-4f52-b50e-43152693f240)  
(KB2616310)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=08b27ce7-c32e-41e4-ad04-481c5eab17a7)  
(KB2601626)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=f116824e-ea48-422d-b284-c9ffa7604bf5)  
(KB2616310)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=de5a74f2-2cc8-4677-b495-3a40fe3d6b9e)  
(KB2601626)  
(Importante)  
[Active Directory Application Mode (ADAM)](http://www.microsoft.com/downloads/details.aspx?familyid=1af1b734-62c7-4e08-91c8-90b6d026da84)  
(KB2616310)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory](http://www.microsoft.com/downloads/details.aspx?familyid=6168bc67-3d59-450f-bd8a-02d61dabe16b)  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fc3fe87c-2493-431d-a904-dec9310f6042)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e08266d8-fffa-40bf-b8f6-10a65ee27524)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=2bd602cf-ae0d-4790-a5d0-6133fd7d01a0)  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=042c1a8f-834d-4eed-8a59-9e030ccc6d39)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4f2365ed-d50e-44d9-b859-1ec54d3b4d38)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=783521ad-5c50-4194-a582-4e5a1c9999e7)  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=79382bf2-d2cb-42ea-92dc-64f949353521)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f82dc413-668c-4ca8-a8c8-db74f05346bc)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=b5688923-3914-4f6c-8bc9-036fb4870cc6)\*  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=71ff3a89-d7ad-4dda-9e59-fab54b21bd5d)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=06ad5637-56a1-4478-aaa0-063e877503c9)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=51f47181-08f6-4de1-80e5-253355675965)\*  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b1c0cb05-c284-49b1-ae4f-92813fdf520f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2de5de74-e643-4045-9c22-ff95b0dbcafc)  
(Moderato)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=4ddb4c2a-bada-49b0-ad78-e07e7e11ced7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2307fa93-8e45-4841-a5a9-7e89960712f9)  
(Basso)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=b06f9f55-e3b2-4705-83d0-1b9f5de9d378)  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=156c1bd9-55bc-482c-874b-61998d1ef153)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=05eef5d7-acf6-46e4-abfc-dc83f0a7cae5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=62603d18-1b21-400c-8eba-202193182960)  
(Basso)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=790f1d99-96a5-438d-b433-895b692912ce)  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5c7db930-5495-43f0-928c-d586ac9e80d0)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-083**](http://go.microsoft.com/fwlink/?linkid=229071)
</td>
<td style="border:1px solid black;">
[**MS11- 085**](http://go.microsoft.com/fwlink/?linkid=229638)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-086**](http://go.microsoft.com/fwlink/?linkid=229253)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS11-084**](http://go.microsoft.com/fwlink/?linkid=229245)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Basso**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3f9f74a6-e984-4aab-837c-ef7286e7305f)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c9cf6a22-f9ab-427a-9b16-33c60baaabb5)\*\*  
(Basso)
</td>
<td style="border:1px solid black;" colspan="2">
[Active Directory e Active Directory Lightweight Directory Service (AD LDS)](http://www.microsoft.com/downloads/details.aspx?familyid=cc1e99af-fc67-400b-a82c-171f8c4d1ac9)\*  
(KB2601626)  
(Importante)
</td>
<td style="border:1px solid black;" colspan="2">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5d810dae-5c52-4155-b5c2-163d27be6e78)\*\*\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=b20bfcbd-a515-4074-b56e-b82539fe5bad)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=012777f5-51f2-4944-91af-a9c79b8081a1)  
(Basso)
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=395819e2-1028-44b7-ace4-ca754b1a7543)  
(Moderato)
</td>
</tr>
</table>
 
**Noteper Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*\*Le installazioni con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano, come indicato, le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 se installati utilizzando l'opzione di installazione di Server Core, anche se i file interessati da questa vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/default.aspx).

**System Center Configuration Manager 2007**

La Gestione aggiornamenti software di Configuration Manager 2007 semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con Configuration Manager 2007, gli amministratori IT possono consegnare gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in Configuration Manager 2007 rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. La Gestione aggiornamenti software di Configuration Manager 2007 si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare Configuration Manager 2007 per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/it-it/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/it-it/windowsserver/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   David Warren di [CERT/CC](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS11-084
-   Ivan Sanchez di EvilCode per aver segnalato un problema descritto nel bollettino MS11-085
-   Xavier Lassoie e Sébastien Godard di Autosécurité per aver segnalato un problema descritto nel bollettino MS11-086

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 novembre 2011): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
