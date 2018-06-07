---
TOCTitle: 'MS04-JUL'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2004'
ms:assetid: 'ms04-jul'
ms:contentKeyID: 61239979
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms04-jul(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - luglio 2004
================================================================

Data di pubblicazione: martedì 13 luglio 2004

**Versione:** 1.0

**Data di pubblicazione:** 13 luglio 2004
**Numero di versione:** 1.0

Una versione per gli utenti finali di questo documento è disponibile presso il seguente [sito Web](http://www.microsoft.com/italy/security/default.mspx).

**Protezione dei PC:** per informazioni su come assicurare la protezione dei PC, visitare gli indirizzi seguenti:

-   Informazioni per gli utenti finali: visitare il sito Web [Proteggi il tuo PC](http://www.microsoft.com/italy/security/protect/).
-   Informazioni per i professionisti IT: visitare il sito Web [Security Guidance Center](http://www.microsoft.com/italy/security/guidance/).

**Strategie per la gestione degli aggiornamenti:** per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare la [Guida Microsoft alla gestione delle patch di sicurezza](http://go.microsoft.com/fwlink/?linkid=21168).

**IT Pro Security Zone Community:** visitando il sito Web [IT Pro Security Zone](http://go.microsoft.com/fwlink/?linkid=21164) è possibile ottenere informazioni su come migliorare la protezione e ottimizzare l'infrastruttura IT utilizzata, nonché discutere con altri professionisti IT le varie problematiche relative alla sicurezza.

**Servizio di notifica sulla sicurezza Microsoft:** per ricevere automaticamente una notifica tramite posta elettronica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, è possibile abbonarsi al [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

#### Riepilogo

Questo bollettino include gli aggiornamenti per alcune vulnerabilità scoperte di recente, elencate di seguito in ordine di gravità.

Critico (2)
-----------

<span></span>
| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-022                                                                                                                                                           |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Una vulnerabilità nell'utilità di pianificazione potrebbe consentire l'esecuzione di codice non autorizzato (841873)**](http://technet.microsoft.com/security/bulletin/ms04-022)                     |
| **Riepilogo**                     | Nell'Utilità di pianificazione esiste una vulnerabilità legata all'esecuzione di codice in modalità remota, provocata dal modo in cui questa utilità gestisce la convalida dei nomi delle applicazioni. |
| **Livello di gravità**            | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                        |
| **Effetti della vulnerabilità**   | Esecuzione di codice in modalità remota                                                                                                                                                                 |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                                                          |

| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-023                                                                                                                         |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Una vulnerabilità nella Guida HTML potrebbe consentire l'esecuzione di codice non autorizzato (840315)**](http://technet.microsoft.com/security/bulletin/ms04-023) |
| **Riepilogo**                     | Esiste una vulnerabilità legata all'esecuzione di codice in modalità remota nell'elaborazione di un URL showHelp appositamente predisposto.                           |
| **Livello di gravità**            | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                      |
| **Effetti della vulnerabilità**   | Esecuzione di codice in modalità remota                                                                                                                               |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                        |

Importante (4)
--------------

<span></span>
| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-019                                                                                                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Una vulnerabilità in Utility Manager potrebbe consentire l'esecuzione di codice non autorizzato (842526)**](http://technet.microsoft.com/security/bulletin/ms04-019)                                                                                             |
| **Riepilogo**                     | Esiste una vulnerabilità legata all'acquisizione di privilegi più elevati nel modo in cui Utility Manager avvia le applicazioni. Un utente che ottiene l'accesso al sistema potrebbe imporre a Utility Manager l'avvio di un'applicazione con privilegi di sistema. |
| **Livello di gravità**            | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                 |
| **Effetti della vulnerabilità**   | Acquisizione di privilegi più elevati nel sistema locale                                                                                                                                                                                                            |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                                                                                                                      |

| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-020                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Una vulnerabilità in POSIX potrebbe consentire l'esecuzione di codice non autorizzato (841872)**](http://technet.microsoft.com/security/bulletin/ms04-020)                                        |
| **Riepilogo**                     | Nel sottosistema POSIX esiste una vulnerabilità legata all'acquisizione di privilegi più elevati che può consentire a un utente che ottiene l'accesso al sistema di assumerne il controllo completo. |
| **Livello di gravità**            | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                  |
| **Effetti della vulnerabilità**   | Acquisizione di privilegi più elevati nel sistema locale                                                                                                                                             |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                                                       |

| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-021                                                                      |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Aggiornamento della protezione per IIS 4.0 (841373)**](http://technet.microsoft.com/security/bulletin/ms04-021) |
| **Riepilogo**                     | In Internet Information Server 4.0 esiste una vulnerabilità di sovraccarico del buffer.                            |
| **Livello di gravità**            | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                |
| **Effetti della vulnerabilità**   | Esecuzione di codice in modalità remota                                                                            |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".     |

| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-024                                                                                                                                                                 |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Una vulnerabilità nella shell di Windows potrebbe consentire l'esecuzione di codice non autorizzato (839645)**](http://technet.microsoft.com/security/bulletin/ms04-024)                                   |
| **Riepilogo**                     | Esiste una vulnerabilità legata all'esecuzione di codice in modalità remota nel modo in cui la shell di Windows avvia le applicazioni. Per sfruttare la vulnerabilità è necessaria l'interazione dell'utente. |
| **Livello di gravità**            | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                           |
| **Effetti della vulnerabilità**   | Esecuzione di codice in modalità remota                                                                                                                                                                       |
| **Software interessato**          | **Windows**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                                                                |

Moderato (1)
------------

<span></span>
| Identificatore del bollettino     | Bollettino Microsoft sulla sicurezza MS04-018                                                                                                                                                                      |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo** **del** **bollettino** | [**Aggiornamento della protezione cumulativo per Outlook Express (823353)**](http://technet.microsoft.com/security/bulletin/ms04-018)                                                                              |
| **Riepilogo**                     | Esiste una vulnerabilità legata alla possibilità di negazione del servizio che potrebbe consentire l'invio di un messaggio di posta elettronica appositamente predisposto provocando un errore in Outlook Express. |
| **Livello di gravità**            | [Moderato](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                  |
| **Effetti della vulnerabilità**   | Negazione del servizio                                                                                                                                                                                             |
| **Software interessato**          | **Windows, Outlook Express**. Per ulteriori informazioni, vedere la sezione "Software interessato e posizioni per il download".                                                                                    |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma o componente elencato sono riportati l'effetto della vulnerabilità e un collegamento al relativo aggiornamento.

Un numero tra parentesi quadre \[x\] indica che è presente una nota che fornisce ulteriori informazioni sul problema. Tutte le note sono riportate sotto la tabella.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

**Software interessato e posizioni per il download**

 
<table style="border:1px solid black;">
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ></th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
<th style="border:1px solid black;" >Dettagli        </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore</strong> <strong>del</strong> <strong>bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-018"><strong>MS04-018</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-019"><strong>MS04-019</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-020"><strong>MS04-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-021"><strong>MS04-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-022"><strong>MS04-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-023"><strong>MS04-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms04-024"><strong>MS04-024</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Software interessato:</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server™ 2003</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8b53c35d-e9ed-46ad-936c-30c8e3a7e606&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=41c7bb26-3500-4492-a447-33440c404e4f&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003 64-Bit Edition</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=df0c5c4e-d986-4ad5-95e0-e87106d7c019&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=79cca663-5b72-4345-a3ee-404b466731bc&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows XP</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8e8d0a2d-d3b9-4de8-8b6f-fc27715bc0cf&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8b412c7f-44ad-4e77-8973-fd3e84cc496a&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=c3365b8e-666b-4c82-a9ed-fc0f84f107ba&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows XP Service Pack 1</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8e8d0a2d-d3b9-4de8-8b6f-fc27715bc0cf&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8b412c7f-44ad-4e77-8973-fd3e84cc496a&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=c3365b8e-666b-4c82-a9ed-fc0f84f107ba&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows XP 64-Bit Edition Service Pack 1</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=7b4ac0fa-7954-4993-85a1-85298f122ce0&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=0042db67-c58b-412c-a24f-9d2aa8071897&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3fee07f5-9e31-481e-9f89-2549f51147af&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows XP 64-Bit Edition versione 2003</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=df0c5c4e-d986-4ad5-95e0-e87106d7c019&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=79cca663-5b72-4345-a3ee-404b466731bc&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Service Pack 2</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=94cd9925-d99b-4cb6-b51e-248d4fd8af07&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=05203a7e-4a11-4f88-aa73-75a6c81466b8&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=bbf3c8a1-7d72-4ce9-a586-7c837b499c08&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3f2f1a7d-5cf2-4791-a7ee-07f20f75796c&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=397be12b-a026-41a6-8e98-b4027bc6a110&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 2000 Service Pack 3</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=94cd9925-d99b-4cb6-b51e-248d4fd8af07&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=05203a7e-4a11-4f88-aa73-75a6c81466b8&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=bbf3c8a1-7d72-4ce9-a586-7c837b499c08&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3f2f1a7d-5cf2-4791-a7ee-07f20f75796c&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=397be12b-a026-41a6-8e98-b4027bc6a110&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Service Pack 4</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=94cd9925-d99b-4cb6-b51e-248d4fd8af07&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=05203a7e-4a11-4f88-aa73-75a6c81466b8&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=bbf3c8a1-7d72-4ce9-a586-7c837b499c08&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3f2f1a7d-5cf2-4791-a7ee-07f20f75796c&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=397be12b-a026-41a6-8e98-b4027bc6a110&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Windows NT® 4.0 Workstation Service Pack 6a</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=25993f70-191b-4e35-aa1b-0aa1a7027880&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3a2b38c5-fa73-49ec-9eef-06fe8d6495c0&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=53f0c9c1-d72f-48e8-8f70-b29a70a618e2&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Windows NT 4.0 Server Service Pack 6a</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=c2018a81-446c-4930-a6cc-ea5b5960ff05&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=3a2b38c5-fa73-49ec-9eef-06fe8d6495c0&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=58906e66-064c-4358-9bf9-bc67b1f57bc5&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows NT Workstation 4.0 Service Pack 6a e Windows NT Server 4.0 Service Pack 6a con Active Desktop</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=87096271-9716-4a46-93f3-d41fcbdf989a&amp;displaylang=en">Importante</a><strong>[5]</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Windows NT 4.0 Server Terminal Server Edition, Service Pack 6</td>
<td style="border:1px solid black;"><strong>[3]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=9cfc4af3-b0bc-4798-bc23-f45739e3b802&amp;displaylang=en">Importante</a></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><strong>[1]</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=34035ce3-1998-4693-8330-c4515a13407d&amp;displaylang=en">Importante</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Millennium Edition (ME)</td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a71faa02-d34c-47cb-bc99-820013211463&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Windows 98 Second Edition (SE)</td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a71faa02-d34c-47cb-bc99-820013211463&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 98</td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a71faa02-d34c-47cb-bc99-820013211463&amp;displaylang=en">Critico</a></td>
<td style="border:1px solid black;"><strong>[2]</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Componenti di Windows affetti dalla vulnerabilità:</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outlook Express 5.5 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=9a8d1bf2-93c5-41a9-b79a-31d54743ba0e&amp;displaylang=en">Nessuno</a><strong>[4]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outlook Express 6</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=d5900df1-10ab-4850-9064-3070ce1f948a&amp;displaylang=en">Moderato</a></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outlook Express 6 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=ad6a96bc-daf0-4eab-89b8-bd702b3e3e5d&amp;displaylang=en">Nessuno</a><strong>[4]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outlook Express 6 Service Pack 1 (64 bit Edition)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=adccf304-6cfc-48d6-9a3f-2a601c3a04a5&amp;displaylang=en">Nessuno</a><strong>[4]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Outlook Express 6 su Windows Server 2003</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=c99aafcd-b99b-4b13-a366-5f8edc83633f&amp;displaylang=en">Nessuno</a><strong>[4]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Outlook Express 6 su Windows Server 2003 (64 bit Edition)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=10d1aad0-0313-4beb-a174-84cf573f31fd&amp;displaylang=en">Nessuno</a><strong>[4]</strong></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Internet Explorer 6 Service Pack 1</td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=d4f57f82-d2ba-411a-8b40-77a3d80e58ac">Critico</a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=18d026d3-3d93-4845-94ad-4f2656500d7a">Critico</a></td>
<td style="border:1px solid black;"></td>
</tr>
</tbody>
</table>
  
**Note**
  
**<sup>[1]</sup>** Questo sistema operativo non è esposto alla vulnerabilità per impostazione predefinita, ma potrebbe diventarlo in seguito all'installazione di determinati programmi o componenti. In particolare, in questo caso il sistema Windows NT4 diventa vulnerabile se si installa Internet Explorer 6 Service Pack 1. Per ulteriori informazioni, vedere il relativo bollettino sulla sicurezza.
  
**<sup>[2]</sup>** Questo sistema operativo è esposto alla vulnerabilità, ma non in modo critico. Gli aggiornamenti per la protezione relativi ai problemi non critici non sono in genere disponibili per questo sistema operativo. Per ulteriori informazioni sui criteri del ciclo di vita del supporto Microsoft per questo sistema operativo, visitare il seguente [sito Web](http://support.microsoft.com/default.aspx?pr=lifean1). Per ulteriori informazioni, vedere il relativo bollettino sulla sicurezza.
  
**<sup>[3]</sup>** È disponibile un aggiornamento della protezione per questo sistema operativo. Per ulteriori dettagli, vedere il componente interessato dalla vulnerabilità, Microsoft Outlook Express, nella tabella e il relativo bollettino sulla sicurezza.
  
**\[4\]** L'aggiornamento della protezione indicato in questo bollettino non risolve alcun problema di vulnerabilità per questa versione di Outlook Express, ma modifica le impostazioni di protezione predefinite per Outlook Express 5.5 Service Pack 2 rendendole più restrittive e risolve un problema introdotto con il bollettino MS04-013 per Outlook Express 6 SP1 e versioni successive relativo alla creazione di una copia della Rubrica di Windows in un percorso prevedibile con un nome di file “~”.
  
**\[5\]** Consultare il bollettino per istruzioni su come stabilire se Active Desktop è installato nel computer in uso.
  
Deployment  
----------
  
<span></span>
**Software Update Services:**
  
Microsoft Software Update Services (SUS) consente agli amministratori di eseguire in modo rapido e affidabile il deployment dei più recenti aggiornamenti critici e per la protezione sia nei server basati su Windows 2000 e Windows Server 2003, sia nei computer desktop che eseguono Windows 2000 Professional o Windows XP Professional.
  
Per ulteriori informazioni su come eseguire il deployment di questo aggiornamento della protezione con Software Update Services, visitare il sito Web [Software Update Services](http://go.microsoft.com/fwlink/?linkid=21133).
  
**Systems Management Server:**
  
Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire il deployment controllato di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per il deployment degli aggiornamenti per la protezione, visitare il sito Web [Gestione delle patch per la protezione con SMS 2003](http://www.microsoft.com/italy/smserver/evaluation/capabilities/patch.asp). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Service Feature Pack](http://www.microsoft.com/smserver/downloads/20/featurepacks/suspack) per semplificare il deployment degli aggiornamenti per la protezione. Per ulteriori informazioni su SMS, visitare il sito Web [SMS](http://go.microsoft.com/fwlink/?linkid=21158).
  
**Nota** SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e il deployment degli aggiornamenti inclusi nei bollettini sulla sicurezza. È possibile, tuttavia, che alcuni aggiornamenti non vengano rilevati tramite questi strumenti. In questi casi, per installare gli aggiornamenti in computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni sulla procedura da utilizzare, visitare il seguente [sito Web](http://www.microsoft.com/technet/prodtechnol/sms/sms2003/patchupdate.mspx). Per alcuni aggiornamenti per la protezione può essere necessario disporre di diritti amministrativi ed eseguire il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare lo strumento Elevated Rights Deployment Tool, disponibile in [**SMS 2003 Administration Feature Pack**](http://red-sec-01/smserver/downloads/2003/adminpack.asp) e in [SMS 2.0 Administration Feature Pack](http://www.microsoft.com/smserver/downloads/20/featurepacks/adminpack)).
  
**QChain.exe e Update.exe:**
  
Lo strumento della riga di comando QChain.exe permette di concatenare in modo sicuro più aggiornamenti per la protezione. Il termine *concatenamento* indica la possibilità di installare più aggiornamenti senza riavviare il computer dopo ogni aggiornamento. Lo strumento Update.exe, utilizzato negli aggiornamenti descritti in questo bollettino, include funzionalità di concatenamento incorporate. Se si utilizza Windows 2000 Service Pack 2 o versione successiva, Windows XP oppure Windows Server 2003, non è necessario utilizzare QChain.exe per concatenare gli aggiornamenti. Qchain.exe supporta comunque il concatenamento anche di questi aggiornamenti di Windows, per consentire agli amministratori di creare uno script di deployment coerente per tutte le piattaforme. Per ulteriori informazioni su Qchain, visitare questo [sito Web](http://go.microsoft.com/fwlink/?linkid=21156).
  
**Microsoft Baseline Security Analyzer:**
  
Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito Web [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).
  
#### Altre informazioni:
  
**Ringraziamenti**
  
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato con noi al fine di proteggere i sistemi dei clienti:
  
-   Cesar Cerrudo di [Application Security Inc.](http://www.appsecinc.com/) per la segnalazione di un problema descritto nel bollettino [MS04-019](http://technet.microsoft.com/security/bulletin/ms04-019).  
-   Rafal Wojtczuk, un collaboratore di [Network Associates](http://www.nai.com/), per la segnalazione di un problema descritto nel bollettino [MS04-020](http://technet.microsoft.com/security/bulletin/ms04-020).  
-   Brett Moore di [Security-Assessment.com](http://www.security-assessment.com/) per la segnalazione di un problema descritto nel bollettino [MS04-022](http://technet.microsoft.com/security/bulletin/ms04-022).  
-   [Dustin Schneider](https://technet.microsoft.com/it-IT/mailto://dschn@verizon.net) per la segnalazione di un problema descritto nel bollettino [MS04-022](http://technet.microsoft.com/security/bulletin/ms04-022).  
-   Peter Winter-Smith di [Next Generation Security Software Ltd.](http://www.ngssoftware.com/) per la segnalazione di un problema descritto nel bollettino [MS04-022](http://technet.microsoft.com/security/bulletin/ms04-022).  
-   Brett Moore di Security-Assessment.com per la segnalazione di un problema descritto nel bollettino [MS04-023](http://technet.microsoft.com/security/bulletin/ms04-023).  
-   **Download di altri aggiornamenti per la protezione:**
  
    Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:
  
    -   Gli aggiornamenti per la protezione sono disponibili nel [Microsoft Download Center](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch".  
    -   Gli aggiornamenti per i sistemi consumer sono disponibili nel sito Web [Windows Update](http://go.microsoft.com/fwlink/?linkid=21130).
  
    **Supporto tecnico:**
  
    -   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Supporto tecnico Microsoft](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.  
    -   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Le chiamate al supporto tecnico relative agli aggiornamenti di protezione sono gratuite. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il [sito Web del supporto internazionale](http://go.microsoft.com/fwlink/?linkid=21155).
  
    **Fonti di informazioni sulla sicurezza:**
  
    -   Nella sezione dedicata alla sicurezza del sito Web [Microsoft TechNet](http://www.microsoft.com/italy/technet/security/default.mspx) sono disponibili ulteriori informazioni sulla protezione e la sicurezza dei prodotti Microsoft.  
    -   [Microsoft Software Update Services](http://go.microsoft.com/fwlink/?linkid=21133)  
    -   [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134) (MBSA)  
    -   [Windows Update](http://go.microsoft.com/fwlink/?linkid=21130)  
    -   Catalogo di Windows Update: Per ulteriori informazioni sul catalogo di Windows Update, vedere l'articolo della Microsoft Knowledge Base [323166](http://support.microsoft.com/default.aspx?scid=kb;en-us;323166).  
    -   [Office Update](http://go.microsoft.com/fwlink/?linkid=21135)
  
    **Dichiarazione di non responsabilità:**
  
    Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Conseguentemente, Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni punitivi o speciali, anche se Microsoft o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.
  
    **Versioni:**
  
    -   V1.0 (13 luglio 2004): pubblicazione del bollettino
  
*Built at 2014-04-18T01:50:00Z-07:00*
