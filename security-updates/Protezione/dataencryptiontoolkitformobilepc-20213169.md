---
TOCTitle: Data Encryption Toolkit for Mobile PC
Title: Data Encryption Toolkit for Mobile PC
ms:assetid: '77403c60-81c4-48c4-b2ee-cbf410572bf0'
ms:contentKeyID: 20213169
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162808(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione
======================================================================================

### Panoramica

La distribuzione della crittografia dei dati in un'organizzazione richiede una consistente gestione delle valutazioni e una precedente pianificazione. In *Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione* vengono descritti i processi di pianificazione e implementazione da eseguire per utilizzare Crittografia unità BitLocker Microsoft (BitLocker) ed EFS (Encrypting File System) nella strategia di protezione dei dati sui PC portatili.

##### In questa pagina

[](#ehaa)[Rapida panoramica su BitLocker](#ehaa)  
[](#egaa)[Rapida panoramica su EFS](#egaa)  
[](#efaa)[Riepilogo dei capitoli](#efaa)  
[](#eeaa)[Destinatari della guida](#eeaa)  
[](#edaa)[Convenzioni di stile](#edaa)  
[](#ecaa)[Supporto e feedback](#ecaa)  
[](#ebaa)[Ringraziamenti](#ebaa)

### Rapida panoramica su BitLocker

BitLocker è una nuova, importante funzionalità di protezione del sistema operativo Windows Vista che fornisce una significativa protezione del sistema operativo e dei dati del computer. BitLocker è una tecnologia di crittografia completa dei volumi che consente di accertarsi che i dati non vengano rivelati se qualcuno tenta di alterare il computer quando il sistema operativo installato è offline. È più efficace su computer che dispongono di un BIOS e di un microchip TPM (Trusted Platform Module) compatibili poiché questi vengono utilizzati per fornire una maggiore protezione dei dati e per assicurare l'integrità dei componenti di avvio. BitLocker può facoltativamente utilizzare una chiave USB esterna come token per contenere la chiave di avvio.

[](#mainsection)[Inizio pagina](#mainsection)

### Rapida panoramica su EFS

EFS abilita una crittografia e decrittografia trasparente dei file utilizzando algoritmi crittografici su base standard. Qualsiasi individuo o programma che non disponga della chiave crittografica appropriata non può decrittografare i dati crittografati, anche se possiede fisicamente il computer in cui si trovano i file. Anche chi è autorizzato ad accedere al computer e al relativo file system non può visualizzare i dati.

EFS combina due tipi di crittografia: per proteggere i dati nel file viene utilizzato un codice simmetrico e per proteggere la chiave utilizzata nel codice simmetrico viene utilizzato un codice asimmetrico.

Il manuale *Distributed Systems Guide* del [Resource Kit di Windows 2000 Server](http://go.microsoft.com/fwlink/?linkid=458) include una panoramica completa di EFS e una serie di informazioni su EFS in Microsoft Windows 2000. Per trovare queste informazioni online, utilizzare il sommario del Resource Kit di Windows 2000 Server per andare al manuale *Distributed Systems Guide*, espandere **Distributed Security**, quindi scegliere **Encrypting File System**.

Ci sono alcune differenze tra EFS in Windows 2000, Windows XP Professional, Windows Server 2003 e Windows Vista. Il Resource Kit di Windows XP Professional illustra le differenze tra le implementazioni di EFS in Windows 2000 e Windows XP Professional e l'articolo "[Encrypting File System in Windows XP and Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=22413)" (in inglese) descrive quelle in Windows XP e Windows Server 2003. Le differenze tra EFS in Windows XP Professional e Windows Vista vengono descritte nel [Capitolo 2: attività di configurazione e distribuzione](http://technet.microsoft.com/it-it/library/cc162812.aspx) di questa guida.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo dei capitoli

I capitoli della *Guida alla pianificazione e all'implementazione* trattano i seguenti argomenti:

-   [Capitolo 1: considerazioni sulla pianificazione](http://technet.microsoft.com/it-it/library/cc162806.aspx). In questo capitolo vengono descritte le considerazioni sulla pianificazione associata alla distribuzione di Windows Vista BitLocker e di entrambi i tipi di EFS, incluse le operazioni di pianificazione che dovrebbero essere eseguite per valutare l'ambiente, decidere quali risorse devono essere protette e quali metodi di protezione siano più appropriati.

-   [Capitolo 2: attività di configurazione e distribuzione](http://technet.microsoft.com/it-it/library/cc162812.aspx). In questo capitolo vengono descritte specifiche attività di configurazione necessarie per la distribuzione. In queste attività rientra la scelta di una configurazione di BitLocker, la configurazione della crittografia del disco e l'impostazione degli oggetti Criteri di gruppo del servizio Active Directory per controllare e gestire il modo in cui l'organizzazione utilizza EFS. Le attività di configurazione descritte in questo capitolo sono, generalmente, attività di preparazione che vengono eseguite una sola volta per preparare l'ambiente alla distribuzione di BitLocker ed EFS. Inoltre, in questo capitolo vengono descritte le attività di distribuzione da eseguire su ogni computer per abilitare l'utilizzo di BitLocker ed EFS nell'ambiente. Potrebbe essere necessario, ad esempio, aggiornare il BIOS su alcuni computer per abilitarli a lavorare con BitLocker.

-   [Capitolo 3: operazioni e scenari di ripristino](http://technet.microsoft.com/it-it/library/cc162802.aspx). In questo capitolo viene trattato lo svolgimento delle operazioni dei computer protetti con BitLocker ed EFS. Ad esempio, vengono illustrati i metodi per soddisfare le esigenze di recupero dei dati dell'organizzazione nel caso in cui il materiale della chiave o i certificati vengano smarriti o compromessi.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

Questa guida è rivolta ai professionisti IT, responsabili del progetto, la pianificazione e l'implementazione delle reti di computer costituite da una dozzina o migliaia di computer client, in particolare laptop e Tablet PC. Se tra le responsabilità di propria competenza rientra quanto segue, sarebbe opportuno leggere questa guida:

-   Implementare i criteri di protezione di client e server.

-   Progettare e implementare la protezione o l'architettura di gestione dei sistemi.

-   Valutare la tecnologia di protezione.

-   Integrare i criteri di protezione con altre tecnologie o criteri di gestione del computer.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento</th>
<th style="border:1px solid black;" >Significato</th>
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
  
### Supporto e feedback
  
Il team SA-SC (Solution Accelerators – Security and Compliance) è interessato a eventuali commenti e suggerimenti offerti su questa e altre soluzioni per la protezione. Inviare commenti e suggerimenti a [secwish@microsoft.com](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc). Microsoft sarà lieta di conoscere le opinioni dei clienti.
  
Solution Accelerators fornisce le indicazioni e l'automazione per l'integrazione tra prodotti. Fornisce, inoltre, strumenti e contenuti per pianificare, creare, distribuire e gestire il settore IT più facilmente. Per visualizzare la gamma di prodotti Solution Accelerators e per ulteriori informazioni, visitare la pagina [Solution Accelerators](http://go.microsoft.com/fwlink/?linkid=51571) su Microsoft TechNet.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ringraziamenti
  
Il gruppo SA-SC ringrazia il team che ha prodotto *Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione*. I collaboratori indicati di seguito sono direttamente responsabili o hanno apportato un contributo sostanziale alla redazione, allo sviluppo e al test di questa guida.
  
**Responsabili dello sviluppo**
  
Mike Smith-Lonergan - *Microsoft*
  
David Mowers - *Securitay, Inc.*
  
**Program Manager**
  
Bill Canning - *Microsoft*
  
**Sviluppatori dei contenuti**
  
Roger A. Grimes - *Microsoft*
  
Paul Robichaux - *3Sharp, LLC*
  
**Editor**
  
Steve Wacker - *Wadeware LLC*
  
**Revisori**
  
Randy Armknecht - *Calamos Investments*
  
Vijay Bharadwaj - *Microsoft*
  
Marcus Bluestein - *Kraft Kennedy & Lesser, Inc.*
  
Dean Chen - *Waggener Edstrom Worldwide*
  
Tom Daemen - *Microsoft*
  
Mike Danseglio - *Microsoft*
  
Erik Holt - *Microsoft*
  
Russell Humphries - *Microsoft*
  
David Kennedy - *Microsoft*
  
Luca Lorenzini
  
Douglas MacIver - *Microsoft*
  
Sanjay Pandit - *Microsoft*
  
Greg Petersen - *Avanade*
  
Matt Setzer - *Microsoft*
  
Stan Shkolnik - *Deloitte Touche Tohmatsu*
  
Michael Trotman - *United States Postal Service (USPS)*
  
Richard Trusson - *Microsoft*
  
Mike Wolfe - *Microsoft*
  
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
  
[Download di Data Encryption Toolkit for Mobile PC (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)
  
**Notifiche di aggiornamento**
  
[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti**
  
[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=data%20encryption%20toolkit%20for%20mobile%20pc,%20guida%20alla%20pianificazione%20e%20all'implementazione%20di%20data%20encryption%20toolkit)
  
[](#mainsection)[Inizio pagina](#mainsection)
