---
TOCTitle: Revisione della progettazione RMS
Title: Revisione della progettazione RMS
ms:assetid: '0ed1dd67-8e07-47c9-9e2e-0104438bd19f'
ms:contentKeyID: 18824505
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720185(v=WS.10)'
---

Revisione della progettazione RMS
=================================

Prima di avviare la distribuzione, assicurarsi che durante la pianificazione RMS siano stati affrontati gli aspetti elencati di seguito.

-   È stata selezionata un'applicazione client abilitata per RMS e i piani di distribuzione sono operativi.
-   È stato determinato un metodo per la distribuzione del client RMS.
-   È stato installato ed è accessibile un server database.
-   È stata selezionata una topologia RMS, di base o distribuita.
-   È stato installato Active Directory sui controller di dominio che eseguono Windows 2000 con Service Pack 3 (SP3) o successivo e tutti gli utenti dispongono di un oggetto contatto per il quale è configurato un attributo di posta elettronica. È installato Windows Server 2003 e i suoi più recenti aggiornamenti. Sono abilitati Accodamento messaggi, Internet Information Services e ASP.NET versione 1.1.

| ![](images/Cc720185.note(WS.10).gif)Nota                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se si prevede di installare RMS su un computer a 64 bit, rileggere "Requisiti software per RMS" in "Pianificazione di una distribuzione di RMS", in questa documentazione, per informazioni sulle istruzioni speciali di configurazione. |

-   Sono stati definiti i metodi di bilanciamento del carico e di failover del server.
-   È stata configurata la registrazione DNS dei server RMS.
-   Sono operativi i piani di backup e ripristino.
-   Sono state completate le valutazioni relative alla protezione, secondo le esigenze della propria organizzazione.
