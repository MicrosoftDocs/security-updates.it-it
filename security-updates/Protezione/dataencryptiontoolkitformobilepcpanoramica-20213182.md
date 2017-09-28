---
TOCTitle: 'Data Encryption Toolkit for Mobile PC: panoramica'
Title: 'Data Encryption Toolkit for Mobile PC: panoramica'
ms:assetid: 'abfc4696-a39a-43df-b559-133633e4bd5e'
ms:contentKeyID: 20213182
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162811(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC - Analisi della protezione
================================================================

### Panoramica

Pubblicato: 4 aprile 2007

Fino a qualche anno fa, i laptop erano ancora relativamente rari nella maggior parte delle organizzazioni. In genere, venivano forniti esclusivamente a chi viaggiava spesso e ai dirigenti. Oggi, i laptop sono più potenti che mai, ma sono anche molto diffusi. Non vengono più assegnati esclusivamente a determinate persone, bensì oltrepassano perfino il numero di desktop, in alcune organizzazioni. Poiché aumenta la capacità della memoria, diventano archivi di valore sempre più elevato per tutti i tipi di dati sensibili.

L'enorme aumento del numero di laptop è stato affiancato dal corrispondente aumento del numero di furti o perdite degli stessi. La protezione dei laptop costituisce un serio problema per la maggior parte delle grandi e medie imprese. Un recente studio condotto da The Ponemon Institute, "[Confidential Data at Risk](http://www.csoonline.com/read/080106/col_ponemon.html)", rileva che "l'81% delle 484 risposte al sondaggio riporta che nelle organizzazioni si sono verificate almeno una volta perdite o furti di laptop contenenti informazioni aziendali riservate o confidenziali negli ultimi 12 mesi". Sebbene i costi della sostituzione siano significativi, i costi diretti e indiretti di una violazione della protezione quando il disco rigido di un laptop rubato contiene dati sensibili o importanti possono essere decisamente superiori.

Alcune informazioni sono protette da leggi nazionali o federali, altre da leggi provinciali o regionali e altre ancora da normative del settore. Il numero di leggi, giurisdizioni e classificazioni di riservatezza sta aumentando insieme al numero di laptop. La perdita di un laptop può esporre un'organizzazione al pagamento di multe significative e responsabilità civile, in base alle misure preventive che venivano adottate. I costi diretti e indiretti conseguenti a una violazione della protezione comprendono la difficoltà di mantenere i clienti e la perdita di credibilità e reputazione.

Microsoft fornisce strumenti di protezione per i laptop. Se i dati contenuti in un laptop vengono crittografati in modo appropriato, è molto più difficile recuperare dati sensibili in caso di perdita o furto del laptop stesso. Utilizzando in modo appropriato Crittografia unità Microsoft® BitLocker™ (BitLocker) e Encrypting File System (EFS), i dati sensibili possono essere protetti contro un'ampia gamma di vettori di attacco tipico.

In questa guida, *Analisi della protezione di Microsoft Data Encryption Toolkit for Mobile PC*, vengono fornite informazioni dettagliate sui livelli di protezione che possono essere raggiunti utilizzando BitLocker ed EFS. Le edizioni Enterprise e Ultimate di Windows Vista™ supportano l'intera gamma di funzionalità descritte in questa guida e un sottogruppo significativo e utile è disponibile in Microsoft Windows® XP. Esistono diversi livelli di protezione, in base alle funzionalità e alle configurazioni applicate. Nella maggior parte delle configurazioni protette, chi effettua l'attacco necessita di una straordinaria quantità di risorse per decodificare i dati contenuti nel disco rigido.

*Analisi della protezione* ti consentirà di comprendere come le funzionalità in Windows Vista e Windows XP attenuano determinati rischi per la protezione nell'organizzazione. Questa guida ti sarà utile per fare quanto segue:

-   Identificare i vettori di minacce comuni e i rischi dell'ambiente.

-   Comprendere come attenuare rischi e minacce specifici utilizzando BitLocker ed EFS, singolarmente e insieme.

-   Preparare l'attenuazione delle minacce alla protezione che non possono essere affrontate da BitLocker o EFS.

-   Comprendere le funzionalità di protezione selezionate e la tecnologia fornita da Windows Vista.

Le funzionalità di protezione trattate in questa guida sono state sviluppate utilizzando le tecnologie note del settore. Ad esempio, l'implementazione Microsoft degli algoritmi di crittografia utilizzati per BitLocker ed EFS sono certificati in base allo standard pubblicato dal Governo degli Stati Uniti Federal Information Processing Standard (FIPS) 140-1 e gli algoritmi implementati risultano tutti conformi. Questa aderenza alle tecnologie note del settore è importante perché alcune leggi nazionali e statali sulla privacy dei dati prevedono esenzioni o riduzioni per le organizzazioni che dimostrano di essersi impegnate nell'adottare le procedure migliori per la protezione dei dati.

##### In questa pagina

[](#egaa)[Destinatari della guida](#egaa)
[](#efaa)[Contenuto del capitolo](#efaa)
[](#eeaa)[Convenzioni di stile](#eeaa)
[](#edaa)[Ulteriori informazioni](#edaa)
[](#ecaa)[Supporto e feedback](#ecaa)
[](#ebaa)[Ringraziamenti](#ebaa)

### Destinatari della guida

Questa guida è destinata agli specialisti della protezione, responsabili delle decisioni o dei suggerimenti sulla tecnologia e i criteri per una dozzina o migliaia di computer client, in particolare laptop. La tecnologia e le minacce correlate, generalmente, non sono applicabili a un utente privato o a una rete domestica. Se tra le responsabilità di tua competenza rientra quanto segue, sarebbe opportuno leggere questa guida:

-   Prendere decisioni o dare suggerimenti su criteri e tecnologia di protezione.

-   Implementare i criteri di protezione di client e server.

-   Valutare la tecnologia di protezione.

-   Integrare i criteri di protezione con altre tecnologie o criteri di gestione del computer.

Questa guida contiene informazioni avanzate e dettagliate e non si tratta di un manuale sulla protezione, la crittografia, i file system o altri argomenti fondamentali di protezione e amministrazione del sistema.

[](#mainsection)[Inizio pagina](#mainsection)

### Contenuto del capitolo

Questa sezione fornisce una panoramica dei capitoli contenuti in questa guida.

[Capitolo 1: Discussione sui rischi](http://technet.microsoft.com/it-it/library/cc162822.aspx) introduce le minacce alla protezione che possono essere affrontate da BitLocker ed EFS. Include anche una discussione sugli scenari utilizzati nella restante parte di *Analisi della protezione* in modo da fornire un modello più concreto per la discussione sui rischi e i vantaggi.

[Capitolo 2: Crittografia unità BitLocker](http://www.microsoft.com/italy/technet/security/guidance/clientsecurity/dataencryption/analysis/4e6ce820-fcac-495a-9f23-73d65d846638.mspx) tratta la tecnologia Crittografia unità BitLocker introdotta in Windows Vista. Illustra come utilizzare BitLocker per attenuare determinate minacce alla protezione descritte nel Capitolo 1 e riporta esempi di configurazione che è possibile utilizzare come punto di inizio per sviluppare un'adeguata implementazione BitLocker nell'organizzazione.

[Capitolo 3: Encrypting File System](http://technet.microsoft.com/it-it/library/cc162818.aspx) descrive il funzionamento di EFS e come è possibile utilizzarlo per attenuare determinate minacce nell'ambiente.

[Capitolo 4: Integrazione di BitLocker ed EFS](http://technet.microsoft.com/it-it/library/cc162807.aspx) illustra come combinare BitLocker ed EFS per attenuare le minacce in modo più efficace rispetto alle due tecnologie utilizzate singolarmente.

[Capitolo 5: Scelta della soluzione più adatta](http://technet.microsoft.com/it-it/library/cc162816.aspx) fornisce discussioni e strumenti per consentire agli specialisti della protezione di scegliere la combinazione appropriata di funzionalità ed elementi di configurazione per le organizzazioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

Questa guida utilizza le convenzioni di stile descritte nella tabella seguente.

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Significato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Testo in grassetto</strong></td>
<td style="border:1px solid black;">Caratteri digitati in grassetto (come nella colonna Elemento), inclusi comandi, switch e nomi di file. Anche gli elementi dell'interfaccia utente vengono visualizzati in grassetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>Testo in corsivo</em></td>
<td style="border:1px solid black;">I titoli dei libri e di altre pubblicazioni vengono visualizzati in <em>corsivo</em>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><em>&lt;Corsivo&gt;</em></td>
<td style="border:1px solid black;">I segnaposti in corsivo e tra parentesi angolari, ad esempio <em>&lt;nome file&gt;</em>, rappresentano le variabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><pre><code>Testo a spaziatura fissa</code></pre></td>
<td style="border:1px solid black;">Indica esempi di codice e script.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Nota</strong></td>
<td style="border:1px solid black;">Segnala la presenza di informazioni supplementari.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Importante</strong></td>
<td style="border:1px solid black;">Segnala la presenza di informazioni supplementari importanti.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
Oltre a questa *Analisi della protezione*, [Data Encryption Toolkit for Mobile PC](http://go.microsoft.com/fwlink/?linkid=86127) include altri documenti e strumenti utili:
  
-   La *Guida all'amministrazione e alla pianificazione* (Planning and Implementation Guide) illustra come pianificare e implementare BitLocker ed EFS per proteggere il PC portatile.
  
-   Lo strumento Microsoft Encrypting File System Assistant (EFS Assistant) consente di automatizzare il processo di rilevamento e crittografia dei file riservati su computer su cui sono in esecuzione Windows XP e Windows Vista.
  
-   La *Guida per amministratori di EFS Assistant* (EFS Assistant Administrator's Guide) spiega come gli amministratori possono distribuire e gestire lo strumento EFS Assistant su computer appartenenti al dominio per fornire una protezione adeguata a tutte le unità aziendali o all'intera azienda.
  
È possibile utilizzare tutte le risorse per consentire a coloro che devono prendere decisioni di acquisire una conoscenza e una comprensione approfondita delle problematiche relative alla protezione nelle reti Microsoft Windows. Un buon punto da cui iniziare è la pagina [Security Guidance](http://www.microsoft.com/technet/security/guidance/default.mspx) su Microsoft TechNet.
  
È possibile trovare suggerimenti specifici per soddisfare i requisiti di protezione della gestione di dominio nella [Guida alla procedura migliore per proteggere le installazioni di Windows Server Active Directory](http://www.microsoft.com/windowsserver2003/techinfo/overview/adsecurity.mspx) (Best Practice Guide for Securing Windows Server Active Directory Installations).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Supporto e feedback
  
Il team SASC (Solution Accelerators - Security and Compliance) è interessato a eventuali commenti e suggerimenti offerti su questa e altre soluzioni per la protezione. Invia commenti e suggerimenti a [secwish@microsoft.com](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet). Saremo lieti di sapere la tua opinione.
  
Solution Accelerators fornisce le indicazioni e l'automazione per l'integrazione tra prodotti. Fornisce, inoltre, strumenti e contenuti per pianificare, creare, distribuire e gestire il settore IT più facilmente. Per visualizzare la gamma di prodotti Solution Accelerators e per ulteriori informazioni, visita la pagina [Solution Accelerators](http://go.microsoft.com/fwlink/?linkid=51571) su Microsoft TechNet.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ringraziamenti
  
Il team SA-SC (Solution Accelerators - Security and Compliance) ringrazia il team che ha prodotto *Data Encryption Toolkit for Mobile PC - Analisi della protezione*. Il personale indicato di seguito è direttamente responsabile o ha apportato un contributo sostanziale alla redazione, allo sviluppo e al test di questa soluzione.
  
**Responsabili dello sviluppo**
  
Mike Smith-Lonergan - *Microsoft*
  
David Mowers - *Securitay, Inc.*
  
**Program Manager**
  
Bill Canning - *Microsoft*
  
**Sviluppatori dei contenuti**
  
Paul Flynn - *3Sharp, LLC*
  
Tommy Phillips - *Butternut Software*
  
Paul Robichaux - *3Sharp, LLC*
  
**Editor**
  
Steve Wacker - *Wadeware LLC*
  
**Revisori**
  
Vijay Bharadwaj - *Microsoft*
  
Tom Daemen - *Microsoft*
  
Mike Danseglio - *Microsoft*
  
Kurt Dillard - *Microsoft*
  
Jeff Hatfield - *Wireless Ink Inc.*
  
Erik Holt - *Microsoft*
  
Russell Humphries - *Microsoft*
  
David Kennedy - *Microsoft*
  
Douglas MacIver - *Microsoft*
  
Josh Phillips
  
Greg Petersen - *Avanade Inc.*
  
Ben Wilson - *ASG Group*
  
**Product Manager**
  
Alain Meeus - *Microsoft*
  
Jim Stuart - *Microsoft*
  
**Responsabile del rilascio**
  
Karina Larson - *Microsoft*
  
**Tester**
  
Gaurav Singh Bora - *Microsoft*
  
Sumit Ajitkumar Parikh - *Infosys Technologies Ltd.*
  
Swaminathan Viswanathan - *Infosys Technologies Ltd.*
  
Swapna Rangachari Jagannathan - *Infosys Technologies Ltd.*
  
Neethu Thomas - *Infosys Technologies Ltd.*
  
**Download**
  
[Get the Data Encryption Toolkit for Mobile PCs (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)
  
**Partecipa**
  
[Iscriviti per partecipare al programma Data Encryption Toolkit Beta](https://connect.microsoft.com/invitationuse.aspx?programid=790&invitationid=desa-r7gd-3f73&siteid=14)
  
**Notifiche di aggiornamento**
  
[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti**
  
[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet)
  
[](#mainsection)[Inizio pagina](#mainsection)
