---
TOCTitle: 'Capitolo 4: Criterio di base per un server membro'
Title: 'Capitolo 4: Criterio di base per un server membro'
ms:assetid: 'd28caa21-4ec2-4556-a92a-5aa8410df6da'
ms:contentKeyID: 20213204
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163121(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 4: Criterio di base per un server membro

##### In questa pagina

[](#ekaa)[Panoramica](#ekaa)
[](#ejaa)[Criteri di base per Windows Server 2003](#ejaa)
[](#eiaa)[Criteri controllo](#eiaa)
[](#ehaa)[Assegnazione dei diritti utente](#ehaa)
[](#egaa)[Opzioni di protezione](#egaa)
[](#efaa)[Registro eventi](#efaa)
[](#eeaa)[Voci di registro aggiuntive](#eeaa)
[](#edaa)[Gruppi con restrizioni](#edaa)
[](#ecaa)[Protezione del File System](#ecaa)
[](#ebaa)[Impostazioni di protezione aggiuntive](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo descrive i requisiti di configurazione per gestire un modello di protezione base per tutti i server con Microsoft Windows Server 2003 con Service Pack 1 (SP1). Vengono fornite, inoltre, indicazioni di carattere amministrativo per l’impostazione e la configurazione di un sistema Windows Server 2003 con SP1 protetto nei tre ambienti aziendali. I requisiti di configurazione in questo capitolo costituiscono la base per tutte le procedure descritte nei capitoli seguenti. Tali capitoli descrivono come offrire una maggior protezione a specifici ruoli server.

I consigli sulle impostazioni contenuti in questo capitolo consentono di stabilire una base solida e sicura per i server delle applicazioni aziendali negli ambienti aziendali. Tuttavia, prima di implementare queste configurazioni di protezione negli ambienti di produzione, è necessario testare in modo esauriente gli effetti della compresenza di tali configurazioni e delle applicazioni aziendali nell’organizzazione.

I suggerimenti contenuti in questo capitolo sono adatti alla maggior parte delle organizzazioni e possono essere distribuiti sui computer esistenti o nuovi che utilizzano Windows Server 2003 con SP1. Le configurazioni di protezione predefinite di Windows Server 2003 con SP1 sono state analizzate, verificate e testate dal team che ha creato questa guida. Per informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata nel presente capitolo, fare riferimento alla guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo <http://technet.microsoft.com/it-it/library/dd162275>. Generalmente, la maggior parte delle seguenti configurazioni suggerite offre una maggior protezione rispetto alle impostazioni predefinite.

Le impostazioni di protezione descritte nel presente capitolo riguardano i seguenti tre ambienti:

-   **Legacy Client (LC).** Quest'ambiente comprende computer con Windows NT 4.0 e Microsoft Windows 98, a cui a volte si fa riferimento chiamandoli sistemi operativi *precedenti.* Sebbene quest'ambiente fornisca protezione adeguata, è il meno sicuro tra tutti gli ambienti definiti in questa guida. Per fornire maggiore protezione, le organizzazioni possono scegliere di passare al più sicuro ambiente Client di organizzazione. Oltre ai sistemi operativi precedenti descritti, l'ambiente LC comprende le workstation Windows 2000 Professional e Windows XP Professional. Quest'ambiente comprende soltanto controller di dominio Windows 2000 o Windows Server 2003. In questo ambiente non vi sono controller di dominio Windows NT 4.0, mentre possono essere presenti server membri Windows NT.

-   **Enterprise Client (EC).** Quest'ambiente fornisce un'alta protezione ed è progettato per le versioni più recenti del sistema operativo Windows. L'ambiente EC comprende computer client con Windows 2000 Professional e Windows XP Professional. La maggior parte del lavoro necessario per passare dall'ambiente LC all'ambiente EC comprende aggiornamenti di client legacy, ad esempio aggiornamenti da workstation Windows 98 e Windows NT 4.0 a Windows 2000 o Windows  XP. Tutti controller di dominio e i server membri in quest'ambiente utilizzano Windows 2000 Server o Windows Server 2003.

-   **Specialized Security – Limited Functionality (SSLF)**. Quest'ambiente fornisce una protezione molto superiore rispetto all'ambiente EC. La migrazione dall'ambiente EC all'ambiente SSLF (Specialized Security – Limited Functionality) richiede la conformità a severi criteri di protezione per i computer client e server. Questo ambiente comprende computer client con Windows 2000 Professional e Windows XP Professional, e controller di dominio con Windows 2000 Server o Windows Server 2003. Nell'ambiente SSLF, i rischi per la protezione sono così grandi che la perdita significativa di funzionalità client e di facilità di gestione sono considerate un compromesso accettabile al fine di conseguire i più alti livelli di protezione. I server membri in quest'ambiente utilizzano Windows 2000 Server o Windows Server 2003.

In molti casi l'ambiente SSLF imposterà esplicitamente il valore predefinito. Si presuppone che questa configurazione avrà effetti sulla compatibilità, perché la modifica di impostazioni locali da parte di alcune applicazioni potrebbe non riuscire. Per esempio, alcune applicazioni hanno bisogno di modificare i diritti di utente per concedere privilegi aggiuntivi al proprio account di servizio. Poiché i Criteri di gruppo hanno precedenza sui criteri del computer locale, tali operazioni non avranno successo. Verificare attentamente tutte le applicazioni prima di distribuire una delle impostazioni consigliate sui computer di produzione, soprattutto le impostazioni SSLF.

La figura seguente mostra i tre ambienti di protezione ed i client che ciascuno supporta.

[![](images/Cc163121.sgfg0401(it-it,TechNet.10).jpg "Figura 4.1 Ambienti di protezione esistenti e previsti")](https://technet.microsoft.com/it-it/cc163121.sgfg0401_big(it-it,technet.10).gif)

**Figura 4.1 Ambienti di protezione esistenti e previsti**

Le organizzazioni che vogliono proteggere i propri ambienti mediante un approccio graduale possono scegliere di iniziare al livello di ambiente client legacy e quindi di passare gradualmente verso ambienti più sicuri, mentre nel contempo aggiornano e verificano le proprie applicazioni e i computer client con impostazioni di sicurezza più severe.

La figura seguente mostra l’utilizzo dei modelli di protezione (file .inf) come base per i criteri di protezione di base dei server membro (MSBP, Member Server Baseline Policy) nell'ambiente Client di organizzazione. La figura mostra inoltre un modo per collegare questo criterio e applicarlo a tutti i server in un'organizzazione.

Windows Server 2003 con SP1 viene consegnato con valori predefiniti impostati su un livello di protezione elevato. In molti casi, questo capitolo prescrive impostazioni diverse dai valori predefiniti. Il capitolo suggerisce inoltre valori predefiniti specifici per tutti i tre ambienti. Queste informazioni sono riportate nella guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), all'indirizzo http://technet.microsoft.com/it-it/library/dd162275.

[![](images/Cc163121.sgfg0402(it-it,TechNet.10).gif "Figura 4.2 Il modello di protezione EC-Member Server Baseline.inf viene importato nei criteri MSBP, i quali vengono collegati all’unità organizzativa (OU, Organizational Unit) Server membri")](https://technet.microsoft.com/it-it/cc163121.sgfg0402_big(it-it,technet.10).gif)

**Figura 4.2 Il modello di protezione EC-Member Server Baseline.inf viene importato nei criteri MSBP, i quali vengono collegati all’unità organizzativa (OU, Organizational Unit) Server membri**

Le procedure per migliorare la protezione di ruoli server specifici sono definite nei capitoli seguenti di questa guida. I ruoli server primari descritti in questa guida comprendono:

-   Controller di dominio che contengono servizi DNS

-   Server infrastruttura che contengono servizi WINS e DHCP

-   File server

-   Server di stampa

-   Web server che eseguono IIS (Internet Information Services)

-   Server IAS (Microsoft Internet Authentication Server)

-   Server Servizi certificati (CA)

-   Host Bastion

Molte delle impostazioni che compaiono nei criteri MSBP dell'ambiente Client di organizzazione descritto di seguito sono valide anche per questi ruoli di server nei tre ambienti definiti in questa guida. I modelli di protezione sono stati progettati specificatamente per rispondere alle esigenze di protezione dei singoli ambienti. La tabella seguente mostra i nomi dei modelli di protezione di base per i tre ambienti.

**Tabella 4.1 Modelli di protezione di base per i tre ambienti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">LC-Member Server Baseline.inf</td>
<td style="border:1px solid black;">EC-Member Server Baseline.inf</td>
<td style="border:1px solid black;">SSLF-Member Server Baseline.inf</td>
</tr>
</tbody>
</table>
  
Nel resto del presente capitolo sono descritte le impostazioni di protezione comuni a tutti i tre ambienti e quindi tutti i modelli di protezione di **base per server membro**.
  
I modelli di protezione di base sono inoltre la base per i modelli di protezione dei controller di dominio descritti nel Capitolo 5, "Criterio di base per il controller di dominio". I modelli di protezione del **Ruolo controller di dominio** comprendono le impostazioni di base per il GPO Criterio di gruppo controller di dominio, che è collegato all'OU dei controller di dominio in tutti i tre ambienti. Il capitolo 2 "Meccanismi di protezione avanzata di Windows Server 2003" fornisce istruzioni dettagliate per la creazione di OU e Criteri di gruppo e per l'importazione del modello di protezione appropriato in ciascun GPO.
  
**Nota**: alcune procedure utilizzate per offrire maggior protezione ai server non possono essere automatizzate mediante i Criteri di gruppo. Queste procedure sono descritte nella sezione "Impostazioni di protezione aggiuntive" di questo capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criteri di base per Windows Server 2003
  
Le impostazioni a livello OU del server membro definiscono le impostazioni comuni per tutti i ruoli di server membro trattati in questa guida. Per applicare queste impostazioni, è possibile creare un GPO collegato all'OU del server membro, detto criterio di base. L’oggetto Criteri di gruppo consente di configurare automaticamente le impostazioni di protezione specifiche per ogni server. Sarà necessario spostare gli account server alle OU figlio appropriate del server membro OU in base al ruolo di ciascun server.
  
Le impostazioni seguenti vengono descritte così come compaiono nell'interfaccia utente dello snap-in Editor di configurazione della protezione (SCE) del Microsoft Management Console (MMC).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criteri controllo
  
Gli amministratori dovrebbero creare un criterio di controllo che definisca quali eventi di protezione sono riferiti e che registri l'attività dell'utente o del computer nell'ambito di categorie evento definite. Gli amministratori possono controllare l'attività legata alla protezione, ad esempio chi accede a un oggetto, quando un utente effettua l'accesso o si disconnette da un computer, o se vengono apportate modifiche a un'impostazione di criterio di controllo.
  
Prima di implementare un criterio di controllo, decidere quali categorie evento controllare per l'ambiente. Le impostazioni di controllo scelte da un amministratore per le categorie di eventi definiscono i criteri di controllo dell'organizzazione. Una volta definite le impostazioni di controllo per specifiche categorie di eventi, gli amministratori possono creare criteri di controllo idonei alle esigenze di protezione dell'organizzazione.
  
Se non esiste alcun criterio di controllo, è difficile o impossibile stabilire le cause e le dinamiche di eventuali problemi di protezione. Tuttavia, se le impostazioni di controllo sono configurate in modo che molte attività autorizzate generino eventi, il registro di protezione si riempirà di dati inutili. I seguenti suggerimenti e le descrizioni di impostazioni sono forniti per meglio determinare cosa controllare in modo che i dati raccolti siano pertinenti.
  
Le informazioni relative alle operazioni non riuscite offrono spesso più informazioni rispetto alle operazioni riuscite, in quanto di solito indicano errori. Ad esempio, l'accesso riuscito a un computer viene considerato normale. Tuttavia, se vi sono molti tentativi di accesso al computer non riusciti, può significare che qualcuno sta tentando di introdursi nel computer utilizzando le credenziali dell'account di un altro utente. Nei registri eventi vengono registrati gli eventi del sistema. Nei sistemi operativi Microsoft Windows, sono presenti registri di evento separati per le applicazioni, gli eventi di protezione e gli eventi di sistema. Nel Registro di protezione vengono registrati gli eventi di controllo. Il contenitore Registro eventi di Criteri di gruppo viene utilizzato per definire gli attributi relativi ai registri eventi per le applicazioni, la protezione e il sistema, quali la dimensione massima del registro, i diritti di accesso e le impostazioni e i criteri di gestione.
  
Prima di implementare un criterio di controllo, le organizzazioni dovrebbero determinare come raccogliere, organizzare ed analizzare i dati. I grandi volumi di dati di controllo sono inutili se non si sa come utilizzarli. Inoltre, quando le reti di computer sono sottoposte a un controllo, le prestazioni possono risentirne. L'effetto di una determinata combinazione di impostazioni può risultare trascurabile sul computer di un utente finale, mentre può risultare significativo su un server con un notevole carico di lavoro. È pertanto consigliabile eseguire alcune prove sulle prestazioni prima di implementare nuove impostazioni di controllo nell'ambiente di produzione.
  
Nella tabella seguente sono inclusi i consigli per l'impostazione dei criteri di controllo per i tre tipi di ambienti definiti in questa guida. Si osservi che nella maggior parte dei valori le impostazioni sono simili per i tre ambienti. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
È possibile configurare i valori di questa impostazione del criterio di controllo in Windows Server 2003 con SP1 alla posizione seguente nell'ambito dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali**  
**\\Criteri di controllo**
  
Per un riepilogo delle impostazioni richieste illustrate in questa sezione, vedere la cartella di lavoro di Microsoft Excel con le impostazioni della "Windows Server 2003 Security Guide Settings" allegata alla versione scaricabile di questa guida. Per ulteriori informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata nella presente sezione, fare riferimento alla guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo <http://technet.microsoft.com/it-it/library/dd162275>.
  
**Tabella 4.2 Impostazioni del Criterio Controllo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controlla eventi accesso account</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazioni riuscite Operazioni non riuscite</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla gestione degli account</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazioni riuscite Operazioni non riuscite</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla eventi di accesso</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazioni riuscite Operazioni non riuscite</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla accesso agli oggetti</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Modifica del criterio di controllo</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla uso dei privilegi</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controlla tracciato processo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
<td style="border:1px solid black;">Nessun controllo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controlla eventi di sistema</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Operazione riuscita</td>
</tr>
</tbody>
</table>
  
#### Controlla eventi accesso account
  
Questa impostazione di criterio consente di controllare ogni istanza delle operazioni di connessione o disconnessione da un altro computer che convalida l'account. L'autenticazione di un account utente di dominio su un controller di dominio genera un evento di accesso account che viene registrato nel registro di protezione del controller di dominio. L'autenticazione di un utente locale su un computer locale genera un evento di accesso che viene registrato nel registro di protezione locale. Nessun evento di chiusura di sessione di account viene registrato.
  
L'impostazione **Controlla eventi accesso account** è configurata in modo da registrare i valori di **Operazioni riuscite** dei criteri di base LC ed EC, e da registrare gli eventi **Operazioni riuscite** e **Operazioni non riuscite** per il criterio di base SSLF.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione. Questi ID di evento possono essere utili quando si desidera creare avvisi personalizzati per controllare qualunque suite di software, come Microsoft Operations Manager (MOM).
  
**Tabella 4.3 Eventi di accesso account**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">672</td>
<td style="border:1px solid black;">Un ticket del servizio di autenticazione (AS, Authentication Service) è stato emesso e convalidato correttamente. In Windows Server 2003 con SP1, il tipo di quest'evento sarà Success Audit per le richieste completate con successo o Failure Audit per le richieste non riuscite.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">673</td>
<td style="border:1px solid black;">È stato concesso un ticket TGS (Ticket Granting Service). Un TGS è un ticket rilasciato da TGS di Kerberos versione 5 che consente a un utente di autenticarsi per uno specifico servizio del dominio. Windows Server 2003 con SP1 registrerà le operazioni riuscite e non riuscite per questo tipo evento.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">674</td>
<td style="border:1px solid black;">Un'identità di protezione ha rinnovato un ticket AS o TGS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">675</td>
<td style="border:1px solid black;">Preautenticazione non riuscita. L'evento viene generato in un centro distribuzione chiavi (KDC) quando un utente immette una password non corretta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">676</td>
<td style="border:1px solid black;">Richiesta ticket autenticazione non riuscita. Questo evento non è generato da Windows Server 2003 con SP1. Altre versioni di Windows utilizzano questo evento per indicare un'autenticazione non riuscita che non è dovuta a credenziali non corrette.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">677</td>
<td style="border:1px solid black;">Non è stato concesso un ticket TGS. Questo evento non è generato da Windows Server 2003 con SP1, che in questo caso usa un evento di controllo non riuscito con l'ID 672.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">678</td>
<td style="border:1px solid black;">Un account è stato mappato in modo corretto a un account del dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">681</td>
<td style="border:1px solid black;">Errore durante l'accesso. È stato tentato un accesso account di dominio. Quest'evento è generato soltanto dai controller di dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">682</td>
<td style="border:1px solid black;">Un utente si è riconnesso a una sessione di server terminal disconnessa.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">683</td>
<td style="border:1px solid black;">Un utente ha terminato una sessione Terminal Server senza chiudere correttamente la connessione.</td>
</tr>
</tbody>
</table>
  
#### Controlla gestione degli account
  
Questa impostazione del criterio determina se controllare ogni evento di gestione di account sul computer. Esempi di eventi di gestione di account sono:
  
-   Creazione, modifica o eliminazione di un account utente o di un gruppo.
  
-   Ridenominazione, disattivazione o attivazione di un account utente.
  
-   Impostazione o modifica di una password.
  
Le organizzazioni devono sapere chi crea, modifica o elimina account di dominio e account locali. Infatti, l’esistenza di modifiche non autorizzate potrebbe essere il risultato di errori fatti da un amministratore che non ha capito come applicare i criteri dell'organizzazione oppure di un attacco intenzionale.
  
Ad esempio, gli eventi che indicano operazioni non riuscite nella gestione degli account spesso segnalano che un amministratore di livello basso, oppure un pirata informatico che ha compromesso l’account di un amministratore di livello basso, sta cercando di elevare il suo privilegio. I registri possono consentire di determinare quali account sono stati modificati o creati da un pirata informatico.
  
L'impostazione **Controlla gestione degli account** è configurata in modo da registrare i valori di **Operazioni riuscite** dei criteri di base LC ed EC e da registrare gli eventi **Operazioni riuscite** e **Operazioni non riuscite** per il criterio di base SSLF.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione. Questi ID di evento possono essere utili quando si desidera creare avvisi personalizzati per controllare qualunque suite di software, come Microsoft Operations Manager (MOM). La maggior parte dei software di gestione dei processi operativi può essere personalizzata con script che catturino o contrassegnino gli eventi basati su tali ID evento.
  
**Tabella 4.4 Eventi di gestione degli account**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">624</td>
<td style="border:1px solid black;">Creazione di un account utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Modifica di una password utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">628</td>
<td style="border:1px solid black;">Impostazione di una password utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">630</td>
<td style="border:1px solid black;">Eliminazione di un account utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">631</td>
<td style="border:1px solid black;">Creazione di un gruppo globale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">632</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo globale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">633</td>
<td style="border:1px solid black;">Rimozione di un membro da un gruppo globale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">634</td>
<td style="border:1px solid black;">Eliminazione di un gruppo globale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">635</td>
<td style="border:1px solid black;">Creazione di un nuovo gruppo locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">636</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo locale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">637</td>
<td style="border:1px solid black;">Rimozione di un membro da un gruppo locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">638</td>
<td style="border:1px solid black;">Eliminazione di un gruppo locale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">639</td>
<td style="border:1px solid black;">Modifica dell'account di un gruppo locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">641</td>
<td style="border:1px solid black;">Modifica dell'account di un gruppo globale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">642</td>
<td style="border:1px solid black;">Modifica di un account utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">643</td>
<td style="border:1px solid black;">Modifica di un criterio di dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">644</td>
<td style="border:1px solid black;">Blocco automatico di un account utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">645</td>
<td style="border:1px solid black;">Creazione di un account di computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">646</td>
<td style="border:1px solid black;">Modifica di un account di computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">647</td>
<td style="border:1px solid black;">Eliminazione di un account di computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">648    </td>
<td style="border:1px solid black;">Creazione di un gruppo di protezione locale con protezione disabilitata.
<strong>Nota</strong>: la presenza di SECURITY_DISABLED nel nome formale indica che il gruppo non può essere utilizzato per concedere autorizzazioni nei controlli di accesso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">649</td>
<td style="border:1px solid black;">Modifica di un gruppo di protezione locale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">650</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo di protezione locale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">651</td>
<td style="border:1px solid black;">Eliminazione di un membro da un gruppo di protezione locale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">652</td>
<td style="border:1px solid black;">Eliminazione di un gruppo locale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">653</td>
<td style="border:1px solid black;">Creazione di un gruppo globale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">654</td>
<td style="border:1px solid black;">Modifica di un gruppo globale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">655</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo globale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">656</td>
<td style="border:1px solid black;">Rimozione di un membro da un gruppo globale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">657</td>
<td style="border:1px solid black;">Eliminazione di un gruppo globale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">658</td>
<td style="border:1px solid black;">Creazione di un gruppo universale con protezione abilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">659</td>
<td style="border:1px solid black;">Modifica di un gruppo universale con protezione abilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">660</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo universale con protezione abilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">661</td>
<td style="border:1px solid black;">Rimozione di un membro da un gruppo universale con protezione abilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">662</td>
<td style="border:1px solid black;">Eliminazione di un gruppo universale con protezione abilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">663</td>
<td style="border:1px solid black;">Creazione di un gruppo universale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">664</td>
<td style="border:1px solid black;">Modifica di un gruppo universale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">665</td>
<td style="border:1px solid black;">Aggiunta di un membro a un gruppo universale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">666</td>
<td style="border:1px solid black;">Rimozione di un membro da un gruppo universale con protezione disabilitata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">667</td>
<td style="border:1px solid black;">Eliminazione di un gruppo universale con protezione disabilitata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">668</td>
<td style="border:1px solid black;">Modifica di un tipo di gruppo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">684    </td>
<td style="border:1px solid black;">Impostazione del descrittore di protezione dei membri del gruppo amministrativo.
<strong>Nota</strong>: nei controller di dominio ogni 60 minuti un thread in background esegue la ricerca di tutti i membri dei gruppi amministrativi, ad esempio amministratori di dominio, dell'organizzazione e di schema, ai quali viene applicato un descrittore di protezione fisso. L'evento viene registrato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">685</td>
<td style="border:1px solid black;">Modifica del nome di un account.</td>
</tr>
</tbody>
</table>
  
#### Controlla eventi di accesso
  
Questa impostazione di criterio determina se controllare ogni istanza di apertura e chiusura del computer. L’impostazione **Controlla eventi di accesso** consente nei controller di dominio di monitorare l’attività degli account di dominio e nei computer locali di monitorare l’attività degli account locali.
  
Se si configura l'impostazione **Controlla eventi di accesso** su **Nessun controllo**, è difficile o impossibile determinare quale utente ha effettuato o tentato di effettuare l'accesso ai computer dell'organizzazione. Se si attiva il valore **Operazioni riuscite** per l'impostazione **Controlla eventi di accesso** su un membro di dominio, sarà generato un evento ogni volta che qualcuno accede alla rete, a prescindere da dove gli account risiedano sulla rete. Se l’utente accede a un account locale e **Controlla eventi accesso account** è impostata su **Abilitato,** l’accesso da parte dell’utente genera due eventi.
  
Anche se i valori predefiniti per questa impostazione di criterio non sono modificati, dopo un problema di protezione non sarà possibile raccogliere alcuna prova basata sui record di controllo. L'impostazione **Controlla eventi di accesso** è configurata in modo da registrare i valori di **Operazioni riuscite** dei criteri di base LC ed EC, e da registrare gli eventi **Operazioni riuscite** e **Operazioni non riuscite** per il criterio SSLF.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione.
  
**Tabella 4.5 Controlla eventi di accesso    **

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528</td>
<td style="border:1px solid black;">Accesso utente eseguito correttamente a un computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Errore durante l'accesso. Tentativo di accesso con un nome utente sconosciuto o con un nome utente conosciuto e una password non valida.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">530</td>
<td style="border:1px solid black;">Errore durante l'accesso. Tentativo di accesso oltre il tempo consentito.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">531</td>
<td style="border:1px solid black;">Errore durante l'accesso. È stato eseguito un tentativo di accesso con un account disabilitato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">532</td>
<td style="border:1px solid black;">Errore durante l'accesso. È stato eseguito un tentativo di accesso con un account scaduto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">533</td>
<td style="border:1px solid black;">Errore durante l'accesso. Tentativo di accesso da parte di un utente non autorizzato a connettersi al computer specificato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Errore durante l'accesso. L'utente ha tentato di accedere con un tipo di password non consentito.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">535</td>
<td style="border:1px solid black;">Errore durante l'accesso. La password per l'account specificato è scaduta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">536</td>
<td style="border:1px solid black;">Errore durante l'accesso. Il servizio Accesso rete non è attivo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">537    </td>
<td style="border:1px solid black;">Errore durante l'accesso. Il tentativo di accesso non è riuscito per altri motivi.
<strong>Nota:</strong> in alcuni casi la ragione per cui un tentativo di accesso non riesce può non essere nota.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">538</td>
<td style="border:1px solid black;">Processo di disconnessione completato per un utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">539</td>
<td style="border:1px solid black;">Errore durante l'accesso. L'account era bloccato al momento del tentativo di accesso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">540</td>
<td style="border:1px solid black;">Accesso riuscito di un utente a una rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">541</td>
<td style="border:1px solid black;">È stata completata l'autenticazione della modalità principale Internet Key Exchange (IKE) tra il computer locale e l'identità peer elencata (stabilendo un'associazione di protezione) o è stato stabilito un canale dati in modalità rapida.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">542</td>
<td style="border:1px solid black;">Chiusura di un canale dati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">543    </td>
<td style="border:1px solid black;">Interruzione della modalità principale.
<strong>Nota:</strong> l'evento può dipendere dalla scadenza del limite di tempo per l'associazione di protezione (che per impostazione predefinita è di otto ore), da modifiche ai criteri o dall'interruzione del peer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">544</td>
<td style="border:1px solid black;">Autenticazione della modalità principale non riuscita perché il peer non ha fornito un certificato valido o la firma non è stata convalidata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">545</td>
<td style="border:1px solid black;">Autenticazione della modalità principale non riuscita a causa di un errore del protocollo di autenticazione Kerberos o di una password non valida.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">546</td>
<td style="border:1px solid black;">Non è stato possibile stabilire l'associazione di protezione IKE perché il peer ha inviato una proposta non valida. È stato ricevuto un pacchetto contenente dati non validi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">547</td>
<td style="border:1px solid black;">Errore durante un handshake IKE.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">548</td>
<td style="border:1px solid black;">Errore durante l'accesso. L'identificatore di protezione (SID) di un dominio trusted non corrisponde al SID di protezione del dominio account del client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">549</td>
<td style="border:1px solid black;">Errore durante l'accesso. Tutti i SID corrispondenti a spazi dei nomi non attendibili sono stati esclusi dal filtro durante un'autenticazione tra insiemi di strutture.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">550</td>
<td style="border:1px solid black;">Messaggio di notifica che potrebbe indicare un attacco di tipo &quot;Denial of Service&quot; (DoS).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">551</td>
<td style="border:1px solid black;">Processo di disconnessione avviato da un utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">552</td>
<td style="border:1px solid black;">Accesso a un computer tramite credenziali esplicite effettuato da un utente già connesso come altro utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">682</td>
<td style="border:1px solid black;">Un utente si è riconnesso a una sessione di server terminal disconnessa.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">683    </td>
<td style="border:1px solid black;">Un utente ha terminato una sessione Terminal Server senza chiudere correttamente la connessione.
<strong>Nota:</strong> l'evento viene generato quando un utente è connesso a una sessione di server terminal dalla rete. Viene visualizzato in Terminal Server.</td>
</tr>
</tbody>
</table>
 

#### Controlla accesso agli oggetti

Di per sé questa impostazione non comporta il controllo di alcun evento. L'impostazione **Controlla accesso agli oggetti** determina se controllare l'evento di un utente che tenta l'accesso a un oggetto, ad esempio un file, una cartella, una chiave del registro di sistema o a una stampante, al quale è associato un elenco di controllo accesso di sistema (SACL).

In un SACL sono presenti le voci di controllo degli accessi (ACE, Access Control Entry). Ciascun ACE contiene tre informazioni:

-   L’identità di protezione (utente, computer o gruppo) da controllare.

-   Il tipo di accesso da controllare, ovvero la maschera di accesso.

-   Un contrassegno che indica se devono essere controllati gli eventi relativi agli accessi non riusciti, gli eventi relativi agli accessi riusciti o entrambi.

Se si configura l'impostazione **Controlla accesso agli oggetti** su **Operazioni riuscite**, ogni volta che un utente riesce ad accedere a un oggetto per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento riuscito. Se si configura l'impostazione su **Operazioni non riuscite**, ogni volta che un utente non riesce ad accedere a un oggetto per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento non riuscito.

Quando si configurano gli elenchi di controllo di accesso di sistema, le organizzazioni devono definire solo le azioni che è necessario abilitare. Ad esempio, potrebbe essere utile abilitare l'impostazione **Write and Append Data auditing** per tenere traccia delle sostituzioni o modifiche apportate ai file eseguibili, che sono di norma il bersaglio di virus, worm e cavalli di Troia. Analogamente, può essere utile tenere traccia degli accessi e delle modifiche apportate a documenti riservati.

L'impostazione **Controlla accesso agli oggetti** è configurata per impostazione predefinita su **Nessun controllo** nei criteri di base degli ambienti LC ed EC. Tuttavia, questa impostazione di criteri è configurata per registrare i valori **Operazioni non riuscite** nel criterio di base per l'ambiente SSLF.

La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione.

**Tabella 4.6 Eventi di accesso oggetti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">560</td>
<td style="border:1px solid black;">È stato concesso l'accesso a un oggetto esistente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">562</td>
<td style="border:1px solid black;">Un handle a un oggetto è stato chiuso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">563    </td>
<td style="border:1px solid black;">È stato eseguito un tentativo di apertura di un oggetto con l'intento di eliminarlo
<strong>Nota:</strong> questo evento è utilizzato nei file system quando in Createfile() viene specificato il flag FILE_DELETE_ON_CLOSE.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">564</td>
<td style="border:1px solid black;">È stato eliminato un oggetto protetto.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">565</td>
<td style="border:1px solid black;">L'accesso è stato concesso a un tipo di oggetto che esiste già.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">567    </td>
<td style="border:1px solid black;">Utilizzo di un'autorizzazione associata a un handle.
<strong>Nota</strong>: gli handle vengono creati con determinate autorizzazioni, ad esempio Lettura o Scrittura. Quando l'handle viene utilizzato, può essere generato un controllo per ciascuna autorizzazione utilizzata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">568</td>
<td style="border:1px solid black;">Tentativo di creazione di un collegamento fisso a un file di cui è in corso il controllo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">569</td>
<td style="border:1px solid black;">Tentativo di creazione di un contesto client da parte del gestore delle risorse di Gestione autorizzazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">570    </td>
<td style="border:1px solid black;">Tentativo di un client di accedere a un oggetto.
<strong>Nota:</strong> verrà generato un evento per ogni operazione tentata sull'oggetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">571</td>
<td style="border:1px solid black;">L'applicazione Gestione autorizzazioni ha eliminato il contesto client.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">572</td>
<td style="border:1px solid black;">Applicazione inizializzata dal gestore di amministrazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">772</td>
<td style="border:1px solid black;">Gestione certificati ha negato una richiesta di certificati in sospeso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">773</td>
<td style="border:1px solid black;">Servizi certificati ha ricevuto una richiesta di certificati nuovamente inoltrata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">774</td>
<td style="border:1px solid black;">Servizi certificati ha revocato un certificato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">775</td>
<td style="border:1px solid black;">Servizi certificati ha ricevuto una richiesta di pubblicazione dell’elenco di revoche di certificati (CRL).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">776</td>
<td style="border:1px solid black;">Servizi certificati ha pubblicato l'elenco dei certificati revocati (CRL).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">777</td>
<td style="border:1px solid black;">È stata effettuata l'estensione di una richiesta di certificati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">778</td>
<td style="border:1px solid black;">Uno o più attributi di richieste di certificati sono stati modificati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">779</td>
<td style="border:1px solid black;">Servizi certificati ha ricevuto una richiesta di arresto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">780</td>
<td style="border:1px solid black;">È stato avviato il backup di Servizi certificati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">781</td>
<td style="border:1px solid black;">È stato completato il backup di Servizi certificati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">782</td>
<td style="border:1px solid black;">È stato avviato il ripristino di Servizi certificati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">783</td>
<td style="border:1px solid black;">È stato completato il ripristino di Servizi certificati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">784</td>
<td style="border:1px solid black;">Servizi certificati avviato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">785</td>
<td style="border:1px solid black;">Servizi certificati arrestato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">786</td>
<td style="border:1px solid black;">Le autorizzazioni di protezione di Servizi certificati sono state modificate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">787</td>
<td style="border:1px solid black;">Servizi certificati ha recuperato una chiave archiviata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">788</td>
<td style="border:1px solid black;">Servizi certificati ha importato un certificato nel proprio database.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">789</td>
<td style="border:1px solid black;">Il filtro di controllo per Servizi certificati è stato modificato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">790</td>
<td style="border:1px solid black;">Servizi certificati ha ricevuto una richiesta di certificato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">791</td>
<td style="border:1px solid black;">Servizi certificati ha approvato una richiesta di certificato e ha rilasciato un certificato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">792</td>
<td style="border:1px solid black;">Servizi certificati ha negato una richiesta di certificato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">793</td>
<td style="border:1px solid black;">Servizi certificati ha negato una richiesta di certificato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">794</td>
<td style="border:1px solid black;">Le impostazioni del gestore certificati per Servizi certificati sono state modificate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">795</td>
<td style="border:1px solid black;">Una voce della configurazione in Servizi certificati è stata modificata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">796</td>
<td style="border:1px solid black;">Una proprietà di Servizi certificati è stata modificata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">797</td>
<td style="border:1px solid black;">Servizi certificati ha archiviato una chiave.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">798</td>
<td style="border:1px solid black;">Servizi certificati ha importato e archiviato una chiave.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">799</td>
<td style="border:1px solid black;">Servizi certificati ha pubblicato il certificato della autorità di certificazione (CA) in Active Directory.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">800</td>
<td style="border:1px solid black;">Una o più righe sono state eliminate dal database dei certificati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">801</td>
<td style="border:1px solid black;">Separazione ruoli abilitata.</td>
</tr>
</tbody>
</table>
  
#### Modifica del criterio di controllo
  
Questa impostazione di criterio determina se controllare tutti gli eventi di modifica dei criteri di assegnazione dei diritti utente, dei criteri di affidabilità ai criteri di controllo stessi.
  
Se si configura l'impostazione **Modifica del criterio di controllo** in modo che registri i valori **Operazioni riuscite**, sarà generata una voce di controllo per ogni modifica ai criteri dei diritti utente, dei criteri di affidabilità ai criteri di controllo stessi riuscita con successo. Se si configura questa impostazione in modo che registri i valori **Operazioni non riuscite**, sarà generata una voce di controllo per ogni modifica ai criteri dei diritti utente, dei criteri di affidabilità ai criteri di controllo stessi non riuscita.
  
L’impostazione consigliata consente di vedere tutti i privilegi dell’account che un pirata informatico sta cercando di elevare, ad esempio aggiungendo il privilegio **Debug di programmi** o il privilegio **Backup di file e directory**.
  
L'impostazione **Modifica del criterio di controllo** è configurata per registrare i valori **Operazioni riuscite** nel criterio di base per tutti i tre ambienti definiti in questa guida. Attualmente, l'impostazione **Operazioni non riuscite** non rileva eventi significativi.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione.
  
**Tabella 4.7 Eventi di modifica del criterio di controllo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">608</td>
<td style="border:1px solid black;">Diritto utente assegnato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">609</td>
<td style="border:1px solid black;">Diritti utente eliminati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">610</td>
<td style="border:1px solid black;">Creazione di una relazione di trust con un altro dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">611</td>
<td style="border:1px solid black;">Eliminazione della relazione di trust con un altro dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">612</td>
<td style="border:1px solid black;">Modifica del criterio di controllo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">613</td>
<td style="border:1px solid black;">Avvio di un agente criteri IPsec.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">614</td>
<td style="border:1px solid black;">Disattivazione di un agente criteri IPsec.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">615</td>
<td style="border:1px solid black;">Modifica di un agente criteri IPsec.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">616</td>
<td style="border:1px solid black;">Un agente IPsec ha riscontrato un errore potenzialmente grave.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">617</td>
<td style="border:1px solid black;">Criterio Kerberos versione 5 cambiato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">618</td>
<td style="border:1px solid black;">Criterio di recupero dati crittografati cambiato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">620</td>
<td style="border:1px solid black;">Modifica di una relazione di trust con un altro dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">621</td>
<td style="border:1px solid black;">Concessione dell'accesso al sistema a un account.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">622</td>
<td style="border:1px solid black;">Rimozione dell'accesso al sistema da un account.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">623</td>
<td style="border:1px solid black;">Impostazione del criterio di controllo in base ai singoli utenti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">625</td>
<td style="border:1px solid black;">Aggiornamento del criterio di controllo in base ai singoli utenti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">768    </td>
<td style="border:1px solid black;">Rilevata collisione tra un elemento dello spazio dei nomi in un'insieme di strutture e un elemento dello spazio dei nomi in un altro insieme di strutture.
<strong>Nota</strong>: se un elemento di uno spazio dei nomi di un insieme di strutture si sovrappone a un elemento di uno spazio dei nomi di un altro insieme di strutture, si può produrre un'ambiguità nella risoluzione di un nome appartenente a uno degli elementi. Questa sovrapposizione viene definita anche collisione. Non tutti i parametri sono validi per ciascun tipo di voce. Campi quali, ad esempio, nome DNS, nome NetBIOS e SID non sono validi per una voce di tipo &quot;TopLevelName&quot;.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">769    </td>
<td style="border:1px solid black;">Aggiunta di informazioni sull'insieme di strutture attendibili.
<strong>Nota:</strong> questo messaggio di evento viene generato quando vengono aggiornate le informazioni sul trust tra insiemi di strutture e vengono aggiunte una o più voci. Per ogni voce aggiunta, eliminata o modificata viene generato un messaggio di evento. Se in un unico aggiornamento delle informazioni sul trust tra insiemi di strutture vengono aggiunte, eliminate o modificate più voci, a tutti i messaggi di evento generati viene assegnato un singolo identificativo univoco denominato ID operazione. In questo modo è possibile stabilire che i diversi messaggi di evento generati sono il risultato di un'unica operazione. Non tutti i parametri sono validi per ciascun tipo di voce. Parametri quali, ad esempio, nome DNS, nome NetBIOS e SID non sono validi per una voce di tipo &quot;TopLevelName&quot;.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">770    </td>
<td style="border:1px solid black;">Eliminazione di informazioni sull'insieme di strutture attendibili.
<strong>Nota:</strong> vedere la descrizione dell'evento 769.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">771    </td>
<td style="border:1px solid black;">Modifica di informazioni sull'insieme di strutture attendibili.
<strong>Nota:</strong> vedere la descrizione dell'evento 769.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">805</td>
<td style="border:1px solid black;">Il servizio Registro eventi ha letto la configurazione del registro protezione per una sessione.</td>
</tr>
</tbody>
</table>
  
#### Controlla uso dei privilegi
  
Consente di controllare tutte le istanze di esercizio di un diritto utente da parte di un utente. Se si configura l'impostazione **Controlla uso dei privilegi** in modo da registrare i valori **Operazioni riuscite**, viene generata una voce ogni volta che viene esercitato un diritto utente. Se si configura l'impostazione in modo da registrare i valori **Operazioni non riuscite**, viene generata una voce ogni volta che viene esercitato senza successo un diritto utente.
  
Quando sono esercitati i seguenti diritti utente non sono generati controlli, anche se si configura l'impostazione **Controlla uso dei privilegi**, perché questi diritti di utente generano molti eventi nel registro di Protezione. Se i seguenti diritti fossero controllati, le prestazioni dei computer in uso potrebbero risentirne sensibilmente:
  
-   Ignora controllo visite
  
-   Debug di programmi
  
-   Creazione di un oggetto token
  
-   Replace process-level token
  
-   Generazione controlli di protezione
  
-   Backup di file e directory
  
-   Ripristina file e directory
  
    **Nota**: se si desidera controllare questi diritti utente, è necessario attivare l'opzione di sicurezza **Controllo: controllo utilizzo dei privilegi di backup e di ripristino** nei Criteri di gruppo.
  
L'impostazione **Controlla uso dei privilegi** è configurata per impostazione predefinita su **Nessun controllo** nei criteri di base degli ambienti LC ed EC. Tuttavia, questa impostazione di criteri è configurata per registrare i valori **Operazioni non riuscite** nel criterio di base per l'ambiente SSLF. L’impossibilità di esercitare un diritto utente è un indicatore di un problema generale della rete e in molti casi può segnalare un tentativo di violazione della protezione. È opportuno impostare **Controlla uso dei privilegi** su **Abilitato** solo se vi è un motivo particolare.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione.
  
**Tabella 4.8 Eventi di uso dei privilegi.**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">576    </td>
<td style="border:1px solid black;">Sono stati aggiunti privilegi specifici a un token di accesso dell'utente
<strong>Nota:</strong> l'evento viene generato quando l'utente effettua l'accesso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">577</td>
<td style="border:1px solid black;">Un utente ha tentato di eseguire un'operazione del servizio soggetta a privilegi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">578</td>
<td style="border:1px solid black;">Utilizzo di privilegi su un handle già aperto per un oggetto protetto.</td>
</tr>
</tbody>
</table>
  
#### Controlla tracciato processo
  
Questa impostazione del diritto determina se controllare le informazioni dettagliate dei tracciati di eventi quali l’attivazione di programmi, l’uscita da processi, la duplicazione di handle e l’accesso indiretto agli oggetti. Se si configura questa impostazione di criterio in modo che registri i valori **Operazioni riuscite**, viene generata una voce di controllo ogni volta che il processo controllato viene eseguito con successo. Se si configura questa impostazione di criterio in modo che registri i valori **Operazioni non riuscite**, viene generata una voce di controllo ogni volta che il processo controllato non viene eseguito con successo.
  
L'impostazione **Controlla tracciato processo** genererà un grande numero di eventi, dunque è normalmente configurata su **Nessun controllo**, così come nel criterio di base per tutti i tre ambienti definiti in questa guida. Tuttavia, questa impostazione di criterio può essere molto utile durante una risposta ai problemi perché fornisce un registro dettagliato dei processi in corso e dell'ora in cui ciascuno di essi è stato avviato.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione di questo criterio registra nel registro di protezione.
  
**Tabella 4.9 Eventi di tracciato processo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">593</td>
<td style="border:1px solid black;">Un processo è terminato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">594</td>
<td style="border:1px solid black;">Duplicazione di un handle per un oggetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">595</td>
<td style="border:1px solid black;">Accesso indiretto a un oggetto.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">596    </td>
<td style="border:1px solid black;">Backup di una chiave principale della protezione dati.
<strong>Nota:</strong> la chiave principale è utilizzata dalle routine CryptProtectData e CryptUnprotectData e da Crittografia file system (EFS, Encrypting File System). Viene eseguito un backup della chiave principale ogni volta che ne viene creata una nuova (L'impostazione predefinita è 90 giorni.) Il backup è di solito eseguito su un controller di dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">597</td>
<td style="border:1px solid black;">Ripristino della chiave principale della protezione dati da un server di ripristino.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">598</td>
<td style="border:1px solid black;">Protezione di dati controllabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">599</td>
<td style="border:1px solid black;">Rimozione della protezione di dati controllabili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">600</td>
<td style="border:1px solid black;">Assegnazione di un token primario a un processo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">601</td>
<td style="border:1px solid black;">Tentativo di installazione di un servizio da parte di un utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">602</td>
<td style="border:1px solid black;">Creazione di un processo di Scheduler.</td>
</tr>
</tbody>
</table>
  
#### Controlla eventi di sistema
  
Consente di controllare i riavvii o gli arresti di un computer da parte di un utente o il verificarsi di eventi che interessano la protezione del sistema o il registro di protezione. Se si configura questa impostazione di criterio per registrare i valori **Operazioni riuscite**, viene creata una voce di controllo per ciascun evento di sistema riuscito. Se si configura questa impostazione di criterio per registrare i valori **Operazioni riuscite**, viene creata una voce di controllo per ciascun evento di sistema non riuscito.
  
La tabella seguente elenca gli eventi eseguiti con successo più utili per questa impostazione.
  
**Tabella 4.10 Messaggi eventi di sistema per Controlla eventi di sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID evento</th>
<th style="border:1px solid black;" >Descrizione evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">512</td>
<td style="border:1px solid black;">Avvio di Windows in corso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">513</td>
<td style="border:1px solid black;">Chiusura di Windows in corso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">514</td>
<td style="border:1px solid black;">Un package di autenticazione è stato caricato dall'autorità di protezione locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">515</td>
<td style="border:1px solid black;">Un processo di accesso attendibile ha effettuato la registrazione presso l'autorità di protezione locale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">516</td>
<td style="border:1px solid black;">Le risorse interne allocate per accodare i messaggi di controllo sono state esaurite, causando la perdita di alcuni messaggi di eventi di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">517</td>
<td style="border:1px solid black;">Il registro di controllo è stato cancellato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">518</td>
<td style="border:1px solid black;">Un package di notifica è stato caricato dal sistema di gestione degli account di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">519</td>
<td style="border:1px solid black;">Un processo sta utilizzando una porta LPC (Local Procedure Call) non valida nel tentativo di impersonare un client e rispondere o leggere da oppure scrivere in uno spazio degli indirizzi client.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">520    </td>
<td style="border:1px solid black;">L'ora di sistema è stata cambiata.
<strong>Nota</strong>: questo controllo è normalmente visualizzato due volte.</td>
</tr>
</tbody>
</table>
 

[](#mainsection)[Inizio pagina](#mainsection)

### Assegnazione dei diritti utente

L’impostazione Assegnazione diritti utente determina quali utenti o gruppi hanno privilegi o diritti di accesso per i computer dell'organizzazione. Un esempio di diritto di accesso è il diritto di accesso al computer in modo interattivo. Un privilegio è, ad esempio, la capacità di arrestare il computer. Entrambi i tipi di diritto utente vengono assegnati dagli amministratori a singoli utenti o gruppi nell’ambito delle impostazioni di protezione del computer.

**Nota**: in questa sezione, il parametro "Non definito" è valido soltanto per gli utenti; gli Amministratori mantengono il diritto utente. Gli amministratori locali possono apportare modifiche, ma queste verranno sovrascritte dalle impostazioni dei criteri di gruppo di dominio non appena i criteri di gruppo verranno aggiornati o applicati.

È possibile configurare le impostazioni per l'assegnazione dei diritti utente in Windows Server 2003 con SP1 alla posizione seguente nell'ambito dell'Editor oggetti Criteri di gruppo:

**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali**
**\\Assegnazioni diritti utenti**

Le impostazioni predefinite di Assegnazione diritti utente sono diverse nei vari tipi di server dell'organizzazione. Per esempio, Windows Server 2003 assegna diritti diversi ai gruppi incorporati sui server membri e i controller di dominio (le somiglianze tra i gruppi incorporati su tipi di server diversi non sono documentate nell'elenco seguente.

-   **Server membri**

    -   **Power Users**. Dispongono della maggior parte dei diritti amministrativi, con alcune restrizioni. I Power Users, oltre alle applicazioni certificate per Windows Server 2003 con SP1 o per Windows XP, possono eseguire applicazioni precedenti.

    -   **HelpServicesGroup**. Questo è il gruppo per Guida in linea e supporto tecnico. Support\_388945a0 appartiene a questo gruppo per impostazione predefinita.

    -   **TelnetClients**. I membri di questo gruppo hanno accesso al server Telnet sulla rete.

-   **Controller di dominio**

    -   **Server Operators**. I membri di questo gruppo possono amministrare i server del dominio.

    -   **Terminal Server License Services**. I membri di questo gruppo hanno accesso ai server licenze Terminal Server nella rete.

    -   **Gruppo di accesso autorizzazione Windows**.** **I membri di questo gruppo hanno accesso all’attributo calcolato tokenGroupsGlobalAndUniversal degli oggetti utente.

Il gruppo **Guests** e gli account utente Guest e Support\_388945a0 hanno ID di protezione (SID) univoci in domini diversi. Pertanto, può essere necessario modificare questo criterio di gruppo per le assegnazioni dei diritti utente in un sistema in cui esiste solo il gruppo di destinazione specifico. In alternativa, è possibile modificare i singoli modelli di criteri inserendo i gruppi appropriati nei file .inf. Ad esempio, in un controller di dominio di un ambiente di testing è necessario creare un criterio di gruppo per il controller di dominio.

**Nota**: a causa dei SID unici tra i membri del gruppo **Guests**, Support\_388945a0 e Guest, alcune impostazioni utilizzate per la sicurezza dei server non possono essere automatizzate mediante i modelli di protezione contenuti in questa guida. Queste impostazioni sono descritte nella sezione "Impostazioni di protezione aggiuntive" di questo capitolo.

Questa sezione fornisce dettagli sulle impostazioni suggerite per l'assegnazione dei diritti utente MSBP per i tre ambienti definiti in questa guida. Per un riepilogo delle impostazioni richieste illustrate in questa sezione, vedere la cartella di lavoro di Microsoft Excel con le impostazioni della "Windows Server 2003 Security Guide Settings" allegata alla versione scaricabile di questa guida. Per informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata nella presente sezione, fare riferimento alla guida correlata, *Pericoli e contromisure: Impostazioni di protezione in Windows* *Server* *2003 e Windows* *XP*.

Nella tabella seguente sono inclusi i consigli per l'assegnazione dei diritti utente per i tre tipi di ambiente definiti in questa guida. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.

**Tabella 4.11 Suggerimenti sulle impostazioni di assegnazione dei diritti utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso al computer dalla rete</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators, Authenticated Users, CONTROLLER DI DOMINIO ORGANIZZAZIONE</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Agisci come parte del sistema operativo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Regolazione quote di memoria per un processo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Administrators, SERVIZIO DI RETE, SERVIZIO LOCALE</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti accesso locale</td>
<td style="border:1px solid black;">Administrators, Backup Operators, Power Users</td>
<td style="border:1px solid black;">Administrators, Backup Operators, Power Users</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consenti accesso tramite Servizi terminal</td>
<td style="border:1px solid black;">Administrators e Utenti desktop remoto</td>
<td style="border:1px solid black;">Administrators e Utenti desktop remoto</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Backup di file e directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ignora controllo visite</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Authenticated Users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modifica dell'orario di sistema</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di file di paging</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione di un oggetto token</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di oggetti globali</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori, SERVIZIO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione di oggetti condivisi permanenti</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Debug di programmi</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso al computer dalla rete</td>
<td style="border:1px solid black;">ACCESSO ANONIMO, Guest; Support_388945a0;
Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">ACCESSO ANONIMO, Guest; Support_388945a0;
Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">ACCESSO ANONIMO, Guest; Support_388945a0;
Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso come processo batch</td>
<td style="border:1px solid black;">Guest; Support_388945a0</td>
<td style="border:1px solid black;">Guest; Support_388945a0</td>
<td style="border:1px solid black;">Guest; Support_388945a0;</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso come servizio</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Guest; Support_388945a0;</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso tramite Servizi terminal</td>
<td style="border:1px solid black;">Guests</td>
<td style="border:1px solid black;">Guests</td>
<td style="border:1px solid black;">Guests</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impostazione account computer ed utente a tipo trusted per la delega</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Arresto forzato da un sistema remoto</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Generazione controlli di protezione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">SERVIZIO DI RETE, SERVIZIO LOCALE</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impersona un cliente dopo l'autenticazione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori, SERVIZIO</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aumenta priorità di esecuzione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Installa e disinstalla driver periferica</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco di pagine in memoria</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso come processo batch</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso come servizio</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">SERVIZIO DI RETE</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione file registro di controllo e di protezione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Modifica valori di ambiente firmware</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Esecuzione operazioni di manutenzione volume</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di profilo del singolo processo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Creazione di profilo delle prestazioni del sistema</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rimozione del computer dall'alloggiamento</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sostituzione token a livello di processo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">SERVIZIO LOCALE, SERVIZIO DI RETE</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ripristina file e directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Arresto del sistema</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Sincronizza i dati di servizio della directory</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Diventa proprietario (di file o altri oggetti)</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
</tbody>
</table>
  
#### Accesso al computer dalla rete
  
Questa impostazione determina quali utenti e gruppi sono autorizzati a connettersi al computer tramite la rete. È richiesta da una serie di protocolli di rete, tra cui i protocolli basati su SMB (Server Message Block), NetBIOS, CIFS (Common Internet File System), HTTP e COM+ (Component Object Model Plus).
  
L'impostazione **Accesso al computer dalla rete** è configurata su **Non definito** per gli ambienti LC ed EC. Sebbene le autorizzazioni che sono assegnate al gruppo di protezione **Everyone** non forniscono più l'accesso agli utenti anonimi in Windows Server 2003 con SP1, i gruppi e gli account guest possono tuttavia avere l'accesso tramite il gruppo di protezione **Everyone**. Per questa ragione, il gruppo di protezione **Everyone** non dispone del diritto utente **Accesso al computer dalla rete** nell'ambiente SSLF. In questo modo è possibile prevenire attacchi che sfruttano l'accesso guest al dominio. Soltanto i gruppi **Administrators**, **Authenticated Users**, e **CONTROLLER DI DOMINIO ORGANIZZAZIONE** dispongono di questo diritto utente nell'ambiente SSLF.
  
#### Agisci come parte del sistema operativo
  
Questa impostazione del criterio determina se un processo può assumere l'identità di un utente per ottenere l'accesso alle risorse cui l'utente è autorizzato ad accedere. Di norma, questo privilegio è necessario solo per i servizi di autenticazione di basso livello.
  
Il diritto utente **Agisci come parte del sistema operativo** è configurato su **Non definito** per gli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF quest impostazione di criterio è configurata su un valore Null o vuoto, che nega all'utente il diritto di accesso a tutti i gruppi di protezione e agli account.
  
#### Regolazione quote di memoria per un processo
  
Questa impostazione del criterio determina se consentire agli utenti di regolare la quantità massima di memoria disponibile per un processo. È utile per l’ottimizzazione del sistema, ma è necessario evitare che venga utilizzato per scopi nocivi. Un pirata informatico potrebbe utilizzare questo diritto utente per lanciare un attacco DoS.
  
L'impostazione **Regolazione quote di memoria per un processo** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato al gruppo **Administrators**, al SERVIZIO DI RETE e SERVIZIO LOCALE per l'ambiente SSLF.
  
#### Consenti accesso locale
  
Questa impostazione di criterio determina quali utenti possono accedere interattivamente al computer specificato. Gli accessi effettuati premendo la combinazione di tasti CTRL+ALT+CANC sulla tastiera richiedono che l'utente possieda questo diritto di accesso. Qualsiasi account con questo diritto utente può essere utilizzato per accedere alla console locale del computer.
  
Il diritto utente **Consenti accesso locale** è limitato ai gruppi **Administrators**, **Backup Operators** e **Power Users** per gli ambienti LC ed EC. In questo modo è possibile prevenire l'accesso di utenti non autorizzati che desiderano cambiare i propri privilegi o introdurre virus nell'ambiente. Questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Consenti accesso tramite Servizi terminal
  
Questa impostazione di criterio determina quali utenti o gruppi hanno il diritto di effettuare l'accesso come client di Servizi terminal.
  
Per gli ambienti LC ed EC, il diritto utente **Consenti accesso tramite Servizi terminal** è limitato ai gruppi **Administrators** e **Utenti desktop remoto**. Per l'ambiente SSLF, solo i membri del gruppo **Administrators** dispongono di questo diritto utente.
  
#### Backup di file e directory
  
Questa impostazione del criterio determina se gli utenti possono aggirare le autorizzazioni per file e directory per eseguire il backup del computer. È utilizzato solo quando un'applicazione tenta l'accesso attraverso l'API (Application Programming Interface) di backup del file system NTFS, utilizzando un'utilità di backup quale NTBACKUP.EXE. In caso contrario si applicano le normali autorizzazioni di file e directory.
  
L'impostazione **Backup di file e directory** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Questo diritto utente è assegnato soltanto al gruppo di **Amministratori** per l'ambiente SSLF.
  
#### Ignora controllo visite
  
Questa impostazione di criterio determina se gli utenti che esplorano un percorso oggetti nel file system NTFS o nel Registro di sistema devono dimostrare di possedere l'autorizzazione di accesso speciale "Visita cartelle". Questo diritto utente consente all'utente solo di cambiare cartelle e non di visualizzarne il contenuto.
  
L'impostazione **Ignora controllo visite** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Questo diritto utente è assegnato soltanto al gruppo **Authenticated Users** per l'ambiente SSLF.
  
#### Modifica dell'orario di sistema
  
Questa impostazione di criterio determina quali utenti possono modificare l'ora e la data dell'orologio interno del computer. Gli utenti a cui è stato assegnato questo diritto utente possono modificare l'aspetto dei registri di evento. Questi ultimi riportano l'ora dell'orologio interno del computer. Se l'ora del computer è modificata, i registri non riporteranno l'ora reale in cui gli eventi si sono verificati.
  
L'impostazione **Modifica dell'orario di sistema** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Questo diritto utente è assegnato soltanto al gruppo di **Administrators** per l'ambiente SSLF.
  
**Nota:** le discrepanze fra l'ora del computer locale e quella dei controller di dominio possono causare problemi per il protocollo di autenticazione Kerberos e questo potrebbe impedire agli utenti di accedere al dominio o ottenere l'autorizzazione per accedere alle risorse del dominio dopo l’accesso.
  
#### Creazione di file di paging
  
Questa impostazione di criterio determina se gli utenti possono creare e modificare le dimensioni dei file di paging. Per effettuare questa operazione, l'utente specifica le dimensioni di un file di paging per una determinata unità nella casella **Opzioni prestazioni** della scheda **Avanzate** della finestra di dialogo di **Proprietà di sistema**.
  
L'impostazione **Creazione di file di paging** è configurata su **Non definito** per gli ambienti LC ed EC, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Creazione di un oggetto token
  
Questa impostazione di criterio consente a un processo di creare un token, che il processo potrà usare per accedere alle risorse locali quando utilizza NtCreateToken() o altre API per la creazione di token.
  
L'impostazione **Creazione di un oggetto token** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
#### Creazione di oggetti globali
  
Questa impostazione del criterio consente agli utenti di creare oggetti globali che siano disponibili in tutte le sessioni. Gli utenti possono comunque creare oggetti specifici per la loro sessione anche se non dispongono di questo diritto utente.
  
L'impostazione **Creazione di oggetti globali** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Per l'ambiente SSLF, questo diritto utente è assegnato soltanto ai gruppi **SERVIZIO** e **Administrators.**
  
#### Creazione di oggetti condivisi permanenti
  
Questa impostazione di criterio determina se gli utenti possono creare oggetti directory nel gestore oggetto, il che significa che è possibile creare cartelle condivise, stampanti e altri oggetti. È utile ai componenti in modalità kernel che estendono lo spazio dei nomi degli oggetti e che sono predefiniti con questo diritto utente. Pertanto, di norma non è necessario assegnarlo esplicitamente agli utenti.
  
L'impostazione **Creazione di oggetti condivisi permanenti** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
#### Debug di programmi
  
Questa impostazione di criterio determina quali utenti possano collegare un debugger a un processo o al kernel. Consente di accedere a componenti del sistema operativo importanti ed essenziali. Non effettuare il debugging di programmi negli ambienti di produzione se non in circostanze particolari, come quando è necessario localizzare i guasti di un'applicazione critica per l'azienda che non può essere valutata efficacemente nell'ambiente di test.
  
L'impostazione **Debug di programmi** è configurata su **Non definito** per l'ambiente LC. Per l'ambiente EC, questo diritto utente è assegnato soltanto al gruppo **Administrators**. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
**Nota**: su Windows Server 2003 con SP1, la rimozione del diritto utente **Debug di programmi** rende indisponibile il servizio Windows Update. Tuttavia, è possibile scaricare e installare o applicare le patch manualmente o tramite altri meccanismi. La rimozione di questo diritto utente può interferire anche col Servizio cluster. Per maggiori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Applicazione delle impostazioni di protezione più restrittive su un server cluster basato su Winows Server 2003](http://support.microsoft.com/kb/891597/it)" all'indirizzo [http://support.microsoft.com/kb/891597/it,](http://support.microsoft.com/kb/891597/it)
  
#### Nega accesso al computer dalla rete
  
**Nota**: ACCESSO ANONIMO, amministratore incorporato, Support\_388945a0, Guest, e tutti gli account di servizio NON utilizzati dal sistema operativo non sono inclusi nel modello di protezione .inf. Questi account e gruppi presentano SID univoci per ogni dominio dell'organizzazione e devono, quindi, essere aggiunti manualmente. Per ulteriori informazioni, consultare il capitolo "Procedure manuali per la protezione avanzata" verso la fine di questo capitolo.
  
Questa impostazione di criterio determina quali utenti non saranno in grado di accedere a un computer della rete. Impedisce l’accesso a numerosi protocolli di rete, inclusi i protocolli basati su SMB, NetBIOS, CIFS, HTTP e COM+. Questa impostazione prevale sul diritto utente **Accedi al computer dalla rete** nei casi in cui a un account utente siano applicate entrambe le impostazioni.
  
Per tutti i tre ambienti definiti in questa guida, il diritto utente **Nega accesso al computer dalla rete** è assegnato al gruppo **Guests**, ACCESSO ANONIMO, Support\_388945a0 e a tutti gli account di servizio che non fanno parte del sistema operativo.
  
La configurazione di questa impostazione di criterio per altri gruppi potrebbe limitare le capacità di utenti assegnati a ruoli amministrativi specifici. Verificare che non vi siano conseguenze negative sulle attività delegate.
  
#### Nega accesso come processo batch
  
**Nota**: ACCESSO ANONIMO, amministratore incorporato, Support\_388945a0, Guest, e tutti gli account di servizio NON utilizzati dal sistema operativo non sono inclusi nel modello di protezione .inf. Questi account e gruppi presentano SID univoci per ogni dominio dell'organizzazione e devono, quindi, essere aggiunti manualmente. Per ulteriori informazioni, consultare il capitolo "Procedure manuali per la protezione avanzata" verso la fine di questo capitolo.
  
Questa impostazione di criterio determina quali account non saranno in grado di accedere al computer come processo batch. Un processo batch non è un file batch (bat), piuttosto una funzionalità per code di tipo batch. Gli account che utilizzano l'Utilità di pianificazione per pianificare i processi necessitano di questo diritto utente.
  
Il diritto utente **Nega accesso come processo batch** ignora il diritto utente **Accesso come processo batch**, che potrebbe essere utilizzato per consentire agli account di pianificare processi che consumano quantità molto elevate di risorse di sistema Tale evento potrebbe causare una condizione DoS. Per questa ragione, il diritto utente **Nega accesso come processo batch** è assegnato al gruppo **Guests** e l'account utente Support\_388945a0 nel criterio di base per tutti i tre ambienti definiti in questa guida. La mancata assegnazione di questo diritto utente agli account raccomandati può essere un rischio di protezione.
  
#### Nega accesso come servizio
  
Questa impostazione di criterio determina se i servizi possono essere lanciati nel contesto dell'account specificato.
  
L'impostazione **Nega accesso come servizio** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
#### Nega accesso locale
  
Questa impostazione del criterio determina se gli utenti possono accedere direttamente alla tastiera del computer.
  
L'impostazione **Nega accesso locale** è configurata su **Non definito** per i computer negli ambienti EC ed LC. Tuttavia, questo diritto utente è assegnato solo al gruppo **Guests** e all'account utente Support\_388945a0 per l'ambiente SSLF. La mancata assegnazione di questo diritto utente agli account raccomandati può essere un rischio di protezione.
  
#### Nega accesso tramite Servizi terminal
  
**Nota**: ACCESSO ANONIMO, amministratore incorporato, Support\_388945a0, Guest, e tutti gli account di servizio NON utilizzati dal sistema operativo non sono inclusi nel modello di protezione .inf. Questi account e gruppi presentano SID univoci per ogni dominio dell'organizzazione e devono, quindi, essere aggiunti manualmente. Per ulteriori informazioni, consultare il capitolo "Procedure manuali per la protezione avanzata" verso la fine di questo capitolo.
  
Questa impostazione di criterio determina se gli utenti possono accedere come client di Servizi terminal. Dopo aver inserito il server membro di base in un dominio, non è necessario utilizzare account locali per accedere al server dalla rete. È possibile, infatti, utilizzare gli account del dominio per accedere al server ed eseguire le attività di amministrazione e di elaborazione per gli utenti finali.
  
In tutti i tre ambienti definiti in questa guida, al gruppo **Guests** è assegnato il diritto utente **Nega accesso tramite Servizi terminal** in modo che non sia possibile accedere attraverso i Servizi terminal.
  
#### Impostazione account computer ed utente a tipo trusted per la delega
  
Questa impostazione del criterio determina se gli utenti possono modificare l'impostazione **Trusted per la delega** di un oggetto utente o computer nell'Active Directory. Gli utenti o i computer cui è stato assegnato questo diritto utente devono disporre dell'accesso in scrittura dei flag di controllo dell'account nell'oggetto. L'abuso di questo diritto utente potrebbe causare la rappresentazione non autorizzata di altri utenti sulla rete.
  
L'impostazione **Impostazione account computer ed utente a tipo trusted per la delega** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Amministratori** per l'ambiente SSLF.
  
#### Arresto forzato da un sistema remoto
  
Questa impostazione di criterio determina se gli utenti possono arrestare i computer da postazioni remote sulla rete. Qualsiasi utente in grado di arrestare un computer può provocare una condizione di DoS. Pertanto, questo privilegio deve essere assegnato solo se strettamente necessario.
  
L'impostazione **Arresto forzato da un sistema remoto** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Generazione controlli di protezione
  
Questa impostazione del criterio determina se un processo può generare registrazioni di controllo nel registro di protezione. Poiché il registro di protezione può essere utilizzato per tracciare l'accesso non autorizzato, gli account che possono scrivere sul registro di protezione potrebbero essere utilizzati da un pirata informatico per riempire il registro con eventi insignificanti. Se il computer è configurato in modo che gli eventi vengano sovrascritti quando necessario, il pirata informatico potrebbe utilizzare questa funzione per cancellare le prove delle sue attività illecite. Se si configura il computer in modo che il sistema si arresti quando non è possibile scrivere sul registro di protezione, un pirata informatico potrebbe utilizzare questa funzionalità per creare una condizione DoS.
  
L'impostazione **Generazione controlli di protezione** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Questo diritto utente è assegnato agli account SERVIZIO DI RETE e SERVIZIO LOCALE per l'ambiente SSLF.  
  
#### Impersona un cliente dopo l'autenticazione
  
Questa impostazione di criterio determina se le applicazioni in esecuzione da parte di un utente autenticato possono rappresentare dei client. Se per questo tipo di rappresentazione è richiesto questo diritto utente, gli utenti non autorizzati non saranno in grado di convincere un client a connettersi, per esempio mediante RPC (Remote Procedure Call) o named pipe, a un servizio che hanno creato per rappresentare tale cliente. L'utente non autorizzato potrebbe utilizzare questa funzionalità per elevare le proprie autorizzazioni a livello amministratore o di sistema.
  
L'impostazione **Impersona un cliente dopo l'autenticazione** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** e SERVIZIO per l'ambiente SSLF.
  
#### Aumenta priorità di esecuzione
  
Questa impostazione del criterio determina se gli utenti possono aumentare la classe di priorità di base di un processo. Aumentare la priorità relativa in una classe di priorità non è un’operazione che richiede privilegi. Questo diritto utente non è necessario per gli strumenti di amministrazione disponibili nel sistema operativo, ma potrebbe esserlo per alcuni strumenti di sviluppo. Un utente cui è stato assegnato questo diritto utente può aumentare la priorità di pianificazione di un processo fino al livello In tempo reale, lasciando così poco tempo per gli altri processi e ciò potrebbe provocare una condizione di tipo DoS.
  
L'impostazione **Aumenta priorità di esecuzione** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Amministratori** per l'ambiente SSLF.
  
#### Installa e disinstalla driver periferica
  
Questa impostazione di criterio determina quali utenti possono caricare e rimuovere dinamicamente i driver di periferica. Questo diritto utente non è necessario se il file Driver.cab del computer contiene già un driver firmato per il nuovo hardware. I driver di periferica vengono eseguiti come codice con privilegi di alto livello. Un utente a cui è stato assegnato il diritto **Installa e disinstalla driver periferica** può installare inconsapevolmente codice dannoso mascherato da driver di periferica (si presume che gli amministratori prestino estrema cautela e che, pertanto, installeranno solo driver con firme digitali verificate).
  
L'impostazione **Installa e disinstalla driver periferica** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Blocco di pagine in memoria
  
Questa impostazione del criterio determina se un processo può archiviare dati nella memoria fisica, per evitare il paging di dati nella memoria virtuale sul disco del computer. Tale evento potrebbe diminuire significativamente le prestazioni. Gli utenti a cui è stato assegnato questo diritto utente possono assegnare la memoria fisica a diversi processi lasciando poca o nessuna memoria RAM a disposizione di altri processi, cosa che potrebbe condurre a una condizione DoS.
  
L'impostazione **Blocco di pagine in memoria** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
#### Accesso come servizio
  
Questa impostazione del criterio determina se un principio di sicurezza può accedere come un servizio. I servizi possono essere configurati in modo da essere eseguiti con l’account di sistema locale, con l’account Servizio locale o con l’account Servizio di rete, in cui il diritto di accedere come servizio è incorporato. Questo diritto deve essere assegnato a ogni servizio che viene eseguito con un account utente distinto.
  
L'impostazione **Accesso come servizio** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto all'account Servizio di rete per l'ambiente SSLF.
  
#### Gestione file registro di controllo e di protezione
  
Questa impostazione di criterio** **determina se gli utenti possono specificare le opzioni di controllo dell'accesso a un oggetto per risorse specifiche, ad esempio file, oggetti Active Directory e chiavi del Registro di sistema. Questo diritto utente è potente e dovrebbe essere protetto con attenzione. Chiunque detiene questo diritto utente può eliminare il contenuto del registro di protezione e cancellare le prove di attività non autorizzate.
  
L'impostazione **Gestione file registro di controllo e di protezione** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
**Importante**: Microsoft Exchange Server 2003 modifica questo diritto utente nel Criterio controller di dominio predefinito durante il processo di installazione. Per maggiori informazioni, consultare [Exchange Server 2003 Deployment](http://www.microsoft.com/technet/prodtechnol/exchange/guides/e2k3adperm/110e37bf-a68c-47bb-b4d5-1cfd539d9cba.mspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/exchange/guides/E2k3ADPerm/110e37bf-a68c-47bb-b4d5-1cfd539d9cba.mspx (in inglese).](http://www.microsoft.com/technet/prodtechnol/exchange/guides/e2k3adperm/110e37bf-a68c-47bb-b4d5-1cfd539d9cba.mspx) Se questo diritto utente è limitato al gruppo dell'amministratore, Exchange registrerà spesso messaggi di errore nel registro eventi applicazioni. Se si utilizza Exchange Server 2003, sarà necessario modificare il valore di questa impostazione per i controller di dominio. Come con tutte le impostazioni suggerite in questa guida, potrebbe essere necessario applicare alcune modifiche per consentire alle applicazioni aziendali di funzionare normalmente.
  
#### Modifica valori di ambiente firmware
  
Questa impostazione di criterio determina se le variabili di ambiente del computer possono essere modificate, sia da un processo attraverso un'API sia da un utente attraverso le **Proprietà di sistema**. Chiunque abbia questo diritto utente può configurare le impostazioni di un componente hardware in modo che si verifichino errori e questo può causare danni ai dati o dar vita a una condizione di tipo DoS.
  
L'impostazione **Modifica valori di ambiente firmware** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Esecuzione operazioni di manutenzione volume
  
Questa impostazione di criterio determina se un utente non-amministrativo o remoto può gestire volumi o dischi. Un utente con questo diritto utente potrebbe cancellare un volume e provocare la perdita di dati o una condizione DoS.
  
L'impostazione **Esecuzione operazioni di manutenzione volume** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Creazione di profilo del singolo processo
  
Questa impostazione di criterio determina quali utenti possono utilizzare gli strumenti per controllare le prestazioni dei processi non di sistema. Questo diritto utente espone il sistema a un rischio moderato. Un pirata informatico con questo privilegio può monitorare le prestazioni di un computer per individuare processi critici da attaccare direttamente. Un pirata informatico potrebbe determinare quali processi sono in esecuzione sul computer in modo da adottare contromisure per evitare l'identificazione da parte di software antivirus, sistemi di rilevamento di intrusione o altri utenti che accedono al computer.
  
L'impostazione **Creazione di profilo del singolo processo** è configurata su **Non definito** per gli ambienti LC ed EC. Per maggiore protezione, verificare che il gruppo **Power Users** non disponga di questo diritto utente nell'ambiente SSLF; soltanto i membri del gruppo **Administrators** dovrebbero disporre di questa funzione in tale ambiente.
  
#### Creazione di profilo delle prestazioni del sistema
  
Questa impostazione di criterio è simile all'impostazione precedente. Determina se gli utenti possono controllare le prestazioni dei processi di sistema. Questo diritto utente espone il sistema a un rischio moderato. Un pirata informatico con questo privilegio può monitorare le prestazioni di un computer per individuare processi critici da attaccare direttamente. Il pirata informatico potrebbe anche scoprire quali processi sono in esecuzione nel sistema, individuando così le contromisure da evitare, ad esempio software antivirus o un sistema di rilevamento delle intrusioni.
  
L'impostazione **Creazione di profilo delle prestazioni del sistema** è configurata su **Non definito** per i computer negli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Rimozione del computer dall'alloggiamento
  
Questa impostazione di criterio determina se l'utente di un computer portatile possa selezionare **Rilascia PC** dal menu **Avvio** per rimuovere il computer dall'alloggiamento. Chiunque abbia questo diritto utente può rimuovere dall’alloggiamento di espansione un computer portatile avviato.
  
L'impostazione **Rimozione del computer dall'alloggiamento** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Sostituzione token a livello di processo
  
Questa impostazione del criterio consente a un processo padre di sostituire il token di accesso associato a un processo figlio.
  
L'impostazione **Sostituzione token a livello di processo** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto agli account SERVIZIO LOCALE e SERVIZIO DI RETE per l'ambiente SSLF.
  
#### Ripristina file e directory
  
Questa impostazione di criterio determina quali utenti possono ignorare le autorizzazioni di file, directory, Registro di sistema e altri oggetti persistenti quando eseguono il ripristino di file e directory da copie di backup. Determina, inoltre, quali utenti possono impostare una qualsiasi identità di protezione valida come proprietario di un oggetto.
  
L'impostazione **Ripristino di file e directory** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF. Di norma il ripristino dei file viene eseguito dagli amministratori o dai membri di un altro gruppo di protezione specificatamente assegnato a questo compito, soprattutto per server e controller di dominio particolarmente importanti.
  
#### Arresto del sistema
  
Questa impostazione di criterio determina quali utenti connessi al computer locale possono arrestare il sistema operativo utilizzando il comando **Arresta il sistema**. Poiché l'abuso di questa funzionalità potrebbe causare una condizione DoS, per quando riguarda i controller di dominio, solo un numero molto ristretto di amministratori affidabili deve avere il diritto di arrestare il sistema. È vero che per arrestare un sistema è necessario prima accedere al server, ma in ogni caso è necessario scegliere con estrema cautela gli account e i gruppi a cui assegnare questo diritto per i controller di dominio.
  
L'impostazione **Arresto del sistema** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente è assegnato soltanto al gruppo **Administrators** per l'ambiente SSLF.
  
#### Sincronizza i dati di servizio della directory
  
Questa impostazione del criterio determina se un processo può leggere tutti gli oggetti e le proprietà della directory, a prescindere dalla protezione di oggetti e proprietà. Questo diritto utente è necessario per poter utilizzare i servizi di sincronizzazione della directory (Dirsync) LDAP.
  
La configurazione predefinita di **Sincronizza i dati di servizio della directory** è **Non definito**, impostazione sufficiente per gli ambienti LC ed EC. Tuttavia, per l'ambiente SSLF questa impostazione di criterio è configurata su un valore nullo o vuoto, e questo significa che nessun gruppo di protezione o account avrà questo diritto di utente.
  
#### Diventa proprietario (di file o altri oggetti)
  
Questa impostazione di criterio determina se un utente può diventare proprietario di qualsiasi oggetto che può essere protetto nella rete, inclusi oggetti Active Directory, file e cartelle NTFS, stampanti, chiavi del Registro di sistema, servizi, processi e thread.
  
L'impostazione **Diventa proprietario (di file o altri oggetti)** è configurata su **Non definito** per gli ambienti LC ed EC. Tuttavia, questo diritto utente deve essere assegnato soltanto al gruppo **Administrators** locale per l'ambiente SSLF.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
Le impostazioni di criterio nella sezione di Opzioni di Protezione dei Criteri di gruppo sono utilizzate per attivare o disattivare le funzionalità come l'accesso all'unità floppy e ai CD-ROM e i prompt di accesso. Queste impostazioni di criterio sono inoltre utilizzate per configurarne altre, ad esempio la firma digitale dei dati, i nomi degli account Amministratore e Guest e la modalità di funzionamento dei driver.
  
È possibile configurare le impostazioni di protezione in Windows Server 2003 con SP1 alla posizione seguente nell'ambito dell'Editor oggetti Criteri di gruppo:
  
**Configurazione del computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\**  
**Opzioni di protezione**
  
Non tutte le impostazioni di protezione trattate in questa sezione sono presenti in tutti i tipi di computer. Pertanto, nei computer in cui sono presenti, potrebbe essere necessario modificare manualmente le impostazioni che comprendono la parte Opzioni di protezione dei Criteri di gruppo definite in questa sezione, per renderle pienamente operative.
  
Le sezioni seguenti forniscono informazioni sulle impostazioni di protezione MSBP suggerite per tutti i tre ambienti definiti in questa guida. Per un riepilogo delle impostazioni richieste, vedere la cartella di lavoro di Excel con le impostazioni della "Windows Server 2003 Security Guide Settings" allegata alla versione scaricabile di questa guida. Per informazioni sulla configurazione predefinita e una spiegazione dettagliata per ogni impostazione, fare riferimento alla guida correlata, *Pericoli e contromisure: Impostazioni di protezione in Windows* *Server* *2003 e Windows* *XP*.
  
Le tabelle in ciascuna delle seguenti sezioni riassumono le impostazioni consigliate per i diversi tipi di impostazioni delle opzioni di protezione. Nelle sottosezioni che seguono ciascuna tabella sono disponibili ulteriori informazioni sulle impostazioni.
  
#### Impostazioni di account
  
**Tabella 4.12 Opzioni di protezione: suggerimenti per le impostazioni degli account**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">stato account Administrator</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">stato account Guest</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">limitare l'uso locale di account con password vuote all'accesso alla console</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Account: stato account Administrator
  
Questa impostazione di criterio attiva o disattiva l'account Administrator durante il normale funzionamento. Nell'avvio in modalità provvisoria, l'account Administrator è sempre abilitato, indipendentemente da questa impostazione.
  
L'impostazione **Account: stato account Administrator** è configurata su **Non definito** per gli ambienti LE ed EC e su **Abilitato** per l'ambiente SSLF.
  
##### Account: stato account Guest
  
Questa impostazione di criterio determina se l'account Guest è attivato o disattivato. Questo account consente a utenti della rete non autenticati di accedere al computer come Guest.
  
L'impostazione **Account: stato account Guest** è configurata su **Disabilitato** nel criterio di base per tutti i tre ambienti definiti in questa guida.
  
##### Account: limitare l'uso locale di account con password vuote all'accesso alla console
  
Questa impostazione di criterio determina se è possibile utilizzare gli account locali non protetti con password per eseguire l’accesso da postazioni che non siano la console fisica del computer. Se si abilita questa impostazione, si impedisce agli account locali con password non vuote di accedere alla rete da un client remoto. Inoltre, gli account locali non protetti con password potranno accedere solo tramite la tastiera del computer.
  
L'impostazione **Account: limitare l'uso locale di account con password vuote all'accesso alla console** è configurata su **Disabilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
#### Impostazioni di controllo
  
**Tabella 4.13 Opzioni di protezione: suggerimenti per le impostazioni dei criteri di controllo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">controllo accesso oggetti di sistema globale</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">controllo utilizzo dei privilegi di backup e di ripristino</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">arresto del sistema immediato se non è possibile registrare i controlli di protezione</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Controllo: controllo accesso oggetti di sistema globale
  
Quando attivato, questo criterio controlla l'accesso agli oggetti di sistema globale. Se si abilitano entrambe le opzioni **Controllo: controllo accesso oggetti di sistema globale** e **Controlla accesso agli oggetti**, viene generato un numero molto elevato di eventi di controllo.
  
L'impostazione **Controllo: controllo accesso oggetti di sistema globale** è configurata sul valore predefinito **Disabilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
**Nota**: le modifiche apportate a questa impostazione del criterio non avranno effetto fino al riavvio di Windows  Server 2003.
  
##### Controllo: controllo utilizzo dei privilegi di backup e di ripristino
  
Questa impostazione di criterio determina se controllare l'utilizzo di tutti i privilegi utente, incluso Backup e ripristino, quando l'impostazione di criterio **Controlla uso dei privilegi** è attiva. L'abilitazione di questa impostazione potrebbe generare un numero elevato di eventi di protezione, con conseguente rallentamento dei tempi di risposta dei server e memorizzazione forzata di numerosi eventi di scarso interesse nel registro eventi protezione.
  
Quindi, l'impostazione **Controllo: controllo utilizzo dei privilegi di backup e di ripristino** è configurata sul valore predefinito **Disabilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
**Nota**: le modifiche apportate a questa impostazione del criterio non avranno effetto fino al riavvio di Windows  Server 2003.
  
##### Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione
  
Questa impostazione di criterio determina se il sistema debba essere arrestato quando non è in grado di registrare gli eventi di protezione.
  
Il sovraccarico amministrativo richiesto per attivare l'impostazione **Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione** negli ambienti LC ed EC è troppo grande. Quindi, questa impostazione di criterio è configurata su **Disabilitato** nel criterio di base per tali ambienti. Tuttavia, questa impostazione di criterio è configurata su **Abilitato** nel criterio di base dell'ambiente SSLF perché è necessario impedire che vengano eliminati eventi dal registro eventi di protezione a meno che un amministratore non decida esplicitamente di farlo e questo giustifica il carico di lavoro per gli amministratori.
  
#### Impostazioni delle periferiche
  
**Tabella 4.14 Opzioni di protezione: suggerimenti per l'impostazione delle periferiche**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">consenti il disinserimento senza dover effettuare l'accesso</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">è consentita la formattazione e la rimozione dei supporti rimovibili</td>
<td style="border:1px solid black;">Amministratori</td>
<td style="border:1px solid black;">Amministratori</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">non consentire agli utenti di installare i driver della stampante</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">funzionamento installazione driver privo di firma digitale</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
<td style="border:1px solid black;">Avvisa ma consenti installazione</td>
</tr>
</tbody>
</table>
  
##### Periferiche: consenti il disinserimento senza dover effettuare l'accesso
  
Questa impostazione di criterio determina se un computer portatile può essere disinserito se l'utente non accede al computer. Attivare questa impostazione di criterio per eliminare un requisito per l'accesso e consentire l’utilizzo di un pulsante di rimozione hardware esterno per rimuovere il computer dall’alloggiamento di espansione. Se si disattiva questa impostazione di criterio, a un utente che non ha effettuato l'accesso deve essere assegnato il diritto utente **Rimozione del computer dall'alloggiamento**.
  
L'impostazione **Periferiche: consenti il disinserimento senza dover effettuare l'accesso** è configurata su **Disabilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibili
  
Questa impostazione di criterio consente di determinare chi può formattare e rimuovere supporti removibili. Questo privilegio deve essere assegnato solo agli amministratori.
  
Quindi, il valore consigliato per l'impostazione **Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibil** è il valore predefinito di **Administrators** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Periferiche: non consentire agli utenti di installare i driver della stampante
  
Per poter utilizzare una stampante di rete, è necessario che nel computer sia installato il driver per tale stampante. Se si attiva l'impostazione **Periferiche: non consentire agli utenti di installare i driver della stampante**, soltanto i gruppi **Administrators,Power Users** o quelli con privilegi Server Operators possono installare un driver di stampante quando aggiungono una stampante di rete. Se si disattiva questa impostazione di criterio, qualunque utente può installare un driver di stampante.
  
L'impostazione **Periferiche: non consentire agli utenti di installare i driver della stampante** è configurata per impostazione predefinita su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale
  
Determina se un CD-ROM è accessibile contemporaneamente agli utenti sia locali che remoti. Se si attiva questa impostazione di criterio, solo gli utenti connessi interattivamente possono accedere ai supporti dall'unità CD-ROM rimovibile. Se questo criterio è abilitato e nessun utente si è connesso in modo interattivo, è possibile accedere all'unità CD-ROM dalla rete.
  
L'impostazione **Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale** è configurato su **Non definito** nel criterio di base degli ambienti LC ed EC. Nel criterio di base per l'ambiente SSLF, questa impostazione di criterio è configurata su **Disabilitato.**
  
##### Periferiche: limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale
  
Determina se un supporto floppy rimovibile è accessibile contemporaneamente agli utenti sia locali che remoti. Se si attiva questa impostazione di criterio, solo gli utenti connessi interattivamente possono accedere ai supporti dall'unità floppy rimovibile. Se questa impostazione di criterio è abilitata e nessun utente si è connesso in modo interattivo, è possibile accedere ai dischi floppy dalla rete.
  
L'impostazione **Periferiche: limita accesso all'unità floppy agli utenti che hanno effettuato l'accesso locale** è configurata su **Non definito** nel criterio di base degli ambienti LC ed EC. Nel criterio di base per l'ambiente SSLF, questa impostazione di criterio è configurata su **Disabilitato.**
  
##### Periferiche: funzionamento installazione driver privo di firma digitale
  
Determina che cosa accade quando viene effettuato un tentativo di installare un driver di periferica (tramite l'API del programma di installazione) che non è stato approvato e dotato di firma digitale WHQL (Windows Hardware Quality Lab). In base alla sua configurazione, questa impostazione di criterio consente di impedire l’installazione di driver privi di firma digitale oppure di avvisare l'amministratore che è in corso un tentativo di installazione di un driver privo di firma digitale.
  
L'impostazione **Periferiche: funzionamento installazione driver privo di firma digitale** consente di impedire l’installazione di driver privi di firma digitale su Windows Server 2003 con SP1. Tuttavia, l'impostazione **Avvisa ma consenti installazione** è configurata nel criterio base di tutti i tre ambienti definiti in questa guida. Un problema potenziale consiste nel fatto che non è possibile eseguire script di installazione automatica se si tenta di installare driver privi di firma digitale.
  
#### Impostazioni dei membri di dominio
  
**Tabella 4.15 Opzioni di protezione: suggerimenti di impostazione dei membri di dominio**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aggiunta firma digitale ai dati del canale protetto (quando possibile)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">disabilitazione cambio password account computer</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">validità massima password account computer</td>
<td style="border:1px solid black;">30 giorni</td>
<td style="border:1px solid black;">30 giorni</td>
<td style="border:1px solid black;">30 giorni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Richiedere una chiave di sessione avanzata (Windows 2000, Windows XP, o Windows Server 2003)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)
  
Questa impostazione di criterio determina se il traffico del canale protetto avviato dal membro di dominio deve essere firmato o crittografato. Se per un sistema è abilitata questa opzione, il sistema non potrà stabilire un canale protetto con un controller di dominio che non sia in grado di crittografare o firmare tutto il traffico del canale protetto.
  
L'impostazione **Membro di dominio: aggiungi crittografia o firma digitale ai dati del canale protetto (sempre)** è configurata su **Disabilitato** nel criterio di base per l'ambiente LC e su **Abilitato** negli ambienti EC e SSLF.
  
**Nota**: per poter sfruttare questa opzione di protezione nelle workstation e nei server membro, è necessario che in tutti i controller di dominio del dominio sia in esecuzione Windows NT 4.0 con Service Pack 6a o versioni successive. Inoltre, questa opzione non è supportata nei client Windows 98 Seconda Edizione, a meno che non sia installato dsclient.
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)
  
Questa impostazione di criterio permette di stabilire se un membro del dominio può richiedere la crittografia per tutto il traffico del canale protetto da esso avviato. Se si attiva questa impostazione di criterio, il membro di dominio richiederà la crittografia di tutto il traffico del canale protetto. Se si disattiva questa impostazione di criterio, al membro di dominio sarà impedito di richiedere la crittografia del canale protetto.
  
Quindi, l'impostazione **Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Controller di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)
  
Questa impostazione di criterio permette di stabilire se un membro del dominio può richiedere la firma per tutto il traffico del canale protetto da esso avviato. La firma evita che il traffico venga modificato da un intruso che riesca ad acquisire i dati.
  
L'impostazione **Controller di dominio: aggiungi crittografia digitale ai dati del canale protetto (quando possibile)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Controller di dominio: disabilitazione cambio password account computer
  
Questa impostazione di criterio determina se un membro di dominio può modificare periodicamente la password dell'account del computer. Se si attiva questa impostazione di criterio, il membro di dominio non sarà in grado di modificare la password dell'account del computer. Se si disattiva questa impostazione di criterio, il membro di dominio può modificare la password dell'account del computer come specificato dall'impostazione **Controller di dominio: validità massima password account computer**, ovvero ogni 30 giorni per impostazione predefinita.
  
I computer sui quali non è possibile modificare automaticamente le password dell'account sono potenzialmente vulnerabili, poiché un pirata informatico potrebbe essere in grado di determinare la password dell'account di dominio del computer. Di conseguenza l'impostazione **Controller di dominio: disabilitazione cambio password account computer** è configurata su **Disabilitato** nel criterio base di tutti e tre gli ambienti definiti in questa guida.
  
##### Controller di dominio: validità massima password account computer
  
Questa impostazione di criterio determina la durata massima della password dell'account di un computer. Questa impostazione viene applicata anche ai computer con Windows 2000, ma in questi casi non è possibile accedervi tramite gli strumenti per la gestione della configurazione della protezione su questi computer. Per impostazione predefinita, le password dei membri del dominio vengono cambiate automaticamente ogni 30 giorni. Se si aumenta in modo significativo tale intervallo o si imposta il numero di giorni su 0 in modo che i computer non possano più modificare le password, i pirati informatici avranno a disposizione più tempo per eseguire un attacco di tipo "brute force" contro gli account dei computer.
  
Di conseguenza l'impostazione **Controller di dominio: validità massima password account computer** è configurata su **30 giorni** nel criterio di base per tutti e tre gli ambienti definiti in questa guida.
  
##### Membro di dominio: richiesta chiave di sessione avanzata (Windows 2000 o versioni successive)
  
Questa impostazione di criterio determina se per i dati del canale protetto crittografati deve essere utilizzata la chiave a 128 bit. Se si abilita questa impostazione di criterio, si impedisce che venga stabilito un canale protetto se non è disponibile la crittografia a 128 bit. Se si disabilita questa opzione, il membro del dominio dovrà negoziare la chiave con il controller di dominio. Le chiavi di sessione utilizzate per stabilire comunicazioni basate su un canale protetto tra i controller di dominio e i computer membro sono di gran lunga più avanzate in Windows 2000 che nei sistemi operativi Microsoft precedenti.
  
Pertanto, dal momento che i tre ambienti di protezione descritti in questa guida contengono controller di dominio Windows 2000 o versioni successive, l'impostazione **Membro di dominio: richiesta chiave di sessione avanzata (Windows 2000 o versioni successive)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti.
  
**Nota**: se l'impostazione è abilitata, non sarà possibile aggiungere computer nei domini Windows 2000 o Windows NT 4.0
  
#### Impostazioni di accesso interattivo
  
**Tabella 4.16 Opzioni di protezione: suggerimenti per l'impostazione di accesso interattivo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Mostra informazioni sull'utente quando la sessione è chiusa</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nome utente mostrato, nomi utente e di dominio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">non visualizzare l'ultimo nome utente</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">non richiedere CTRL+ALT+CANC</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">testo del messaggio per gli utenti che tentano l'accesso</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">titolo del messaggio per gli utenti che tentano l'accesso</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
<td style="border:1px solid black;">(Consultare i responsabili all'interno della propria organizzazione.)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">richiesta cambio password prima della scadenza</td>
<td style="border:1px solid black;">14 giorni</td>
<td style="border:1px solid black;">14 giorni</td>
<td style="border:1px solid black;">14 giorni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">richiedi smart card</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">funzionamento rimozione smart card</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Blocca workstation</td>
<td style="border:1px solid black;">Blocca workstation</td>
</tr>
</tbody>
</table>
  
##### Accesso interattivo: mostra informazioni sull'utente quando la sessione è chiusa
  
Permette di stabilire se il nome account dell'ultimo utente che ha effettuato l'accesso ai computer client dell'organizzazione verrà visualizzato sullo schermo di accesso Windows di ciascun computer. L'attivazione di questa impostazione impedisce agli intrusi di raccogliere visivamente i nomi degli account dagli schermi dei computer desktop o portatili dell'organizzazione.
  
L'impostazione **Accesso interattivo: mostra informazioni utente quando la sessione è chiusa** è configurata su **Non definito** per gli ambienti LC ed EC. È configurata su **Nome utente visualizzato, nomi utente e di dominio** nel criterio server di base per l'ambiente SSLF.
  
##### Accesso interattivo: non visualizzare l'ultimo nome utente
  
Determina se nella schermata di accesso di Windows debba essere visualizzato il nome dell'ultimo utente che ha effettuato l'accesso al computer. Se si attiva questa impostazione di criterio, il nome dell'ultimo utente che ha effettuato l'accesso non sarà mostrato nella finestra di dialogo **Accesso a Windows.**
  
L'impostazione **Accesso interattivo: non visualizzare l'ultimo nome utente** è configurata su **Abilitato** nel criterio server di base per tutti i tre ambienti definiti in questa guida.
  
##### Accesso interattivo: non richiedere CTRL + ALT + CANC
  
Questa impostazione di criterio determina se un utente deve premere CTRL + ALT + CANC per poter accedere a Windows. Se si disabilita questa opzione, tutti gli utenti dovranno premere CTRL+ALT+CANC per poter accedere a Windows (a meno che non utilizzino una smart card per l’accesso a Windows).
  
L'impostazione **Accesso interattivo: non richiedere CTRL + ALT + CANC** è configurata su **Disabilitato** nel criterio base di tutti e tre gli ambienti definiti in questa guida, allo scopo di ridurre il rischio che un pirata informatico intercetti le password degli utenti tramite un programma cavallo di Troia.
  
##### Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso
  
Consente di specificare un messaggio di testo che viene visualizzato agli utenti quando effettuano l'accesso. Questo testo viene utilizzato principalmente per motivi legali, ad esempio per informare gli utenti delle conseguenze di un accesso non autorizzato o un uso improprio delle informazioni aziendali o per avvisarli che le loro azioni potrebbero essere controllate.
  
L'opzione di protezione **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** è consigliata. Consultare i responsabili all'interno della propria organizzazione per determinare l'esatto contenuto del messaggio.
  
**Nota:** le impostazioni **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** e **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** devono essere entrambe abilitate perché una delle due funzioni correttamente.
  
##### Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso
  
Questa impostazione di criterio consente di specificare un titolo che verrà visualizzato nella barra del titolo della finestra per l'accesso interattivo al sistema. La motivazione per questo criterio è uguale a quella per l'opzione **Testo del messaggio per gli utenti che tentano l’accesso**.
  
Quindi, l'opzione di protezione **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** è consigliata. Consultare i responsabili all'interno della propria organizzazione per determinare l'esatto contenuto del messaggio.
  
**Nota:** le impostazioni **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** e **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** devono essere entrambe abilitate perché una delle due funzioni correttamente.
  
##### Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)
  
Questa impostazione di criterio determina se un utente può accedere a un dominio Windows utilizzando le informazioni sull'account memorizzate nella cache. Le informazioni di accesso per gli account di dominio possono essere memorizzate nella cache locale, in modo che un utente possa accedere comunque anche se non è possibile contattare un controller di dominio per gli accessi successivi. Questa funzionalità può consentire agli utenti di accedere dopo che il loro account è stato disattivato o è stato cancellato, poiché la workstation non contatta il controller di dominio. Questa impostazione del criterio consente di specificare per quanti utenti univoci è possibile memorizzare informazioni nella cache locale. Se si configura questa impostazione su 0, l'accesso cache è disattivato.
  
L'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** è configurato a **0** nel criterio di base per gli ambienti EC e SSLF. Nell'ambiente LC, l'impostazione è configurata su **1** per consentire l'accesso dei client legittimi quando questi non riescono a contattare il controller di dominio.
  
##### Accesso interattivo: richiesta cambio password prima della scadenza
  
Questa impostazione di criterio determina con quanti giorni di anticipo gli utenti vengono avvisati della scadenza imminente della password. La sezione di "Criteri di account" nel Capitolo 3 consiglia di impostare per le password una scadenza periodica. È importante informare con un certo preavviso gli utenti che la password sta per scadere, per evitare che la password scada senza che se ne rendano conto. Ciò potrebbe confondere gli utenti locali che riscontrano problemi quando cercano di cambiare la password. Le scadenze impreviste impediscono inoltre agli utenti remoti di accedere attraverso connessioni dial-up o VPN (virtual private networking).
  
Quindi, l'impostazione **Accesso interattivo: richiesta cambio password prima della scadenza** è configurata per impostazione predefinita su 14 giorni nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation
  
Per gli account di dominio, questa impostazione di criterio determina se per sbloccare un computer deve essere contattato un controller di dominio. Questa impostazione di criterio risolve una potenziale vulnerabilità simile a quella dell'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)**. Un utente potrebbe scollegare il cavo di rete del server e sbloccare il server utilizzando una vecchia password, senza venire autenticato.
  
Per evitare tale evento, l'impostazione **Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Importante**: questa impostazione di criterio concerne i computer con Windows 2000, Windows  XP, e Windows Server 2003, ma non è disponibile tramite gli strumenti per la gestione della configurazione della protezione di Windows 2000.
  
##### Accesso interattivo: richiedi smart card
  
Questa impostazione di criterio richiede agli utenti di accedere a un computer con una smart card. La protezione è migliore quando gli utenti devono utilizzare per l'autenticazione password lunghe e complicate, soprattutto se devono modificare le loro password regolarmente. In questo modo, si riducono le probabilità che un pirata informatico riesca a determinare la password di un utente tramite un attacco di tipo "brute force". Tuttavia, è difficile convincere gli utenti a scegliere password complicate e anche queste sono comunque vulnerabili ad attacchi brute-force.
  
L'uso di smart card, invece che di password, per l'autenticazione aumenta sensibilmente la protezione, perché grazie alla moderna tecnologia è quasi impossibile per un pirata informatico impersonare un altro utente. Le smart card che richiedono l'uso di PIN forniscono un doppio fattore di autenticazione: l'utente deve possedere la smart card e conoscere il PIN. Dopo aver acquisito il traffico di autenticazione tra il computer dell'utente e il controller di dominio, per un pirata informatico risulta estremamente difficile decrittografarlo. Anche se ci riesce, al successivo accesso in rete dell'utente verrà generata una nuova chiave di sessione per crittografare il traffico tra l'utente e il controller di dominio.
  
Microsoft consiglia l'uso di smart card o di altre tecnologie di autenticazione avanzata. Tuttavia, è consigliabile attivare solo l'opzione **Accesso interattivo: richiedi smart card** se le smart card sono già in uso. Per questa ragione, questa impostazione di criterio è configurata su **Non definito** nel criterio base degli ambienti LC ed EC. Questa impostazione di criterio è configurata su **Disabilitato.** nel criterio di base per l'ambiente SSLF.
  
##### Accesso interattivo: funzionamento rimozione Smart card
  
determina l'azione conseguente alla rimozione della smart card dal lettore da parte di un utente connesso. Se si configura questa impostazione su **Blocca workstation**, la workstation viene bloccata quando la smart card viene rimossa, permettendo agli utenti di allontanarsi dalla postazione, portare con sé la smart card e mantenere comunque una sessione protetta. Se si configura questa impostazione su **Imponi disconnessione**, l'utente è automaticamente disconnesso quando la smart card viene tolta.
  
L'impostazione **Accesso interattivo: funzionamento rimozione Smart card** è configurata su **Non definito** nel criterio di base per l'ambiente LC e su **Blocca workstation** per gli ambienti EC e SSLF.
  
#### Impostazioni dei client di rete Microsoft
  
**Tabella 4.17 Opzioni di Protezione: suggerimenti per le impostazioni dei client di rete Microsoft**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">aggiungi firma digitale alle comunicazioni (sempre)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">aggiungi firma digitale alla comunicazione client (se autorizzato dal server)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">invia password non crittografata per la connessione ai server SMB di terzi</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)
  
Questa impostazione di criterio determina se il componente client SMB deve richiedere la firma del pacchetto. Se si abilita questa opzione, si impedisce al client di rete Microsoft di comunicare con un server di rete Microsoft, a meno che il server non accetti di firmare il pacchetto SMB. Negli ambienti misti con client legacy è importante impostare questa opzione su **Disabilitato**, perché questi client non possono eseguire l’autenticazione o accedere ai controller di dominio. È possibile, tuttavia, utilizzare questa impostazione in ambienti con Windows 2000, Windows XP e Windows Server 2003. Gli ambienti EC e SSLF definiti in questa guida contengono computer che utilizzano unicamente questi sistemi operativi e che quindi supportano tutti le firme digitali.
  
Pertanto, per aumentare la protezione delle comunicazioni tra i sistemi di questi ambienti, l'impostazione **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** è configurata su **Abilitato** nel criterio di base per gli ambienti EC e SSLF.
  
##### Client di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal server)
  
Questa impostazione di criterio determina se il client SMB tenterà di negoziare la firma del pacchetto SMB. L'implementazione della firma digitale nelle reti Windows facilita la prevenzione del dirottamento delle sessioni. Se si abilita questa impostazione, il client di rete Microsoft nei server membro richiede la firma solo se i server con cui sta comunicando accettano la comunicazione con firma digitale.
  
L'impostazione **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi
  
Se si attiva questo criterio, il redirector SMB è autorizzato a inviare password con testo in chiaro ai server SMB non Microsoft che non supportano la crittografia della password durante l'autenticazione.
  
L'impostazione **Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi** è configurata per impostazione predefinita su **Disabilitato** nel criterio base per i tre ambienti definiti in questa guida, a meno che i requisiti di un'applicazione non prevalgano sull'esigenza di mantenere segrete le password.
  
#### Impostazioni dei server di rete Microsoft
  
**Tabella 4.18 Opzioni di Protezione: suggerimenti per le impostazioni dei server di rete Microsoft**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">periodo di inattività richiesto prima di sospendere la sessione</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">aggiungi firma digitale alle comunicazioni (sempre)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">aggiungi firma digitale alla comunicazione client (se autorizzato dal client)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">disconnetti automaticamente i client al termine dell'orario di accesso</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione
  
Questa impostazione di criterio determina il periodo di inattività continua che deve trascorrere in una sessione SMB prima che avvenga la disconnessione a causa dell'inattività. Gli amministratori possono utilizzare questa impostazione per controllare quando un computer deve sospendere una sessione SMB inattiva. Se l'attività del client riprende, la sessione viene automaticamente ristabilita.
  
L'impostazione **Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione** è configurata su **15 minuti** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)
  
Questo criterio determina se il componente server SMB deve richiedere la firma del pacchetto per autorizzare il proseguimento della comunicazione con un client SMB. Windows 2000 Server, Windows 2000 Professional, Windows Server 2003 e Windows XP Professional includono versioni di SMB che supportano l'autenticazione reciproca. Questa modalità di autenticazione previene gli attacchi con dirottamento di sessione e supporta l'autenticazione dei messaggi, impedendo gli attacchi di tipo man-in-the-middle. La firma SMB fornisce questa autenticazione dato che inserisce una firma digitale in ogni pacchetto SMB, che viene quindi verificato sia dal client sia dal server. Se i computer vengono configurati in modo da ignorare tutte le comunicazioni SMB prive di firma digitale, le applicazioni e i sistemi operativi precedenti non possono connettersi. Se tutte le funzioni di firma SMB sono completamente disattivate, i computer sono vulnerabili agli attacchi che tentano di appropriarsi delle sessioni di comunicazione.
  
L'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** è configurata su **Disabilitato** nel criterio base per l'ambiente LC e su **Abilitato** per gli ambienti EC e SSLF.
  
##### Server di rete Microsoft: aggiungi firma di comunicazione digitale alle comunicazioni client (se autorizzato dal client)
  
Questa impostazione di criterio determina se il server SMB deve negoziare la firma dei pacchetti SMB con i client che la richiedono. Windows 2000 Server, Windows 2000 Professional, Windows Server 2003 e Windows XP Professional includono versioni di SMB che supportano l'autenticazione reciproca. Questa modalità di autenticazione blocca gli attacchi con dirottamento di sessione e supporta l'autenticazione dei messaggi, impedendo gli attacchi di tipo man-in-the-middle. La firma SMB fornisce questa autenticazione dato che inserisce una firma digitale in ogni pacchetto SMB, che viene quindi verificato sia dal client sia dal server. Se i computer vengono configurati in modo da ignorare tutte le comunicazioni SMB prive di firma digitale, le applicazioni e i sistemi operativi precedenti non possono connettersi. Se tutte le funzioni di firma SMB sono completamente disattivate, i computer sono vulnerabili agli attacchi che tentano di appropriarsi delle sessioni di comunicazione.
  
L'impostazione **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal client)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso
  
L'impostazione di questo criterio determina se scollegare gli utenti connessi a un computer di rete al di fuori dell'orario di connessione valido per l'account. Questa impostazione influisce sul componente SMB. Se nell'organizzazione è stato configurato l'orario di accesso, è consigliabile abilitare questa impostazione di criterio. In caso contrario, gli utenti privi dei diritti di accesso alle risorse di rete al di fuori dell'orario di accesso potrebbero continuare effettivamente a utilizzare tali risorse tramite le sessioni stabilite durante l'orario di accesso.
  
L'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
#### Impostazioni di accesso alla rete
  
**Tabella 4.19 Opzioni di protezione: suggerimenti per le impostazioni di accesso alla rete**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">consenti conversione anonima SID/nome</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">non consentire l'enumerazione anonima degli account SAM</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">non consentire l'enumerazione anonima degli account e le condivisioni SAM</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">consenti l'accesso libero agli utenti anonimi</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">named pipe a cui è possibile accedere in modo anonimo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">COMNAP, COMNODE, SQL\QUERY, SPOOLSS, LLSRPC, netlogon, lsarpc, samr, browser</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">percorsi del Registro di sistema ai quali è possibile accedere in modo remoto</td>
<td style="border:1px solid black;">System\<br />
CurrentControlSet\<br />
Control\<br />
Product Options;
System\<br />
CurrentControlSet\<br />
Control\
Applicazioni del server;
Software\Microsoft\
Windows NT\Current
Versione</td>
<td style="border:1px solid black;">System\<br />
CurrentControlSet\<br />
Control\<br />
Product Options;
System\<br />
CurrentControlSet\<br />
Control\
Applicazioni del server;
Software\Microsoft\
Windows NT\Current
Versione</td>
<td style="border:1px solid black;">System\<br />
CurrentControlSet\<br />
Control\<br />
Product Options;
System\<br />
CurrentControlSet\<br />
Control\
Applicazioni del server;
Software\Microsoft\
Windows NT\Current
Versione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto</td>
<td style="border:1px solid black;">(per le informazioni di impostazione vedere la seguente sottosezione)</td>
<td style="border:1px solid black;">(per le informazioni di impostazione vedere la seguente sottosezione)</td>
<td style="border:1px solid black;">(per le informazioni di impostazione vedere la seguente sottosezione)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">limita accesso anonimo a named pipe e condivisioni</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">condivisioni alle quali è possibile accedere in modo anonimo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">modello di condivisione e protezione per gli account locali</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione come se stessi</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione come se stessi</td>
<td style="border:1px solid black;">Classico: gli utenti locali effettuano l'autenticazione come se stessi</td>
</tr>
</tbody>
</table>
  
##### Accesso di rete: consenti conversione anonima SID/NOME
  
Questa impostazione di criterio determina se un utente anonimo può richiedere gli attributi SID di un altro utente. Se questa impostazione è abilitata, un utente potrebbe utilizzare il SID degli amministratori noto per ottenere il nome reale dell'account Administrator predefinito, anche se tale account è stato rinominato. Tale persona potrebbe quindi utilizzare l'account per avviare un attacco di determinazione della password.
  
L'impostazione **Accesso di rete: consenti conversione anonima SID/NOME** è configurata su **Non definito** nel criterio base degli ambienti LC ed EC. Questa impostazione di criterio è configurata su **Disabilitato** nel criterio di base per l'ambiente SSLF.
  
##### Accesso di rete: non consentire l'enumerazione anonima degli account SAM
  
Questa impostazione di criterio determina le autorizzazioni aggiuntive da assegnare per le connessioni anonime al computer. Gli utenti anonimi di Windows possono svolgere determinate attività, ad esempio l'enumerazione dei nomi degli account di dominio. Questa funzionalità risulta utile, ad esempio, quando un amministratore intende concedere agli utenti l'accesso a un dominio attendibile in cui non venga mantenuta una relazione di trust reciproca. Tuttavia, anche quando l'impostazione è abilitata, gli utenti anonimi avranno comunque accesso a tutte le risorse per le quali dispongono di autorizzazioni che includono in modo esplicito il gruppo predefinito speciale **ACCESSO ANONIMO**.
  
L'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM
  
Questa impostazione di criterio determina se l'enumerazione anonima di account e condivisioni SAM è consentita.
  
L'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete
  
Questa impostazione di criterio determina se le impostazioni di **Gestione nomi utente e password archiviati** devono consentire o meno il salvataggio di password, credenziali o profili .NET Passport da riutilizzare dopo aver ottenuto l’autenticazione nel dominio.
  
L'impostazione **Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti di protezione definiti in questa guida.
  
**Nota**: le modifiche apportate a questa impostazione del criterio non avranno effetto fino al riavvio di Windows.
  
##### Accesso di rete: consenti l'accesso libero agli utenti anonimi
  
Questa impostazione di criterio determina le autorizzazioni aggiuntive da assegnare per le connessioni anonime al computer. Se questa impostazione di criterio viene abilitata, gli utenti Windows anonimi possono svolgere determinate attività, ad esempio l'enumerazione dei nomi degli account di dominio e delle condivisioni di rete. Un utente non autorizzato potrebbe elencare in modo anonimo i nomi degli account e le risorse condivise e utilizzare queste informazioni per cercare di scoprire le password o per eseguire altri attacchi.
  
Quindi, l'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi** è configurata su **Disabilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Nota:** i domini con questa impostazione non possono stabilire o mantenere relazioni di trust con domini o controller di dominio Windows NT 4.0.
  
##### Accesso di rete: named pipe a cui è possibile accedere in modo anonimo
  
Questa impostazione di criterio determina le sessioni di comunicazione (named pipe) a cui verranno assegnati gli attributi e le autorizzazioni che consentono l’accesso anonimo.
  
Applicare i valori predefiniti per l'impostazione **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo** nell'ambiente SSLF. I valori predefiniti sono rappresentati dai seguenti named pipe:
  
-   COMNAP – accesso alla sessione SNA
  
-   COMNODE – accesso alla sessione SNA
  
-   SQL\\QUERY – accesso istanza SQL
  
-   SPOOLSS – Servizio di Spooler
  
-   LLSRPC – Servizio registrazione licenze
  
-   Netlogon – Servizio accesso rete
  
-   Lsarpc – Accesso LSA
  
-   Samr – Accesso SAM
  
-   browser – Servizio Browser di computer
  
    **Importante:** se è necessario abilitare questa impostazione, aggiungere solo le named pipe necessarie per supportare le applicazioni dell’ambiente. Come per tutte le impostazioni consigliate in questa guida, è essenziale testare accuratamente questa impostazione di criterio prima di installarla in un ambiente di produzione
  
##### Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto.
  
Questa impostazione di criterio determina a quali percorsi del Registro di sistema è possibile accedere tramite la rete.
  
L'impostazione **Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto** è configurata per impostazione predefinita su Abilitato nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Nota:** dopo aver impostato questa impostazione di criterio, è necessario avviare il servizio Registro di sistema remoto per consentire agli utenti autorizzati di accedere al Registro di sistema tramite la rete.
  
##### Accesso di rete: percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto
  
Questa impostazione di criterio determina quali percorsi e sottopercorsi del Registro di sistema è possibile accedere tramite la rete.
  
I valori predefiniti per l'impostazione **Accesso di rete: percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto** sono applicati a tutti e tre gli ambienti di protezione definiti in questa guida. Seguono i valori predefiniti dei percorsi e sottopercorsi del Registro di sistema:
  
-   System\\CurrentControlSet\\Control\\Print\\Printers
  
-   System\\CurrentControlSet\\Services\\Eventlog
  
-   Software\\Microsoft\\OLAP Server
  
-   Software\\Microsoft\\Windows NT\\CurrentVersion\\Print
  
-   Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows
  
-   System\\CurrentControlSet\\Control\\ContentIndex
  
-   System\\CurrentControlSet\\Control\\Terminal Server
  
-   System\\CurrentControlSet\\Control\\Terminal Server\\UserConfig
  
-   System\\CurrentControlSet\\Control\\Terminal Server\\DefaultUserConfiguration
  
-   Software\\Microsoft\\Windows NT\\CurrentVersion\\Perflib
  
-   System\\CurrentControlSet\\Services\\SysmonLog
  
##### Accesso di rete: limita accesso anonimo a named pipe e condivisioni
  
Questa impostazione di criterio può essere utilizzata per limitare l'accesso anonimo alle condivisioni e alle named pipe in base alle seguenti impostazioni
  
-   **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo**
  
-   **Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo**
  
L'impostazione **Accesso di rete: limita accesso anonimo a named pipe e condivisioni** è configurata per impostazione predefinita su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo
  
Questa impostazione di criterio determina a quali condivisioni possono accedere gli utenti anonimi. L’impostazione predefinita ha un effetto limitato, poiché tutti gli utenti devono essere autenticati per poter accedere alle risorse condivise del server.
  
L'impostazione **Accesso di rete: condivisioni alle quali è possibile accedere in modo anonimo** è configurata su **Non definito** per gli ambienti LC ed EC e su **Nessuno** per l'ambiente SSLF.
  
**Nota**: è molto rischioso abilitare questa opzione di Criteri di gruppo, perché si consente a tutti gli utenti della rete di accedere a tutte le condivisioni indicate nell'elenco. Se questa impostazione di criterio è abilitata, dati riservati potrebbero essere messi a rischio o danneggiati.
  
##### Accesso di rete: modello di condivisione e protezione per gli account locali
  
Questa impostazione di criterio determina la modalità di autenticazione degli accessi in rete che utilizzano account locali. La configurazione **Classico** consente un controllo preciso dell'accesso alle risorse, compresa la possibilità di assegnare tipi di accesso differenti a utenti diversi per la stessa risorsa. L'impostazione **Solo Guest** consente di trattare tutti gli utenti in modo uguale. In questo contesto, tutti gli utenti si autenticano come **Solo Guest** per ricevere lo stesso livello di accesso a una determinata risorsa.
  
L'impostazione **Accesso di rete: modello di condivisione e protezione per gli account locali** è configurata per impostazione predefinita su **Classico** nel criterio di base per tutti i tre ambienti definiti in questa guida.
  
#### Impostazioni di protezione di rete
  
**Tabella 4.20 Opzioni di protezione: suggerimenti per le impostazioni di protezione di rete**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">non memorizzare il valore hash di LAN Manager al prossimo cambio di password</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">livello di autenticazione di LAN Manager</td>
<td style="border:1px solid black;">Invia solo risposte NTLMv2</td>
<td style="border:1px solid black;">Invia solo risposta NTLMv2\Rifiuta LM</td>
<td style="border:1px solid black;">Invia solo risposte NTLMv2\Rifiuta LM e NTLM</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">requisiti per la firma client LDAP</td>
<td style="border:1px solid black;">Negozia firma</td>
<td style="border:1px solid black;">Negozia firma</td>
<td style="border:1px solid black;">Negozia firma</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)</td>
<td style="border:1px solid black;">Nessun minimo</td>
<td style="border:1px solid black;">Tutte le impostazioni abilitate</td>
<td style="border:1px solid black;">Tutte le impostazioni abilitate</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)</td>
<td style="border:1px solid black;">Nessun minimo</td>
<td style="border:1px solid black;">Tutte le impostazioni abilitate</td>
<td style="border:1px solid black;">Tutte le impostazioni abilitate</td>
</tr>
</tbody>
</table>
  
##### Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password
  
Questa impostazione di protezione determina se il valore hash di LAN Manager (LM) per la nuova password verrà memorizzato al successivo cambio di password. L'hash di LAN Manager è relativamente debole e vulnerabile agli attacchi, rispetto all'hash di Windows NT crittograficamente più forte.
  
Per questa ragione, l'impostazione **Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti di protezione definiti in questa guida.
  
**Nota:** quando questa impostazione è attivata, sistemi operativi precedenti molto vecchi e alcune applicazioni di terzi potrebbero non funzionare. Inoltre, alla sua attivazione, è necessario cambiare la password su tutti gli account.
  
##### Protezione di rete: livello di autenticazione di LAN Manager
  
Questo criterio determina quale protocollo di autenticazione Challenge/Response viene utilizzato per l'accesso alla rete. Questa scelta interessa il livello del protocollo di autenticazione utilizzato dai computer client, il livello di protezione negoziato, ed il livello di autenticazione accettato dai server come segue. I numeri nella seguente tabella sono le impostazioni del valore di registro **LMCompatibilityLevel**.
  
**Tabella 4.21 Impostazioni di valore del registro MCompatibilityLevel**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Valore</th>
<th style="border:1px solid black;" >Protocollo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">I client utilizzano l'autenticazione LM e NTLM; non utilizzano mai la protezione di sessione NTLMv2.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">I client utilizzano l'autenticazione LM e NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">I client utilizzano solo l'autenticazione NTLM e la protezione della sessione NTLMv2, se supportate dal server.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">I client utilizzano solo l'autenticazione NTLMv2 e la protezione della sessione NTLMv2 se supportata dal server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">I client utilizzano solo l'autenticazione NTLM e la protezione della sessione NTLMv2, se supportate dal server. Il controller di dominio rifiuta l'autenticazione LM.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">I client utilizzano solo l'autenticazione NTLMv2 e la protezione della sessione NTLMv2 se supportata dal server. Il controller di dominio rifiuta l'autenticazione di LM e NTLM ed accetta soltanto NTLMv2.</td>
</tr>
</tbody>
</table>
  
Per questa impostazione è consigliabile impostare il livello più alto possibile, tenendo conto delle seguenti indicazioni:
  
In un ambiente che contiene solo Windows NT 4.0 SP4, Windows 2000, e Windows XP Professional, impostare questo criterio su **Invia solo risposta NTLMv2\\Rifiuta LM e NTLM** in tutti i client e, dopo aver configurato tutti i client, impostare **Invia solo risposta NTLMv2\\Rifiuta LM e NTLM** in tutti i server. Costituiscono un'eccezione i server di Routing e Accesso remoto basati su Windows Server 2003, che non funzionano in modo corretto se per questo criterio è impostato un valore più alto di **Invia solo risposta NTLMv2\\Rifiuta LM**.
  
L'ambiente EC può dover supportare server di Routing e di Accesso remoto, quindi l'impostazione **Protezione di rete: livello di autenticazione di LAN Manager** per quest'ambiente è configurata su **Invia solo risposta NTLMv2\\Rifiuta LM** nel criterio base. I server di Routing e di Accesso remoto non sono supportati nell'ambiente SSLF, dunque l'impostazione di criterio per quest'ambiente è configurata su **Invia solo risposte NTLMv2\\Rifiuta LM e NTLM.**
  
Se si possiedono client Windows 9x ed è possibile installare in ognuno di essi DSClient, configurare questa impostazione di criterio su **Invia solo risposte NTLMv2\\Rifiuta LM e NTLM** sui computer con Windows NT (Windows NT, Windows 2000 e Windows XP Professional). In caso contrario è necessario impostare un valore non superiore di **Invia solo risposte NTLMv2** nel criterio base dei computer che non utilizzano Windows 9x, cioè come l'impostazione è configurata per l'ambiente LC.
  
Se dopo aver abilitato questo criterio alcune applicazioni non funzionano, eseguire il roll back, un passaggio alla volta, per scoprire la causa del problema. Configurare questa impostazione di criterio almeno su **Invia LM e NTLM. Utilizza la protezione sessione NTLMv2 se negoziata** nel criterio base su tutti i computer. Generalmente è possibile configurarlo su **Invia solo risposte NTLMv2** su tutti i computer dell'ambiente.
  
##### Protezione di rete: requisiti per la firma client LDAP
  
Questa impostazione di criterio determina il livello di firma dei dati che viene richiesto per conto dei client che emettono richieste di binding LDAP. Il traffico di rete privo di firma è esposto ad attacchi man-in-the-middle. Di conseguenza, nel caso di un server LDAP, un pirata informatico potrebbe indurre un server a prendere decisioni sulla base di richieste false del client LDAP.
  
Quindi, l'impostazione **Protezione di rete: requisiti per la firma client LDAP** è configurata su **Negozia firma** nel criterio base per tutti i tre ambienti definiti in questa guida.
  
##### Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)
  
Questa impostazione di criterio consente a un client di richiedere la negoziazione della riservatezza (crittografia) dei messaggi, l'integrità dei messaggi, la crittografia a 128 bit o la protezione di sessione NTLMv2. Configurare questa impostazione del criterio sul massimo livello di protezione possibile, ma ricordare che bisogna comunque permettere alle applicazioni sulla rete di funzionare. La corretta configurazione di questa impostazione di criterio consentirà di proteggere il traffico di rete proveniente da server basati su NTLM SSP da attacchi man-in-the-middle ed evitare intercettazioni dei dati.
  
L'impostazione **Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)** è configurata su **Nessun minimo** nel criterio base dell'ambiente LC. Tutte le impostazioni sono abilitate per gli ambienti EC e SSLF.
  
##### Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)
  
Questa impostazione di criterio consente a un server di richiedere la negoziazione della riservatezza (crittografia) dei messaggi, l'integrità dei messaggi, la crittografia a 128 bit o la protezione di sessione NTLMv2. Configurare questa impostazione del criterio sul massimo livello di protezione possibile, ma ricordare che bisogna comunque permettere alle applicazioni sulla rete di funzionare. Come per l'impostazione precedente, la corretta configurazione di questa impostazione di criterio consentirà di proteggere il traffico di rete proveniente da client basati su NTLM SSP da attacchi man-in-the-middle ed evitare intercettazioni dei dati.
  
L'impostazione **Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)** è configurata su **Nessun minimo** nel criterio base dell'ambiente LC. Tutte le impostazioni sono abilitate per gli ambienti EC e SSLF.
  
#### Impostazioni della Console di ripristino di emergenza
  
**Tabella 4.22 Opzioni di protezione: suggerimenti di impostazione della Console di ripristino di emergenza**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">consenti accesso di amministrazione automatico</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Console di ripristino di emergenza: consente l'accesso di amministrazione automatico
  
Questa impostazione di criterio determina se deve essere specificata la password dell’account Administrator per accedere al sistema. Se questa impostazione di criterio è abilitata, la Console ripristino di emergenza non richiede di specificare la password e consente l’accesso automatico al computer. La Console di ripristino di emergenza può essere molto utile se un computer ha problemi di avvio. Tuttavia, l'attivazione di questa opzione può avere effetti negativi, perché chiunque potrebbe arrestare il server staccando la corrente, riavviarlo, scegliere **Console ripristino di emergenza** dal menu **Riavvia**, quindi assumere il controllo completo del server.
  
Quindi, l'impostazione **Console di ripristino di emergenza: consente l'accesso di amministrazione automatico** è configurata per impostazione predefinita su **Disabilitato** nel criterio base di tutti i tre ambienti definiti in questa guida. Per utilizzare la Console ripristino di emergenza quando questa opzione è disabilitata, l’utente deve immettere nome utente e password per accedere all’account della Console ripristino di emergenza.
  
##### Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle
  
Abilitando questa impostazione di criterio, è possibile rendere disponibile il comando **SET** della Console di ripristino di emergenza, che consente di impostare le seguenti variabili di ambiente della console:
  
-   **AllowWildCards**. abilita il supporto dei caratteri jolly per alcuni comandi, ad esempio per il comando DEL.
  
-   **AllowAllPaths**. consente l'accesso a tutti i file e a tutte le cartelle del computer.
  
-   **AllowRemovableMedia**. consente di copiare i file su supporti rimovibili, ad esempio su dischi floppy.
  
-   **NoCopyPrompt**. Non viene richiesta conferma per la sovrascrittura di file
  
Per la massima protezione, l'impostazione **Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle** è configurata su **Disabilitato** nel criterio base dell'ambiente SSLF. Tuttavia, questa impostazione del criterio è configurata su **Abilitato** per gli ambienti LC ed EC.
  
#### Impostazioni di arresto
  
**Tabella 4.23 Opzioni di protezione: suggerimenti per le impostazioni di arresto**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">consente di arrestare il sistema senza effettuare l'accesso</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">cancella il file di paging della memoria virtuale</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
##### Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso
  
Determina se un computer può essere chiuso da un utente a cui non è richiesto di accedere a Windows. Gli utenti che hanno accesso alla console possono arrestare il sistema. Un pirata informatico potrebbe connettersi al server tramite Servizi terminal e arrestarlo o riavviarlo senza farsi riconoscere.
  
Quindi, l'impostazione **Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso** è configurata per impostazione predefinita su **Disabilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Arresto del sistema: cancella il file di paging della memoria virtuale
  
Determina se il contenuto del file di paging della memoria virtuale deve essere cancellato all’arresto del sistema. Se questa impostazione di criterio è abilitata, il contenuto del file di paging del sistema viene cancellato ogni volta che il computer viene arrestato normalmente. Se si abilita questa impostazione di criterio, nei computer portatili in cui è disabilitata la sospensione viene cancellato anche il contenuto del file di sospensione (hiberfil.sys). Richiederà più tempo per arrestare e riavviare il server, specialmente nel caso di server con file di paging di notevoli dimensioni.
  
Per queste ragioni, l'impostazione **Arresto del sistema: cancella il file di paging della memoria virtuale** è configurata su **Disabilitato** in tutti i tre ambienti definiti in questa guida.
  
**Nota**: un pirata informatico con accesso fisico al server potrebbe aggirare questa contromisura semplicemente scollegando il server dalla presa di alimentazione.
  
#### Impostazioni della crittografia di sistema
  
**Tabella 4.24 Opzioni di Protezione: suggerimenti per le impostazioni della crittografia di sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">imponi protezione chiave avanzata per chiavi utente archiviate nel computer</td>
<td style="border:1px solid black;">L'utente riceve una richiesta al primo utilizzo della chiave</td>
<td style="border:1px solid black;">L'utente riceve una richiesta al primo utilizzo della chiave</td>
<td style="border:1px solid black;">L'utente deve immettere una password ogni volta che utilizza una chiave</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">utilizza algoritmi FIPS compatibili per crittografia, hash e firma</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Crittografia di sistema: imponi protezione chiave avanzata per chiavi utente archiviate nel computer
  
Questa impostazione di criterio determina se per utilizzare le chiavi private degli utenti, ad esempio le chiavi S-MIME, è necessaria una password. Se questo criterio è configurato in modo che gli utenti debbano specificare una password (diversa da quella di dominio) ogni volta che utilizzano una chiave, un pirata informatico che assumesse il controllo del computer e intercettasse la password di accesso avrebbe comunque maggiori difficoltà ad accedere alle chiavi utente memorizzate nel computer locale.
  
Per rendere più agevole l’utilizzo del sistema, negli ambienti LC ed EC, l'impostazione **Crittografia di sistema: imponi protezione chiave avanzata per chiavi utente archiviate nel computer** è configurata su **L'utente riceve una richiesta al primo utilizzo della chiave** nel criterio base. Per fornire protezione aggiuntiva, questa impostazione di criterio è configurata su **L'utente deve immettere una password ogni volta che utilizza una chiave** per l'ambiente SSLF.
  
##### Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma
  
Questa impostazione di protezione determina se il provider di protezione TLS/SSL (Transport Layer Security/Secure Sockets Layer) supporta solo il pacchetto di crittografia TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA. Nonostante questa impostazione di criterio aumenti la protezione, la maggior parte dei siti Web pubblici che sono protetti da TLS o SSL non supporta questi algoritmi. Anche molti computer client non sono configurati per supportare questi algoritmi.
  
Per queste ragioni, l'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash, e firma** è configurata su **Disabilitato** nel criterio base per ambienti LC ed EC. Questa impostazione di criterio è **Abilitata** per l'ambiente SSLF.
  
#### Impostazioni degli oggetti di sistema
  
**Tabella 4.24 Opzioni di protezione: suggerimenti per le impostazioni degli oggetti di sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators</td>
<td style="border:1px solid black;">Creatore oggetto</td>
<td style="border:1px solid black;">Creatore oggetto</td>
<td style="border:1px solid black;">Creatore oggetto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Potenzia le autorizzazioni predefinite degli oggetti di sistema interni (ad esempio, i collegamenti simbolici)</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators
  
Questa impostazione di criterio consente di stabilire se il proprietario predefinito degli oggetti di sistema è il gruppo **Administrators** o il Creatore oggetto. Quando vengono creati oggetti di sistema, come proprietario di un nuovo oggetto verrà indicato l'account che ha lo creato anziché, in modo più generico, il gruppo **Administrators.**
  
L'impostazione **Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators** è configurata su **Creatore oggetto** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows
  
Questa impostazione di criterio determina se per tutti i sottosistemi deve essere ignorata la differenza tra maiuscole e minuscole. Nel sottosistema Microsoft Win32 viene ignorata la differenza tra maiuscole e minuscole. Tuttavia, il kernel supporta la differenziazione tra maiuscole e minuscole per altri sottosistemi, quali POSIX (Portable Operating System Interface for UNIX). Dal momento che in Windows non viene fatta distinzione tra maiuscole e minuscole, mentre il sottosistema POSIX distingue tra maiuscole e minuscole, non applicando questa impostazione un utente di questo sottosistema potrebbe creare un file con lo stesso nome di un altro file, ma con un uso diverso di maiuscole e minuscole. Una situazione del genere può bloccare un altro utente che accede a questi file con i normali strumenti Win32, perché solo uno dei file sarebbe disponibile.
  
Per garantire uniformità tra i nomi dei file, l'impostazione **Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
##### Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema interni (ad esempio, i collegamenti simbolici)
  
Questa impostazione di criterio determina il livello di potenza dell’elenco di controllo di accesso discrezionale (DACL) predefinito per gli oggetti, e gli aiuti ottengono degli oggetti che possono essere localizzati e contribuisce a proteggere gli oggetti che possono essere condivisi dai processi. Per rendere più potente l'elenco DACL è possibile utilizzare il valore predefinito **Abilitato**, consentendo agli utenti che non sono amministratori di leggere gli oggetti condivisi, ma non di modificare quelli che sono stati creati da altri utenti.
  
L'impostazione **Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema interni (ad esempio, i collegamenti simbolici)** è configurata su **Abilitato** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
#### Impostazioni di sistema
  
**Tabella 4.26 Opzioni di Protezione: suggerimenti per le impostazioni del sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Impostazioni di sistema: sottosistemi facoltativi</td>
<td style="border:1px solid black;">Nessuna</td>
<td style="border:1px solid black;">Nessuna</td>
<td style="border:1px solid black;">Nessuna</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
##### Impostazioni di sistema: sottosistemi facoltativi
  
Questa impostazione di criterio determina quali sistemi vengono utilizzati per supportare le applicazioni. Il valore predefinito di questo criterio in Windows Server 2003 è **POSIX**.
  
Per disabilitare il sottosistema POSIX, l'impostazione **Impostazioni di sistema: sottosistemi facoltativi** è configurata su **Nessuno** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
##### Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software
  
Questa impostazione di criterio permette di stabilire se i certificati digitali vengono elaborati quando un utente o un processo tentano di eseguire software con un'estensione del nome file exe. Consente di abilitare o disabilitare le regole certificati, ovvero un tipo di criteri di restrizione software. Mediante tali criteri è possibile creare un regola certificato che consenta o impedisca l'esecuzione di software con firma Microsoft Authenticode, in base al relativo certificato digitale associato. Perché le regole certificati siano operative, è necessario attivare questa impostazione di protezione.
  
L'impostazione **Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software** è configurata su **Abilitato** nell'ambiente SSLF. Tuttavia, è configurata su **Disabilitato** nell'ambiente EC e su **Non definito** nell'ambiente LC a causa del potenziale impatto sulle prestazioni.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Registro eventi
  
Nel Registro eventi vengono registrati gli eventi del sistema, mentre nel Registro di protezione vengono registrati gli eventi di controllo. Il contenitore Registro eventi di Criteri di gruppo viene utilizzato per definire gli attributi relativi ai registri eventi per le applicazioni, la protezione e il sistema, quali la dimensione massima del registro, i diritti di accesso, le impostazioni e i criteri di gestione. Le impostazioni dei registri eventi per le applicazioni, la protezione e il sistema sono configurate nel criterio MSBP e vengono applicate a tutti i server membro del dominio.
  
È possibile configurare le impostazioni del registro eventi in Windows Server 2003 con SP1 alla posizione seguente nell'ambito dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Registro eventi**
  
Questa sezione fornisce dettagli sulle impostazioni suggerite per le impostazioni del registro eventi MSBP per i tre ambienti definiti in questa guida. Per un riepilogo delle impostazioni richieste illustrate in questa sezione, vedere la cartella di lavoro di Excel con le impostazioni della "Windows Server 2003 Security Guide Settings" disponibile con la versione scaricabile di questa guida. Per informazioni sulla configurazione predefinita e una spiegazione dettagliata per ogni impostazione trattata nel presente capitolo, fare riferimento alla guida correlata, *Pericoli e contromisure: Impostazioni di protezione in Windows* *Server* *2003 e Windows* *XP*, disponibile all'indirizzo <http://technet.microsoft.com/it-it/library/dd162275>.
  
La tabella seguente riassume i consigli per l'impostazione del registro eventi per i tre tipi di ambienti definiti in questa guida. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna impostazione.
  
**Tabella 4.27 Suggerimenti per le impostazioni del Registro eventi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Dimensione massima registro applicazioni</td>
<td style="border:1px solid black;">16.384 KB</td>
<td style="border:1px solid black;">16.384 KB</td>
<td style="border:1px solid black;">16.384 KB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dimensione massima registro protezione</td>
<td style="border:1px solid black;">81.920 KB</td>
<td style="border:1px solid black;">81.920 KB</td>
<td style="border:1px solid black;">81.920 KB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Dimensione massima registro eventi di sistema</td>
<td style="border:1px solid black;">16.384 KB</td>
<td style="border:1px solid black;">16.384 KB</td>
<td style="border:1px solid black;">16.384 KB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro applicazione</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro applicazione</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impedisci accesso guest locale al registro eventi di sistema</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri gestione registro applicazione</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri gestione registro protezione</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri gestione registro eventi di sistema</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
<td style="border:1px solid black;">In base alle necessità</td>
</tr>
</tbody>
</table>
  
#### Dimensione massima registro applicazioni
  
Questa impostazione di criterio specifica la dimensione massima del registro eventi applicazioni, la cui capacità massima è di 4 GB. Tuttavia, queste dimensioni non sono raccomandate a causa del rischio di frammentazione della memoria, che causa prestazioni lente e una registrazione degli eventi non affidabile. I requisiti per la dimensione del registro applicazioni variano a seconda della funzione della piattaforma e della necessità di conservare record degli eventi relativi alle applicazioni.
  
L'impostazione **Dimensione massima registro applicazioni** è configurata per impostazione predefinita su **16.384 KB** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
#### Dimensione massima registro protezione
  
Questa impostazione di criterio specifica la dimensione massima del registro eventi di protezione, la cui capacità massima è di 4 GB. Impostare almeno 80 MB nei controller di dominio e nei server autonomi, in questo modo dovrebbero venire registrate informazioni sufficienti per effettuare controlli adeguati. Le dimensioni indicate per gli altri sistemi dipendono da fattori quali la frequenza con cui il registro viene esaminato, lo spazio disponibile su disco e così via.
  
L'impostazione **Dimensione massima registro protezione** è configurata per impostazione predefinita su **81.920 KB** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
#### Dimensione massima registro eventi di sistema
  
Questa impostazione di criterio specifica la dimensione massima del Registro eventi sistema, la cui capacità massima è di 4 GB. Tuttavia, queste dimensioni non sono raccomandate a causa del rischio di frammentazione della memoria, che causa prestazioni lente e una registrazione degli eventi non affidabile. I requisiti per la dimensione del Registro di sistema variano a seconda della funzione della piattaforma e della necessità di conservare record storici.
  
L'impostazione **Dimensione massima del registro eventi di sistema** è configurata per impostazione predefinita su **16.384 KB** nel criterio di base di tutti i tre ambienti definiti in questa guida.
  
#### Impedisci accesso guest locale al registro applicazione
  
Questa impostazione di criterio determina se gli ospiti possono accedere o meno al registro eventi Applicazioni. Per impostazione predefinita, in Windows Server 2003 con SP1 l'accesso guest è negato su tutti i computer. Quindi, questa impostazione di criterio non ha effetto reale sui computer con configurazioni predefinite.
  
Tuttavia, poiché è considerata una soluzione di protezione avanzata senza effetti collaterali, l'impostazione **Impedisci accesso guest locale al registro applicazione** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Nota**: questa impostazione non compare nell'oggetto Criteri del computer locale.
  
#### Impedisci accesso guest locale al registro applicazione
  
Questa impostazione di criterio determina se gli ospiti sono negati l'accesso al registro eventi di protezione. Per accedere al registro di protezione un utente deve avere il diritto utente **Gestione file registro di controllo e di protezione** (non definito in questa guida). Quindi, questa impostazione di criterio non ha effetto reale sui computer con configurazioni predefinite.
  
Tuttavia, poiché è considerata una soluzione di protezione avanzata senza effetti collaterali, l'impostazione **Impedisci accesso guest locale al registro applicazione** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Nota**: questa impostazione non compare nell'oggetto Criteri del computer locale.
  
#### Impedisci accesso guest locale al registro eventi di sistema
  
Questa impostazione di criterio determina se gli ospiti sono negati l'accesso al registro eventi di sistema. Per impostazione predefinita, in Windows Server 2003 con SP1 l'accesso guest è negato su tutti i computer. Quindi, questa impostazione di criterio non ha effetto reale sui computer con configurazioni predefinite.
  
Tuttavia, poiché è considerata una soluzione di protezione avanzata senza effetti collaterali, l'impostazione **Impedisci accesso guest locale al registro di sistema** è configurata su **Abilitato** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
**Nota**: questa impostazione non compare nell'oggetto Criteri del computer locale.
  
#### Criteri gestione registro applicazione
  
Questa impostazione di criterio determina il metodo di permanenza dei record nel registro applicazioni. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. Se gli eventi sono sovrascritti come necessario, il registro memorizza sempre quelli più recenti, sebbene questa configurazione potrebbe determinare una perdita di dati cronologici.
  
Il **Criteri gestione registro applicazione** è configurato su **Se necessario** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
#### Criteri gestione registro protezione
  
Questa impostazione di criterio determina il metodo di gestione del registro protezione. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. Se gli eventi sono sovrascritti come necessario, il registro memorizza sempre quelli più recenti, sebbene questa configurazione potrebbe determinare una perdita di dati cronologici.
  
Il **Criteri gestione registro protezione** è configurato su **Se necessario** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
#### Criteri gestione registro eventi di sistema
  
Questa impostazione di criterio determina il metodo di permanenza dei record nel registro di sistema. Per poter avere a disposizione informazioni cronologiche attendibili, sia per motivi di analisi che per la risoluzione dei problemi, è fondamentale archiviare il registro con regolarità. Se gli eventi sono sovrascritti come necessario, il registro memorizza sempre quelli più recenti, sebbene questa configurazione potrebbe determinare una perdita di dati cronologici.
  
L'impostazione **Criteri gestione registro eventi di sistema** è configurata su **Se necessario** nel criterio base di tutti i tre ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Voci di registro aggiuntive
  
Per i file dei modelli di protezione di base sono state create voci per i *valori del Registro* di sistema che non sono definite nel file del modello amministrativo (.adm) dei tre ambienti di protezione definiti in questa guida. I file .adm definiscono le restrizioni e i criteri per la protezione del desktop e della shell di Windows Server 2003.
  
Queste voci di registro sono incorporate nei modelli di protezione, nella sezione Opzioni di protezione, e consentono l’esecuzione automatica delle procedure di modifica. Se il criterio viene rimosso, queste voci di registro non vengono rimosse automaticamente insieme ad esso e devono essere modificate manualmente, utilizzando uno strumento di modifica del Registro di sistema, come Regedt32.exe. In tutti e tre gli ambienti vengono applicate le stesse voci di registro.
  
Questa guida contiene voci di registro aggiuntive che sono aggiunte all'Editor di configurazione della protezione (SCE, Security Configuration Editor). Per aggiungere queste voci di registro, è necessario modificare il file sceregvl.inf, nella cartella **%windir%\\inf** e registrare nuovamente il file scecli.dll. Le voci di protezione originali e le impostazioni aggiuntive compaiono in **Criteri locali\\Protezione** negli snap-in e negli strumenti menzionati in precedenza nel presente capitolo. È necessario aggiornare il file Sceregvl.inf e ripetere la registrazione del file** **Scecli.dll in tutti i computer in cui si modificano i modelli di protezione e i criteri di gruppo forniti con questa Guida. Per ulteriori informazioni sulle impostazioni predefinite, consultare la guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo <http://technet.microsoft.com/it-it/library/dd162275>(in lingua inglese).
  
Questa sezione contiene solo un riepilogo delle impostazioni aggiuntive del Registro di sistema. Queste impostazioni sono trattate in modo esauriente nella guida correlata. Per informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata nella presente sezione, fare riferimento a, *Pericoli e contromisure: Impostazioni di protezione in Windows* *Server* *2003 e Windows* *XP* (in inglese).
  
#### Considerazioni sulla protezione per gli attacchi alle reti
  
Gli attacchi di tipo Denial of service (DoS) sono attacchi alla rete finalizzati a rendere un computer o un servizio non disponibile per gli utenti della rete. Non è semplice difendersi da questi attacchi.
  
Per prevenirli, è necessario mantenere aggiornato il computer con le correzioni per la protezione più recenti e proteggere con particolare attenzione lo stack di protocolli TCP/IP nei computer Windows Server 2003 con SP1 esposti a possibili attacchi. La configurazione dello stack TCP/IP è ottimizzata per gestire il traffico standard delle reti Intranet. Se si connette un computer direttamente a Internet, è consigliabile rafforzare la protezione dello stack TCP/IP rispetto agli attacchi DoS.
  
È possibile aggiungere i valori del registro di sistema nella seguente tabella nel file modello della sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\**
  
.
  
**Tabella 4.28 Suggerimenti per le voci del Registro TCP/IP**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Voce di registro</th>
<th style="border:1px solid black;" >Formato</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">EnableICMPRedirect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SynAttackProtect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">EnableDeadGWDetect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">KeepAliveTime</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">300.000</td>
<td style="border:1px solid black;">300.000</td>
<td style="border:1px solid black;">300.000</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DisableIPSourceRouting</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TcpMaxConnectResponseRetransmissions</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TcpMaxDataRetransmissions</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">3</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PerformRouterDiscovery</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
</tbody>
</table>
  
#### Altre voci di registro
  
La tabella seguente elenca altre voci di registro consigliate, non specifiche per TCP/IP. Nelle sottosezioni che seguono la tabella sono disponibili ulteriori informazioni su ciascuna voce.
  
**Tabella 4.29 Altri suggerimenti per le voci di registro**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Voce di registro</th>
<th style="border:1px solid black;" >Formato</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoNameReleaseOnDemand) Consente al computer di ignorare le richieste di rilascio del nome NetBIOS eccetto per i server WINS</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (NtfsDisable8dot3NameCreation) consente al computer di bloccare la creazione di nomi file in formato 8.3 (consigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoDriveTypeAutoRun) disabilita l'esecuzione automatica per tutte le unità (consigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0xFF</td>
<td style="border:1px solid black;">0xFF</td>
<td style="border:1px solid black;">0xFF</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (ScreenSaverGracePeriod) tempo in secondi prima della scadenza del periodo di prova dello screen saver (consigliato: 0)</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (WarningLevel) limite in percentuale del registro eventi di protezione raggiunto il quale viene creato un messaggio di avviso</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">90</td>
<td style="border:1px solid black;">90</td>
<td style="border:1px solid black;">90</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (SafeDllSearchMode) modalità di ricerca Safe DLL (consigliata)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (AutoReboot) Consente a Windows di effettuare il riavvio dopo un blocco di sistema (non consigliato per gli ambienti ad alta sicurezza)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (AutoAdminLogon) abilita l'accesso automatico (sconsigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (AutoShareWks) Attiva le condivisioni amministrative (non consigliato per ambienti ad alta sicurezza)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (DisableSavePassword) Impedisce il salvataggio della password dial-up (consigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoDefaultExempt) abilita NoDefaultExempt per i filtri IPSec (consigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">3</td>
</tr>
</tbody>
</table>
  
##### Configurazione del rilascio dei nomi NetBIOS: consente al computer di ignorare le richieste di rilascio del nome NetBIOS eccetto per i server WINS
  
Questa voce è presente come **MSS: (NoNameReleaseOnDemand) Consente al computer di ignorare le richieste di rilascio del nome NetBIOS eccetto per i server WINS** nell'interfaccia utente di SCE.
  
TCP/IP è un protocollo di rete che, fra l’altro, consente di risolvere facilmente i nomi NetBIOS registrati in sistemi basati su Windows negli indirizzi IP configurati in tali sistemi. Questo valore determina se il computer deve rilasciare il suo nome NetBIOS quando riceve una richiesta di rilascio di nome.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Netbt\\Parameters\\**
  
sottochiave.
  
##### Disabilitazione della creazione automatica di nomi file in formato 8.3: consente al computer di bloccare la creazione di nomi file in formato 8.3
  
Questa voce è presente come **MSS: (NtfsDisable8dot3NameCreation) consente al computer di bloccare la creazione di nomi file in formato 8.3 (consigliato)** nell'interfaccia utente di SCE.
  
Windows Server 2003 con SP1 supporta i nomi di file 8.3 per garantire la compatibilità con le applicazioni a 16 bit. Il formato di denominazione 8.3 consente di assegnare a un file un nome lungo al massimo otto caratteri.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Control\\FileSystem\\**
  
sottochiave.
  
##### Disattivazione esecuzione automatica: disattivazione dell'esecuzione automatica di tutte le unità
  
Questa voce è presente come **MSS: (NoDriveTypeAutoRun) disabilita l'esecuzione automatica per tutte le unità (consigliato)** nello SCE.
  
La funzionalità di esecuzione automatica inizia a leggere in un’unità del computer non appena si inserisce un supporto in essa. Di conseguenza, i file di installazione (per i programmi) o il suono (per i contenuti audio) sono avviati immediatamente.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\**
  
sottochiave.
  
##### Protezione da password immediata dello screen saver: tempo in secondi prima della scadenza del periodo di prova dello screen saver (consigliato: 0)
  
Questa voce è presente come **MSS: (ScreenSaverGracePeriod) tempo in secondi prima della scadenza del periodo di prova dello screen saver (consigliato: 0)** nell'interfaccia utente di SCE.
  
Se è impostato il blocco dello screen saver, tra l’avvio dello screen saver e il blocco effettivo della console intercorre un periodo di tempo.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\**  
**Winlogon\\**
  
sottochiave.
  
##### Messaggio di avviso per il raggiungimento del limite massimo nel registro di protezione: limite in percentuale del registro eventi di protezione raggiunto il quale viene creato un messaggio di avviso
  
Questa voce è presente come **MSS: (WarningLevel) limite in percentuale del registro eventi di protezione raggiunto il quale viene creato un messaggio di avviso** nell'interfaccia utente di SCE.
  
Questa opzione è disponibile a partire da Windows 2000 SP3. Genera un controllo della protezione nel registro eventi di protezione quando il registro di protezione raggiunge la soglia definita dall’utente. Se, ad esempio, questo valore è impostato su 90, quando viene raggiunto il 90 percento della capacità del registro viene registrata una voce per l’ID evento 523 con il seguente testo: “Il registro di protezione è ora pieno al 90 percento".
  
**Nota:** se per il registro è selezionata l’opzione **Sovrascrivi eventi se necessario** o **Sovrascrivi eventi anteriori a x giorni**, questo evento non viene generato.
  
È possibile aggiungere questo valore di registro al file di modello di protezione nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\ SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Security\\**
  
.
  
##### Abilitazione dell'ordine di ricerca Safe DLL: abilita l'ordine di ricerca Safe DLL: (consigliato)
  
Questa voce è presente come **MSS: (SafeDllSearchMode) Attiva il modo di ricerca di DLL Sicuro (consigliato**) nello SCE.
  
È possibile configurare la ricerca delle DLL richieste dai processi in esecuzione in due modi:
  
-   Prima eseguire la ricerca nelle cartelle specificate nel percorso di sistema, quindi eseguire la ricerca nella cartella di lavoro corrente.
  
-   Prima eseguire la ricerca nella cartella di lavoro corrente, quindi eseguire la ricerca nelle cartelle specificate nel percorso di sistema.
  
Il valore del Registro di sistema è impostato su 1. Se l’impostazione è 1, il sistema esegue la ricerca prima nelle cartelle specificate nel percorso di sistema, quindi nella cartella di lavoro corrente. Se l’impostazione è 0, il sistema esegue la ricerca prima nella cartella di lavoro corrente, quindi nelle cartelle specificate nel percorso di sistema.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\ SYSTEM\\CurrentControlSet\\Control\\Session Manager\\**
  
.
  
##### Riavvio automatico: consente il riavvio automatico di Windows dopo un blocco del sistema.
  
Questa voce è presente come **MSS: (AutoReboot) consente il riavvio automatico di Windows dopo un blocco del sistema** (**non consigliato per gli ambienti ad alta sicurezza**) nello SCE.
  
Quando questa voce è abilitata, il server può eseguire il riavvio automatico dopo un errore critico. È attivato per impostazione predefinita (sconsigliato su server ad alta sicurezza).
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Control\\CrashControl\\**
  
sottochiave.
  
##### Accesso automatico: abilita l'accesso automatico
  
Questa voce è presente come **MSS: (AutoAdminLogon) abilita l'accesso automatico**  (**sconsigliato)** nello SCE. Per impostazione predefinita, questa voce non è attivata e non dovrebbe mai essere utilizzata su un server in nessuna circostanza.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Come attivare l'accesso automatico in Windows](http://support.microsoft.com/kb/315231/it)", disponibile online all'indirizzo [http://support.microsoft.com/kb/315231/it.](http://support.microsoft.com/kb/315231/it)
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\**  
**Winlogon\\**
  
sottochiave.    
  
##### Condivisioni amministrative: attiva le condivisioni amministrative
  
Questa voce è presente come **MSS: (AutoShareWks) Attiva le condivisioni amministrative** (**non consigliato per ambienti ad alta sicurezza**) nello SCE. Per impostazione predefinita, quando la rete Windows è attiva su un server, Windows creerà condivisioni amministrative nascoste. Questa impostazione è sconsigliabile su server ad alta sicurezza.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\RasMan\\Parameters\\**
  
sottochiave.
  
##### Disabilita salvataggio password: impedisce il salvataggio della password dial-up
  
Questa voce appare come **MSS: (DisableSavePassword) Impedisce il salvataggio della password dial-up** (**consigliato**) nello SCE. Per impostazione predefinita, Windows consente di salvare le password per connessioni dial-up e VPN, opzione sconsigliata su un server.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\LanmanServer\\**  
**Parameters\\**
  
.
  
##### Abilita IPSec per proteggere il Traffico RSVP Kerberos: abilita NoDefaultExempt per i filtri IPSec
  
Questa voce è presente come **NoDefaultExempt) abilita NoDefaultExempt per i filtri IPSec** (**consigliato**) nello SCE. Le esenzioni predefinite ai filtri dei criteri IPsec sono descritte nella guida in linea di Microsoft Windows Server 2003. Questi filtri consentono il funzionamento di IKE (Internet Key Exchange) e del protocollo di autenticazione Kerberos. I filtri consentono inoltre alla qualità del servizio (QoS) di rete di essere segnalata (RSVP) sia quando il traffico di dati è protetto da IPsec sia quando il traffico potrebbe non essere protetto da IPsec, come ad esempio il traffico multicast e broadcast.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\IPSEC\\**
  
sottochiave.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Gruppi con restrizioni
  
La funzione Gruppi con restrizioni consente di gestire l'appartenenza a gruppi attraverso l'applicazione dei criteri e di prevenire l'uso deliberato o involontario dei gruppi per ottenere diritti utente non autorizzati. Esaminare prima di tutto le esigenze dell'organizzazione per determinare quali gruppi devono essere limitati.
  
I gruppi **Backup Operators e Power Users** sono limitati in tutti i tre ambienti definiti in questa guida. Anche se i membri dei gruppi **Backup Operators e Power Users** godono di un accesso più limitato rispetto ai membri del gruppo **Administrators**, dispongono tuttavia di funzionalità potenti.
  
**Nota:** se l'organizzazione utilizza uno qualsiasi di questi gruppi, controllare attentamente la loro appartenenza e non implementare le istruzioni relative all'impostazione dei gruppi con restrizioni. Se l'organizzazione aggiunge utenti al gruppo Power Users, è possibile implementare le autorizzazioni di file system opzionali descritte nella sezione "Protezione del File System" più avanti nel presente capitolo.
  
È possibile configurare l'impostazione Gruppi con restrizioni in Windows Server 2003 con SP1 alla posizione seguente nell'ambito dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Gruppi con restrizioni\\**
  
Gli amministratori possono configurare i gruppi con restrizioni aggiungendo il gruppo desiderato direttamente all'MSBP. Quando viene posta la restrizione su un gruppo, è possibile definirne i membri e altri gruppi a cui esso appartiene. Se non si definiscono questi membri del gruppo, esso mantiene tutte le restrizioni.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione del File System
  
Il file system NTFS è stato migliorato in ogni nuova versione di Microsoft Windows, e le autorizzazioni predefinite per NTFS sono adeguate per la maggior parte delle organizzazioni. Le impostazioni descritte in questa sezione sono fornite per uso facoltativo alle organizzazioni che non utilizzano i gruppi con restrizioni ma desiderano tuttavia avere un livello aggiuntivo di protezione avanzata sui propri server.
  
È possibile configurare le impostazioni di protezione di Microsoft Office XP all'interno dell'Editor oggetti Criteri di gruppo nella posizione seguente:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\File system**
  
**Nota**: qualsiasi modifica alle impostazioni di protezione del file system dovrebbe essere controllata attentamente in un ambiente di prova prima della distribuzione in una grande organizzazione. Si sono registrati casi in cui le autorizzazioni sui file sono state modificate a tal punto che si è dovuto provvedere alla completa ricostruzione dei computer interessati.
  
Le autorizzazioni predefinite sui file in Windows Server 2003 con SP1 sono sufficienti per la maggior parte delle situazioni. Tuttavia, se non si sta per bloccare l'appartenenza al gruppo **Power Users** con la funzionalità Gruppi con restrizioni o si sta per attivare l'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi**, è possibile applicare le autorizzazioni opzionali descritte nel paragrafo riportato di seguito. Queste autorizzazioni opzionali sono molto specifiche e applicano ulteriori restrizioni ad alcuni degli strumenti eseguibili che un utente malintenzionato con un livello di privilegi elevato può utilizzare per compromettere ulteriormente il sistema o la rete.
  
Queste modifiche alle autorizzazioni non interessano le cartelle multiple o la directory principale del volume di sistema. Può essere molto rischioso utilizzare questo metodo per modificare le autorizzazioni, poiché spesso può provocare instabilità del sistema. Tutti i file sono collocati nella cartella **%SystemRoot%\\System32\\**, e riportano tutti le seguenti autorizzazioni: **Administrators: controllo completo, Sistema: controllo completo**.
  
-   regedit.exe
  
-   arp.exe
  
-   a.exe
  
-   attrib.exe
  
-   cacls.exe
  
-   debug.exe
  
-   edlin.exe
  
-   eventcreate.exe
  
-   eventtriggers exe
  
-   ftp.exe
  
-   nbtstat.exe
  
-   net.exe
  
-   net1.exe
  
-   netsh.exe
  
-   netstat.exe
  
-   nslookup.exe
  
-   ntbackup.exe
  
-   rcp.exe
  
-   reg.exe
  
-   regedt32.exe
  
-   regini.exe
  
-   regsvr32.exe
  
-   rexec.exe
  
-   strada.exe
  
-   rsh.exe
  
-   sc.exe
  
-   secedit.exe
  
-   subst.exe.exe
  
-   systeminfo.exe
  
-   telnet.exe
  
-   tftp.exe
  
-   tlntsvr.exe
  
Per maggior comodità, queste autorizzazioni opzionali sono già configurate nel modello di protezione chiamato **Optional-File-Permissions.inf**, incluso nella versione scaricabile di questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
La maggior parte delle misure adottate per potenziare la protezione dei server di base in questa guida sono state applicate tramite Criteri di gruppo. Vi sono, tuttavia, altre impostazioni che non è facile o possibile applicare con Criteri di gruppo. Per ulteriori informazioni sulle impostazioni predefinite e una spiegazione dettagliata per ogni impostazione trattata nella presente sezione, fare riferimento alla guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo <http://technet.microsoft.com/it-it/library/dd162275>.
  
#### Procedure manuali per la protezione avanzata
  
In questa sezione verranno descritte in che modo le misure aggiuntive (ad esempio la protezione degli account) sono state implementate manualmente, per ciascuno degli ambienti definiti nella presente guida.
  
##### Aggiunta manuale di gruppi di protezione univoci ad Assegnazioni diritti utente
  
La maggior parte dei gruppi di protezione consigliati per l'assegnazione dei diritti utente sono stati configurati nei modelli di protezione allegati alla presente guida. Vi sono, tuttavia, alcuni diritti che non possono essere inseriti nei modelli di protezione, perché i SID di specifici gruppi di protezione sono univoci nei diversi domini Windows Server 2003. Il problema è che l’identificatore relativo (RID, Relative Identifier), che fa parte del SID, è univoco. Questi diritti sono descritti nella tabella seguente.
  
**Avvertenza**: nella tabella che segue sono contenuti i valori per l'Amministratore incorporato. Con account Administrator predefinito si intende l’account utente predefinito, *non* il gruppo di protezione **Administrators.** Se si aggiunge il gruppo di protezione **Administrators** a uno qualunque dei seguenti diritti di accesso utente negati sarà necessario accedere a livello locale per correggere l'errore.
  
Inoltre, l’account Administrator predefinito potrebbe essere stato modificato a seguito dei suggerimenti presentati in questa guida. Verificare di scegliere l'account amministratore appena rinominato quando si aggiunge l'account a uno qualunque dei diritti di accesso utente negati.
  
**Tabella 4.30 Assegnazioni diritti utente aggiunte manualmente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome dell'impostazione nell'interfaccia utente</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso al computer dalla rete</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nega accesso come processo batch</td>
<td style="border:1px solid black;">Support_388945a0 e Guest</td>
<td style="border:1px solid black;">Support_388945a0 e Guest</td>
<td style="border:1px solid black;">Support_388945a0 e Guest</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso tramite Servizi terminal</td>
<td style="border:1px solid black;">Administrator predefinito, Guests, Support_388945a0, Guest, tutti gli account di servizio non utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Administrator predefinito, Guests, Support_388945a0, Guest, tutti gli account di servizio non utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Administrator predefinito, Guests, Support_388945a0, Guest, tutti gli account di servizio non utilizzati dal sistema operativo</td>
</tr>
</tbody>
</table>
  
**Importante:** gli account di servizio non utilizzati dal sistema operativo sono account di servizio che vengono utilizzati per applicazioni specifiche. Fra questi NON rientrano gli account SISTEMA LOCALE, SERVIZIO LOCALE e SERVIZIO DI RETE, che sono account predefiniti utilizzati dal sistema operativo.
  
Per aggiungere manualmente i gruppi di protezione elencati ai criteri di protezione di base dei server membro (MSBP, Member Server Baseline Policy) nell'ambiente Client di organizzazione, effettuare le seguenti operazioni.
  
**Per aggiungere gruppi di protezione ad Assegnazione diritti utente**
  
1.  In **Utenti e computer di Active Directory** fare clic con il pulsante destro del mouse sull'unità organizzativa del server membro, quindi scegliere Proprietà.
  
2.  Sulla scheda **Criteri di gruppo**, scegliere i **criteri di protezione di base dei server membro (MSBP, Member Server Baseline Policy) nell'ambiente Client di organizzazione** per modificare il GPO collegato.
  
3.  Scegliere **i criteri di protezione di base dei server membro nell'ambiente Client di organizzazione**, e poi fare clic su **Modifica.**
  
4.  Nella finestra **Criteri di gruppo**, fare clic su **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Assegnazioni diritti utenti** per aggiungere dalla tabella precedente i gruppi di protezione univoci per ciascuno diritto.
  
5.  Chiudere i Criteri di gruppo modificati.
  
6.  Chiudere la **finestra delle proprietà delle OU dei server membro**.
  
7.  Per eseguire una replica forzata tra i controller di dominio in modo che in tutti vengano applicati i criteri, procedere come segue:
  
    1.  aprire un prompt dei comandi, digitare **gpupdate /Force** e premere ENTER per forzare il server ad aggiornare il criterio.
  
    2.  Riavviare il server.
  
8.  Controllare nel registro eventi che i criteri di gruppo siano stati scaricati e che il server sia in grado di comunicare con gli altri controller di dominio all'interno del dominio.
  
##### Protezione di account noti
  
In Windows Server 2003 sono disponibili alcuni account utente predefiniti, che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membro e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account predefinito. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
Per proteggere gli account noti su domini e server, completare la procedura seguente:
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico che riuscisse ad accedere a un server membro potrebbe avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Salvare qualsiasi modifica effettuata in un luogo sicuro.
  
    **Nota**: per rinominare l'account Amministratore incorporato è possibile utilizzare Criteri di gruppo. Questa impostazione non è stata implementata nei criteri base in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare le impostazioni di **Account: Rinomina l'impostazione di account amministratore** per rinominare gli account amministratore in tutti e tre gli ambienti che sono definiti in questa guida. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
##### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche la [Guida alla pianificazione della protezione degli account dei servizi](http://technet.microsoft.com/it-it/library/cc170953) all'indirizzo <http://technet.microsoft.com/it-it/library/cc170953> (in inglese).
  
##### NTFS
  
Le partizioni NTFS supportano gli ACL a livello di file e cartelle. Questo supporto non è disponibile nel file system FAT o FAT32. FAT32 è una versione del file system FAT che è stata aggiornata per rendere possibili dimensioni di cluster predefinite molto più piccole e per supportare dischi rigidi di dimensioni fino a due terabyte. FAT32 è disponibile in Windows 95 OSR2, Windows 98, Microsoft Windows ME, Windows 2000, Windows XP Professional e Windows Server 2003.
  
Formattare tutte le partizioni di tutti i server utilizzando NTFS. Utilizzare l**’**utilità convert per convertire le partizioni FAT in NTFS, tenendo presente, tuttavia, che questa utilità imposterà per gli ACL dell’unità convertita il valore Everyone: Controllo completo.
  
Per i sistemi basati su Windows 2003 Server SP1 applicare i seguenti modelli di protezione in locale, per configurare gli ACL predefiniti del file system rispettivamente per server membri e controller di dominio
  
-   **%windir%\\inf\\defltsv.inf**
  
-   **%windir%\\inf\\defltdc.inf**
  
    **Nota**: le impostazioni di protezione dei controller di dominio vengono applicate quando il server viene alzato di livello e diventa controller di dominio.
  
Tutte le partizioni dei server di tutti e tre gli ambienti definiti in questa guida sono formattate con NTFS, in modo da consentire la gestione della protezione di file e directory mediante gli ACL.
  
##### Impostazioni di Servizi terminal
  
L'impostazione **Imposta livello di crittografia connessione client** determina il livello di crittografia applicato alle connessioni client dei Servizi terminal nell'ambiente in uso. L’impostazione **Alto,** che utilizza la crittografia a 128 bit, evita che un pirata informatico possa seguire di nascosto le sessioni di Servizi terminal utilizzando uno strumento di analisi dei pacchetti. Alcune versioni precedenti dei client di Servizi terminal non supportano questo livello di crittografia elevato. Se nella rete sono presenti client di questo tipo, impostare il livello di crittografia della connessione in modo da inviare e ricevere dati al livello di crittografia più elevato tra quelli supportati dal client.
  
È possibile configurare questa impostazione nei Criteri di gruppo alla posizione seguente:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\**  
**Servizi terminal \\Crittografia e protezione**
  
**Tabella 4.31 Suggerimenti per l'impostazione del livello di crittografia connessione client**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome dell'impostazione nell'interfaccia utente</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Imposta livello di crittografia connessione client</td>
<td style="border:1px solid black;">Alto</td>
<td style="border:1px solid black;">Alto</td>
<td style="border:1px solid black;">Alto</td>
</tr>
</tbody>
</table>
  
I tre livelli di crittografia disponibili sono descritti nella tabella seguente:
  
**Tabella 4.32 Livelli di crittografia di Servizi terminal**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Livello di crittografia</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Alto</td>
<td style="border:1px solid black;">Codifica i dati inviati dal client al server e dal server al client con crittografia avanzata a 128 bit. Utilizzare questo livello quando il server terminal è in esecuzione in un ambiente dove si trovano solo client a 128 bit (ad esempio client di Connessione desktop remoto). I client che non supportano questo livello di crittografia non possono stabilire la connessione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Compatibile con client</td>
<td style="border:1px solid black;">Codifica i dati inviati fra client e server basandosi sulla forza massima della chiave supportata dal client. Utilizzare questo livello se il server terminal è in esecuzione in un ambiente con client misti o legacy.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Basso</td>
<td style="border:1px solid black;">Codifica i dati inviati fra client e server con crittografia a 56 bit.
<strong>Importante</strong>: i dati inviati dal server al client non sono crittografati.</td>
</tr>
</tbody>
</table>
 

#### Segnalazione errori

**Tabella 4.33 Impostazioni di segnalazione errori consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disabilitare la segnalazione errori di Windows</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
Questo servizio aiuta Microsoft a rintracciare e a correggere eventuali errori. È possibile configurare questo servizio in modo che vengano segnalati gli errori del sistema operativo, gli errori dei componenti di Windows o gli errori dei programmi. È disponibile soltanto in Windows XP Professional e Windows Server 2003.
  
Il **Servizio di segnalazione errori** può segnalare tali errori a Microsoft tramite Internet o una condivisione di file interni. Sebbene le relazioni di errore possono potenzialmente contenere dei dati sensibili o anche riservati, l'informativa sulla privacy di Microsoft garantisce che, nell'ambito della segnalazione di tali errori, Microsoft non utilizzerà tali dati in modo inappropriato. I dati vengono però trasmessi non crittografati su HTTP e possono essere intercettati su Internet e visualizzati da terzi.
  
L'impostazione di disattivazione della segnalazione degli errori di Windows regola la trasmissione di dati da parte del servizio Segnalazione errori.
  
È possibile configurare questa impostazione del criterio in Windows Server 2003 alla posizione seguente nell'ambito, dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Gestione comunicazioni Internet\\impostazioni di comunicazione Internet**
  
Abilitare **l'impostazione di disattivazione della segnalazione degli errori di Windows** nel DCBP per tutti e tre gli ambienti definiti in questa guida.
  
##### Attivare immagine della memoria manuale
  
Windows Server 2003 SP1 dispone di una funzionalità che consente di bloccare il computer e generare un file Memory.dmp. È necessario attivare esplicitamente questo servizio, e potrebbe non essere adatto a tutti i server dell'organizzazione. Se si ritiene utile catturare un'immagine della memoria su alcuni server, seguire le istruzioni riportate nell'articolo [Funzione di Windows che consente la generazione di un file Memory.dmp con la tastiera](http://support.microsoft.com/kb/244139/it) all'indirizzo [http://support.microsoft.com/kb/244139/it.](http://support.microsoft.com/kb/244139/it)
  
**Importante**: quando si copia la memoria su disco come descritto nell'articolo citato, il file Memory.dmp potrebbe contenere dati sensibili. In genere, tutti i server sono protetti dall'accesso fisico non autorizzato. Se si genera un'immagine della memoria su un server ad alto rischio di infrazione fisica della protezione, eliminare il file immagine una volta terminata la risoluzione dei problemi.
  
#### Creazione del criterio di base utilizzando SCW
  
Per distribuire le impostazioni di sicurezza adeguate, è necessario creare innanzitutto un'MSBP (Member Server Baseline Policy). A questo fine, utilizzare la Configurazione guidata impostazioni di sicurezza (SCW) ed i modelli di sicurezza contenuti nella versione scaricabile della guida.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e "Criterio di controllo". Queste impostazioni sono fornite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, utilizzare un hardware simile a quello usato durante la distribuzione. L'installazione nuova è chiamata *computer di riferimento.*
  
È possibile che durante le fasi di creazione del MSBP venga eliminato il ruolo di File server dall'elenco di ruoli rilevati. Questo ruolo è comunemente configurato sui server che non lo richiedono e potrebbe essere considerato un rischio di protezione. Per abilitare il ruolo di File server per i server che lo richiedono, è possibile applicare successivamente un secondo criterio nel corso di questo processo.
  
**Per creare i criteri di base dei server membro (MSBP, Member Server Baseline Policy).**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un nuovo computer di riferimento.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio.
  
4.  Installare e configurare soltanto le applicazioni obbligatorie che dovrebbero essere presenti su ogni server dell'ambiente in uso. Gli esempi contengono agenti di software e di gestione, agenti di backup su nastro e le utilità antivirus o antispyware.
  
5.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
6.  Rimuovere il ruolo di File server dall'elenco di ruoli rilevati.
  
7.  Accertarsi che i ruoli rilevati siano adatti all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
10. Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
11. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di utilizzarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
12. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
13. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
14. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
15. Allegare il modello di protezione idoneo (ad esempio EC-Member Server Baseline.inf).
  
16. Salvare il criterio con un nome idoneo (ad esempio, Member Server Baseline.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o usare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo offre la possibilità di rieseguire facilmente i criteri utilizzati dallo SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), verificare che i client possano richiedere e ottenere certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la [Guida di sviluppo per la configurazione guidata delle impostazioni di sicurezza](http://technet.microsoft.com/en-us/library/cc776871.aspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx](http://technet.microsoft.com/en-us/library/cc776871.aspx) e la [Documentazione di configurazione guidata impostazioni di sicurezza](http://go.microsoft.com/fwlink/?linkid=43450)all'indirizzo <http://go.microsoft.com/fwlink/?linkid=43450> (in inglese).
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:&lt;PathToPolicy.xml&gt; /g:&lt;GPODisplayName&gt;  
```
  
    e premere INVIO. Ad esempio:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:"C:\\Windows\\Security\\msscw\\Policies\\Member Server Baseline.xml" /g:"Member Server Baseline Policy"  
```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo ha descritto le procedure di rafforzamento della protezione da applicare inizialmente a tutti i server con Windows Server 2003 con SP1 in tutti e tre gli ambienti definiti in questa guida. Per l’applicazione della maggior parte di queste procedure è stato creato un modello di protezione specifico per ogni ambiente di protezione, quindi questo modello è stato importato in un oggetto Criteri di gruppo collegato all’unità organizzativa padre del server membro.
  
Alcune di queste procedure, tuttavia, non possono essere applicate mediante i criteri di gruppo. Sono state fornite indicazioni su come configurare queste impostazioni manualmente. Sono state elaborate ulteriori procedure per ruoli di server specifici, per consentir loro di operare nel modo più protetto possibile.
  
Le procedure specifiche per i ruoli di server includono sia procedure aggiuntive per la protezione avanzata, sia procedure per ridurre le impostazioni di protezione nei criteri di base dei server. Queste procedure verranno trattate dettagliatamente nei successivi capitoli di questa guida.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server che eseguono Windows Server 2003 con SP1.
  
-   Per ulteriori informazioni sulle impostazioni di protezione di Windows Server 2003, vedere la pagina [Descrizioni delle impostazioni di protezione](http://technet.microsoft.com/en-us/library/cc785357.aspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/ServerHelp/dd980ca3-f686-4ffc-a617-50c6240f5582.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/dd980ca3-f686-4ffc-a617-50c6240f5582.mspx) (in inglese).
  
-   Per ulteriori informazioni sulla protezione di Windows Server 2003, vedere [Windows Server 2003 Security Center](http://www.microsoft.com/technet/security/prodtech/windowsserver2003.mspx) all'indirizzo <http://www.microsoft.com/technet/security/prodtech/windowsserver2003.mspx> (in inglese).
  
-   Per ulteriori informazioni sui criteri di controllo di Windows Server 2003, vedere la pagina [Descrizioni dei criteri di controllo](http://technet.microsoft.com/en-us/library/cc785357.aspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/ServerHelp/6847e72b-9c47-42ab-b3e3-691addac9f33.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/6847e72b-9c47-42ab-b3e3-691addac9f33.mspx) (in inglese).
  
-   Per ulteriori informazioni su Microsoft Operations Manager (MOM), vedere la pagina [Microsoft Operations Manager](http://technet.microsoft.com/opsmgr/bb498231.aspx) all'indirizzo [http: //www.microsoft.com/mom/](http://www.microsoft.com/systemcenter/operationsmanager/en/us/default.aspx) (in inglese).
  
-   Per ulteriori informazioni sui diritti utente di Windows Server 2003, vedere la pagina [Diritti utente](http://technet.microsoft.com/en-us/library/cc778337.aspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/ServerHelp/589980fb-1a83-490e-a745-357750ced3d9.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/589980fb-1a83-490e-a745-357750ced3d9.mspx) (in inglese).
  
-   Per ulteriori informazioni sulle impostazioni di protezione predefinite per Windows Server 2003, vedere la pagina [Differenze nelle impostazioni di protezione predefinite](http://technet.microsoft.com/en-us/library/cc784886.aspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/ServerHelp/1494bf2c-b596-4785-93bb-bc86f8e548d5.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/1494bf2c-b596-4785-93bb-bc86f8e548d5.mspx) (in inglese).
  
-   Per ulteriori informazioni su come proteggere lo stack TCP/IP di Windows Server 2003, consultare l'articolo della Microsoft Knowledge Base "[Rendere più forte lo stack TCP/IP rispetto ad attacchi di tipo "denial of service" in Windows Server 2003](http://support.microsoft.com/kb/324270/it)" all'indirizzo <http://support.microsoft.com/kb/324270/it>.
  
-   Per ulteriori informazioni su come aumentare la protezione delle impostazioni per le applicazioni Windows Sockets, vedere l'articolo della Knowledge Base Microsoft "[Server Internet non disponibile a causa di attacchi SYN](http://support.microsoft.com/kb/142641/it)" all'indirizzo <http://support.microsoft.com/kb/142641/it>.
  
-   Per ulteriori informazioni sulla posizione dei file .adm, consultare l'articolo della Microsoft Knowledge Base "[Posizione di file ADM (modello amministrativo) in Windows](http://support.microsoft.com/kb/228460/it)" all'indirizzo <http://support.microsoft.com/kb/228460/it>.
  
-   Per ulteriori informazioni su come personalizzare l'interfaccia utente dell'Editor di configurazione della protezione, consultare l'articolo della Microsoft Knowledge Base "[Come aggiungere le impostazioni di Registro di sistema personalizzato a Editor di configurazione della protezione](http://support.microsoft.com/kb/214752/it)" all'indirizzo <http://support.microsoft.com/kb/214752/it>.
  
-   Per ulteriori informazioni sulla creazione di modelli amministrativi personalizzati in Windows, consultare l'articolo della Microsoft Knowledge Base "[Creare modelli amministrativi personalizzati in Windows 2000"](http://support.microsoft.com/kb/323639/it) all'indirizzo <http://support.microsoft.com/kb/323639/it>. Consultare inoltre il white paper "[Implementazione dei criteri di gruppo basati sul registro](http://technet.microsoft.com/en-us/library/bb742499.aspx)" all'indirizzo <http://technet.microsoft.com/en-us/library/bb742499.aspx> (in inglese).
  
-   Per ulteriori informazioni su come assicurare che le impostazioni di livello di autenticazione di LAN Manager più sicure collaborino su reti miste Windows 2000 e Windows NT 4.0, consultare l'articolo della Microsoft Knowledge Base "[I problemi di autenticazione in Windows 2000 con NTLM 2 livellano sopra 2 in un dominio di Windows NT 4.0](http://support.microsoft.com/kb/305379/it)" all'indirizzo <http://support.microsoft.com/kb/305379/it>.
  
-   Per ulteriori informazioni sull'autenticazione NTLMv2, vedere l'articolo della Microsoft Knowledge Base "[Attivazione dell'autenticazione NTLM 2](http://support.microsoft.com/kb/239869/it)" all'indirizzo <http://support.microsoft.com/kb/239869/it>.
  
-   Per ulteriori informazioni sulle impostazioni predefinite per i servizi di Windows Server 2003, vedere la pagina [Impostazioni predefinite dei servizi](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/2b1dc6cf-2e34-4681-9aa6-8d0ffba2d3e3.mspx) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    library/ServerHelp/2b1dc6cf-2e34-4681-9aa6-8d0ffba2d3e3.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/serverhelp/2b1dc6cf-2e34-4681-9aa6-8d0ffba2d3e3.mspx) (in inglese).
  
-   Per ulteriori informazioni sulla distribuzione delle smart card, vedere ["Una scelta intelligente! Rendete la vostra rete più intelligente con le Smart Card "](http://www.microsoft.com/technet/technetmag/issues/2005/01/smartcards/)all'indirizzo [http://www.microsoft.com/technet/technetmag/issues/2005/01/SmartCards/default.aspx](http://www.microsoft.com/technet/technetmag/issues/2005/01/smartcards/) (in inglese).
  
-   Per ulteriori informazioni sul valore di registro "Restrict Anonymous" e Windows 2000, vedere l'articolo della Knowledge Base Microsoft "[Il valore di registro "RestrictAnonymous" può compromettere la sicurezza di un dominio Windows 2000](http://support.microsoft.com/kb/296405/it)" all'indirizzo [http://support.microsoft.com/kb/296405/it,](http://support.microsoft.com/kb/296405/it)
  
-   Per ulteriori informazioni sulla segnalazione di errori, vedere la pagina [Corporate error reporting (CER)](http://technet.microsoft.com/en-us/library/cc775885.aspx) all'indirizzo <http://technet.microsoft.com/en-us/library/cc775885.aspx> (in inglese).
  
-   Per informazioni sulle porte di rete utilizzate dalle applicazioni Microsoft, vedere l'articolo della Knowledge Base Microsoft "[Panoramica del servizio e requisiti delle porte di rete per il sistema Server Windows](http://support.microsoft.com/kb/832017/it/it)" all'indirizzo [http://support.microsoft.com/kb/832017/it/it.](http://support.microsoft.com/kb/832017/it/it)
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
