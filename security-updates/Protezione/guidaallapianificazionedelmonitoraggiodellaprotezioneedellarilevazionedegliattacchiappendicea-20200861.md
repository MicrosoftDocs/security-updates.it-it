---
TOCTitle: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Appendice A'
Title: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Appendice A'
ms:assetid: '2a358239-864f-40aa-8427-45fed1a0c7c1'
ms:contentKeyID: 20200861
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536262(v=TechNet.10)'
---

Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi
==============================================================================================

### Appendice A - Esclusione degli eventi superflui

Aggiornato: 23 maggio 2005

Nella seguente tabella sono elencati gli eventi che in genere vengono esclusi dai controlli del monitoraggio della protezione perché si verificano molto raramente e non forniscono inoltre alcuna informazione utile.

**Nota: **l'esclusione di qualsiasi informazione da un controllo implica ovviamente un aumento del rischio. Questo aspetto, tuttavia, deve essere valutato rispetto alla frequenza degli eventi e al carico di lavoro risultante sull'agente di analisi.

**Tabella A.1. Riduzione del carico di lavoro sul sistema di archiviazione mediante la rimozione di eventi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Occorrenza</th>
<th style="border:1px solid black;" >Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">538</td>
<td style="border:1px solid black;">Fine sessione dell'utente</td>
<td style="border:1px solid black;">Questo evento non indica necessariamente il momento in cui l'utente ha smesso di utilizzare il computer. Se ad esempio l'utente spegne il computer senza prima disconnettersi oppure si verifica un'interruzione nella connessione di rete a una condivisione, è possibile che nel computer l'operazione di disconnessione non venga registrata affatto o che venga registrata solo quando il computer rileva che la connessione è interrotta.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">551</td>
<td style="border:1px solid black;">Disconnessione avviata dall'utente</td>
<td style="border:1px solid black;">Utilizzare l'evento 538, che consente di verificare la disconnessione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">562</td>
<td style="border:1px solid black;">Handle di oggetto chiuso</td>
<td style="border:1px solid black;">Questo evento viene sempre registrato come operazione riuscita.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">571</td>
<td style="border:1px solid black;">Contesto client eliminato da Gestione autorizzazioni</td>
<td style="border:1px solid black;">Si tratta di un evento normale quando si utilizza Gestione autorizzazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">573</td>
<td style="border:1px solid black;">Generazione di un evento di controllo non di sistema con API di autorizzazione (Authorization Application Programming Interface)</td>
<td style="border:1px solid black;">Comportamento normale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">577
578</td>
<td style="border:1px solid black;">Servizio privilegiato chiamato, operazione su un oggetto privilegiato</td>
<td style="border:1px solid black;">Questi eventi con volumi elevati in genere non contengono informazioni sufficienti per comprendere l'accaduto o per consentire di prendere decisioni operative.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">594</td>
<td style="border:1px solid black;">Handle di oggetto duplicato</td>
<td style="border:1px solid black;">Comportamento normale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">595</td>
<td style="border:1px solid black;">Accesso indiretto a un oggetto</td>
<td style="border:1px solid black;">Comportamento normale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">596</td>
<td style="border:1px solid black;">Backup della chiave master della protezione dati</td>
<td style="border:1px solid black;">Con le impostazioni predefinite, questo evento si verifica automaticamente ogni 90 giorni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">597</td>
<td style="border:1px solid black;">Ripristino della chiave master della protezione dati</td>
<td style="border:1px solid black;">Comportamento normale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">624
642</td>
<td style="border:1px solid black;">Evento 624 in cui il valore del campo <strong>Utente</strong> è <em>System</em>, seguito dall'evento 642 in cui il valore del campo <strong>Nome account di destinazione</strong> è <em>IUSR_machinename</em> o <em>IWAM_machinename</em> e il valore del campo <strong>Nome utente chiamante</strong> è <em>machinename$</em>.</td>
<td style="border:1px solid black;">Questa sequenza di eventi indica che un amministratore ha installato IIS nel computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">624
630
642</td>
<td style="border:1px solid black;">Il valore del campo <strong>Utente</strong> è <em>System</em> e tutti e tre gli eventi hanno lo stesso timestamp e il valore del campo <strong>Nome nuovo account/Nome account di destinazione</strong> è <em>HelpAssistant</em> e il valore del campo <strong>Nome utente chiamante</strong> è <em>DCname$</em></td>
<td style="border:1px solid black;">Questa sequenza di eventi viene generata quando un amministratore installa Active Directory in un computer su cui è in esecuzione Windows Server 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">624 o
642</td>
<td style="border:1px solid black;">Il valore del campo <strong>Utente</strong> è <em>ExchangeServername$</em> e il campo <strong>Nome account di destinazione</strong> contiene un identificatore univoco globale (GUID)</td>
<td style="border:1px solid black;">Questo evento si verifica la prima volta che un server di Exchange viene portato in linea generando automaticamente le cassette postali di sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">624</td>
<td style="border:1px solid black;">Il campo <strong>Nome utente chiamante</strong> contiene un qualsiasi utente e il valore del campo <strong>Nome nuovo account</strong> è <em>machinename$</em></td>
<td style="border:1px solid black;">Un utente del dominio ha creato o connesso un nuovo account del computer nel dominio. Questo evento è accettabile se gli utenti hanno la facoltà di aggiungere computer a un dominio. In caso contrario, è necessaria un'analisi approfondita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Il valore del campo <strong>Utente</strong> è <strong>System</strong>, il valore del campo <strong>Nome account di destinazione</strong> è <strong>TsInternetUser</strong> e il valore del campo <strong>Nome utente chiamante</strong> è in genere <strong>DCname$</strong></td>
<td style="border:1px solid black;">Si tratta di eventi normali in un computer su cui è in esecuzione Servizi terminal.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">672</td>
<td style="border:1px solid black;">Richiesta di ticket Kerberos AS</td>
<td style="border:1px solid black;">Se si ricevono eventi di accesso 528 e 540 da tutti i computer, è possibile che l'evento 672 non contenga alcuna informazione utile aggiuntiva, poiché registra semplicemente che è stato concesso un ticket Kerberos TGT. Affinché si verifichi un accesso, deve comunque esistere un ticket di servizio concesso (evento 673).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">680</td>
<td style="border:1px solid black;">Accesso account</td>
<td style="border:1px solid black;">Se si ricevono eventi di accesso 528 e 540 da tutti i computer, è possibile che l'evento 680 non contenga alcuna informazione utile aggiuntiva, poiché registra semplicemente la convalida delle credenziali dell'account. Un ulteriore evento di accesso registra le informazioni relative all'accesso effettuato dall'utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">697</td>
<td style="border:1px solid black;">Chiamata all'API di controllo criterio password</td>
<td style="border:1px solid black;">Comportamento normale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">768</td>
<td style="border:1px solid black;">Conflitto di spazio dei nomi nell'insieme di strutture</td>
<td style="border:1px solid black;">Evento non relativo alla protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">769
770
771</td>
<td style="border:1px solid black;">Aggiunta, eliminazione o modifica delle informazioni sull'insieme di strutture trusted</td>
<td style="border:1px solid black;">Questi eventi indicano un normale funzionamento dei trust tra insiemi di strutture. Non confondere questi eventi con l'aggiunta, l'eliminazione o la modifica del trust stesso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Da 832 a 841</td>
<td style="border:1px solid black;">Problemi vari relativi alla replica di Active Directory</td>
<td style="border:1px solid black;">Nessuna implicazione sulla protezione.</td>
</tr>
</tbody>
</table>
  
##### Download
  
[![](images/Dd536262.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41310)
  
[](#mainsection)[Inizio pagina](#mainsection)
