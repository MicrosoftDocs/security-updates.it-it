---
TOCTitle: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 3'
Title: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 3'
ms:assetid: '5d917262-e02e-4c89-b0fb-f10a7481ef71'
ms:contentKeyID: 20200781
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536181(v=TechNet.10)'
---

Guida alla pianificazione della protezione degli account amministrativi
=======================================================================

### Capitolo 3 - Direttive per rendere più sicuri gli account amministrativi

Aggiornato: 25/5/2005

Questo capitolo descrive, sotto forma di procedure ottimali, alcune direttive generali per rendere più sicuri gli account amministrativi. Queste direttive seguono i principi presentati nel capitolo 2, "Principi di base per rendere più sicuri gli account amministrativi".

### Cenni generali sulle direttive per rendere più sicuri gli account amministrativi

In ogni nuova installazione del servizio directory Active Directory® viene creato un account Administrator per ciascun dominio. Questo account non può essere eliminato né escluso. In Microsoft® Windows Server™ è possibile disattivare l'account Administrator, ma esso verrà riattivato automaticamente quando il computer viene avviato in modalità provvisoria.

Un utente malintenzionato che cerca di insinuarsi in un computer, di solito inizia col cercare un account valido e quindi prova a innalzare i privilegi di quell'account. Questi potrebbe anche utilizzare tecniche di deduzione delle password per ottenere la password dell'account Administrator. Questo account viene scelto poiché è potente e non può essere bloccato. Il malintenzionato potrebbe anche cercare di indurre l'amministratore ad eseguire del codice maligno che conceda l'accesso all'aggressore.

#### Separare il ruolo di amministratore del dominio da quello di amministratore dell'organizzazione.

Poiché il ruolo di amministratore dell'organizzazione ha i maggiori privilegi in un ambiente di insieme di strutture, è necessario eseguire una delle due azioni che garantiscono un buon controllo del suo utilizzo. È possibile creare e selezionare un singolo account ben protetto in modo da renderlo membro di Enterprise Admins o scegliere di non configurare un account con quelle credenziali e creare invece tale account solo quando è necessario per eseguire un'attività autorizzata che richieda quei privilegi. Quando è stata completata l'operazione eseguita con quell'account, l'account temporaneo Enterprise Admins dovrebbe essere immediatamente eliminato.

#### Separare gli account utente dagli account amministrativi.

Per ogni utente che svolge il ruolo di amministratore, si dovrebbero creare due account: un account utente regolare per le normali operazioni quotidiane come l'accesso alla posta elettronica e ad altri programmi e un account amministrativo per le sole attività amministrative. Questi account amministrativi non dovrebbero essere abilitati alla posta elettronica o utilizzati per eseguire programmi standard o esplorare Internet. Ogni account deve possedere una password univoca. Queste semplici precauzioni riducono significativamente l'esposizione degli account al mondo esterno e riducono il periodo di tempo in cui gli account amministrativi accedono a un computer o a un dominio.

#### Utilizzare il Servizio di accesso secondario.

In Microsoft Windows® 2000, Windows XP Professional e Windows Server 2003 è possibile eseguire programmi da un account utente diverso da quello dell'utente attualmente connesso. In Windows 2000, questa possibilità viene fornita dal servizio **Esegui come**, mentre in Windows XP e Windows Server 2003 la funzionalità è nota come Servizio di accesso secondario. I servizi **Esegui come** e di accesso secondario sono lo stesso servizio, anche se hanno nomi diversi.  

Il Servizio di accesso secondario permette agli amministratori di accedere al computer con un account non amministrativo e, senza disconnettersi, eseguire le operazioni amministrative mediante programmi amministrativi attendibili in contesti amministrativi.

Un servizio di accesso secondario risolve i pericoli di protezione rappresentati dall'esecuzione di programmi influenzabili da codice dannoso da parte degli amministratori; ad esempio, questo potrebbe accadere a un utente che accede a un sito Web non attendibile mentre dispone di privilegi amministrativi.

L'accesso secondario è essenzialmente utile agli amministratori di sistema; tuttavia, il servizio può essere utilizzato anche da qualsiasi utente che dispone di più account e deve poter utilizzare i programmi in contesti di account diversi senza disconnettersi.

Il Servizio di accesso secondario è impostato in modo da avviarsi automaticamente, utilizza lo strumento **Esegui come** per l'interfaccia utente e **runas.exe** come interfaccia dalla riga di comando. Con **Esegui come** è possibile eseguire i programmi (\*.exe), le console Microsoft Management Console (MMC) salvate (\*.msc), i collegamenti ai programmi e gli elementi del Pannello di controllo. Questi programmi possono essere eseguiti come amministratore anche se si accede al computer con un account utente standard che non ha alcun privilegio amministrativo, purché si forniscano le credenziali amministrative di un account utente e la relativa password quando vengono richieste.

**Esegui come** permette di gestire un server di un altro dominio o insieme di strutture, purché si disponga delle credenziali di un account amministrativo dell'altro dominio.

**Nota:** Alcuni elementi come la cartella Stampanti, Risorse del computer e Risorse di rete non possono essere avviati da **Esegui come**.

##### Utilizzo di Esegui come

**Esegui come** può essere utilizzato in svariati modi:

**Per utilizzare Esegui come per avviare una shell dei comandi utilizzando le credenziali dell'account di amministratore del dominio**

1.  Fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui**, digitare **runas /user:**&lt;*nome\_dominio*&gt;**\\administrator cmd** (dove &lt;*nome\_dominio*&gt; è il nome del dominio), quindi fare clic su **OK**.

3.  Quando viene richiesto di immettere una password per l'account *nome\_dominio*\\administrator, digitare la password dell'account amministrativo, quindi premere INVIO.

4.  Si apre una nuova finestra della console per l'esecuzione nel contesto amministrativo. Il titolo della console la identifica come **Esecuzione come** *nome\_dominio***\\administrator**.

**Per utilizzare Esegui come per eseguire un elemento del Pannello di controllo**

1.  In Windows XP o Windows Server 2003 fare clic su **Start**, quindi scegliere **Pannello di controllo**.

2.  Mentre si tiene premuto il tasto MAIUSC, fare clic con il pulsante destro del mouse sullo strumento o programma da eseguire nel contesto amministrativo (ad esempio, **Installazione hardware**).

3.  Nel menu della scorciatoia, fare clic su **Esegui come**.

4.  Nella finestra di dialogo **Esegui come**,fare clic su **Utente seguente**, quindi immettere il nome dominio appropriato, il nome e la password dell'account amministrativo, ad esempio:

    CORPDOMAIN\\Administrator

    P@ssw0rd

5.  Fare clic su **OK**. Il programma viene eseguito nel contesto amministrativo.

**Per utilizzare Esegui come per aprire un programma del menu di avvio come Utenti e computer di Active Directory**

1.  In Windows Server 2003, fare clic su **Start**, selezionare **Strumenti di amministrazione**, quindi fare clic con il pulsante destro del mouse su **Utenti e computer di Active Directory**.

2.  Nel menu della scorciatoia, fare clic su **Esegui come**.

È possibile anche utilizzare il programma eseguibile **runas.exe** dalla riga di comando per eseguire programmi e avviare la console di gestione dalla riga di comando.

**Per avviare un'istanza del prompt dei comandi come amministratore del computer locale**

1.  Fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui**, digitare **runas /user:**&lt;*nomecomputerlocale*&gt;**\\administrator cmd**

3.  Scegliere **OK**.

4.  Quando richiesto, immettere la password dell'amministratore nella finestra del prompt dei comandi, quindi premere INVIO.

**Per avviare un'istanza dello snap-in Gestione computer con un account di amministratore di dominio chiamato** ***domainadmin*** **nel dominio** ***corpdomain***

1.  Fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui**, digitare **runas /user:**&lt;*corpdomain*&gt;**\\**&lt;*domainadmin*&gt; **"mmc %windir%\\system32\\compmgmt.msc"** 

3.  Scegliere **OK**.

4.  Quando richiesto, immettere la password dell'amministratore nella finestra del prompt dei comandi, quindi premere INVIO.

È possibile anche utilizzare **runas.exe** per eseguire programmi e avviare console di gestione dalla riga di comando con credenziali su smart card.

**Per avviare un'istanza del prompt dei comandi come amministratore del computer locale con credenziali smart card**

1.  Fare clic su **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui**, digitare **runas /smartcard /user**:&lt;*nomecomputerlocale*&gt;**\\administrator cmd**  

3.  Scegliere **OK**.

4.  Quando richiesto, digitare il PIN della smart card nella finestra del prompt dei comandi, quindi premere INVIO.

**Nota:** Non è possibile immettere la password come parametro dalla riga di comando in **runas.exe**, poiché questa operazione non è sicura.

#### Eseguire una sessione di Servizi terminal separata per l'amministrazione

**Esegui come** è l'approccio più comune utilizzato dagli amministratori per eseguire modifiche sui propri computer locali ed, eventualmente, per eseguire alcuni programmi specifici del settore. Per le proprie attività di amministratore IT, è possibile utilizzare Servizi terminal per collegarsi ai server da gestire. È molto più facile gestire più server remoti senza dover accedere fisicamente a ognuno di essi; questo approccio diminuisce la necessità di diritti di accesso interattivo sui server. Per utilizzare questo metodo, accedere con le normali credenziali dell'account utente, quindi eseguire una sessione Servizi terminal come amministratore del dominio. Le operazioni di amministrazione del dominio dovrebbero essere eseguite solo all'interno di quella finestra di sessione.

#### Rinominare l'account Administrator predefinito

Quando si rinomina l'account Administrator predefinito, si rimuove l'indicazione evidente che l'account ha privilegi elevati. Anche se un aggressore avrebbe comunque necessità della password per utilizzare l'account Administrator predefinito, un account predefinito Administrator ridenominato aggiunge un ulteriore livello di protezione contro gli attacchi di elevazione dei privilegi. Un'opzione potrebbe essere l'utilizzo di un nome e cognome fittizi, nello stesso formato degli altri nomi di utente.

**Nota:** Rinominare l'account Administrator predefinito impedisce solo alcuni tipi di attacchi. Per un aggressore è comunque relativamente facile determinare quale account è l'account Administrator predefinito, poiché l'ID di protezione di questo account è sempre lo stesso. Inoltre, sono disponibili strumenti per enumerare i membri dei gruppi e questi elencano sempre per primo l'account dell'amministratore originale. Per una migliore protezione contro gli attacchi all'account Administrator predefinito, si dovrebbe creare un nuovo account di amministrazione e disabilitare l'account predefinito.

**Per rinominare l'account Administrator predefinito di un dominio**

1.  Accedere come membro del gruppo Domain Admins (senza però utilizzare l'account Administrator predefinito), quindi aprire **Utenti e computer di Active Directory**.

2.  Nella struttura della console, fare clic su **Users**.

3.  Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **Administrator** e scegliere **Rinomina**.

4.  Digitare il nome e il cognome fittizi e premere INVIO.

5.  Nella finestra di dialogo **Rinomina Utente** modificare i valori **Nome completo**, **Nome**, **Cognome**, **Nome visualizzato**, **Nome accesso utente** e **Nome accesso utente (precedente a Windows 2000)** inserendo i dati del nome account fittizio, quindi scegliere **OK**.

6.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse sul nuovo nome e scegliere **Proprietà**.

7.  Selezionare la scheda **Generale**. Nel riquadro **Descrizione**,eliminare **Account predefinito per l'amministrazione del computer/dominio**, quindi digitare una descrizione simile a quella degli altri account utente (per molte organizzazioni, questo valore è vuoto).

8.  Scegliere **OK**.

**Per rinominare l'account Administrator locale predefinito**

1.  Accedere come membro del gruppo locale Administrators (ma non con l'account Administrator predefinito) e aprire lo strumento snap-in **Users e gruppi locali** nella console **Gestione computer**.

2.  Nella struttura della console, scegliere **Utenti e gruppi locali**, quindi fare clic su **Users**.

3.  Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **Administrator** e scegliere **Rinomina**.

4.  Digitare il nome e il cognome fittizi e premere INVIO.

5.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse sul nuovo nome e scegliere **Proprietà**.

6.  Selezionare la scheda **Generale**. Nel riquadro **Nome completo**, immettere il nuovo nome completo. Nel riquadro **Descrizione**,eliminare **Account predefinito per l'amministrazione del computer/dominio**, quindi digitare una descrizione simile a quella degli altri account utente (per molte organizzazioni, questo valore è vuoto).

7.  Scegliere **OK**.

**Nota:** Esiste anche un'impostazione dell'oggetto Criteri di gruppo (GPO) utilizzabile per ridenominare l'account Administrator predefinito su più computer. Questa impostazione non permette tuttavia di modificare la descrizione predefinita. Per ulteriori informazioni, vedere [HOW TO: Rename the Administrator and Guest Account in Windows Server 2003](http://support.microsoft.com/default.aspx?scid=kb;en-us;816109) (in inglese) nell'articolo della Knowledge Base all'indirizzo http://support.microsoft.com/default.aspx?scid=kb;en-us;816109.

#### Per creare un account Administrator fittizio

Per incrementare il livello di protezione, è possibile creare un account Administrator che funga da esca. Ciò può ingannare un aggressore che intenda condurre un attacco alla password dell'account Administrator, portandolo ad attaccare un account che non ha alcun privilegio speciale, diminuendo la probabilità che l'aggressore scopra l'account Administrator rinominato. È inoltre consigliabile allungare i tempi dell'attacco facendo in modo che l'account esca non venga bloccato e impostando su di esso una password complessa. Dopo avere creato l'account che fungerà da esca, ci si dovrebbe assicurare che non sia membro di alcun gruppo di protezione privilegiato e quindi controllare le attività impreviste nell'utilizzo dell'account come gli errori di accesso. Per ulteriori informazioni, vedere [Securing Active Directory Administrative Groups and Accounts](http://www.microsoft.com/technet/security/topics/networksecurity/sec_ad_admin_groups.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/security/topics/networksecurity/sec\_ad\_admin\_groups.mspx.

**Per creare un account Administrator di un dominio che funga da esca**

1.  Accedere come membro del gruppo Domain Admins, quindi aprire **Utenti e computer di Active Directory**.

2.  Fare clic con il pulsante destro del mouse sul contenitore **Users**, scegliere **Nuovo**, quindi fare clic su **Utente**.

3.  Digitare **Administrator** nelle caselle **Nome** e **Nome accesso utente**, quindi scegliere **Avanti**.

4.  Digitare e confermare una password.

5.  Deselezionare la casella di controllo **Cambiamento obbligatorio password all'accesso successivo**, quindi scegliere **Avanti**.

6.  Verificare che le informazioni dell'account siano corrette, quindi fare clic su **Fine**.

7.  Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **Administrator** e scegliere **Proprietà**.

8.  Selezionare la scheda **Generale**. Nella casella **Descrizione, digitareAccount predefinito per l'amministrazione del computer/dominio,** quindi scegliere **OK**.

**Per creare un account Administrator fittizio**

1.  Accedere come membro del gruppo locale Administrators e aprire lo strumento snap-in **Utenti e gruppi locali** nella console **Gestione computer**.

2.  Nella struttura della console, espandere **Utenti e gruppi locali**.

3.  Fare clic con il pulsante destro del mouse sul contenitore **Users**, quindi scegliere **Nuovo utente**.

4.  Nella casella **Nome utente**, digitare **Administrator**. Nella casella **Descrizione**, digitare **Account predefinito per l'amministrazione del computer/dominio**.

5.  Digitare e confermare una password.

6.  Deselezionare la casella di controllo **Cambiamento obbligatorio password all'accesso successivo**.

7.  Fare clic su **Crea**.

#### Creare un account Administrator secondario e disabilitare l'account predefinito

Anche se non si utilizza Servizi terminal per l'amministrazione o si concede l'accesso ai server a utenti che non sono amministratori, è consigliabile creare un utente aggiuntivo come account amministrativo secondario per amministrare i server. Questo utente dovrebbe essere membro del gruppo Administrators. Dopo avere creato l'account secondario, è possibile disabilitare l'account Administrator predefinito.

**Per creare un account Administrator secondario**

1.  Accedere come Administrator, quindi aprire **Utenti e computer di Active Directory**.

2.  Fare clic con il pulsante destro del mouse sul contenitore **Users**, scegliere **Nuovo**, quindi fare clic su **Utente**.

3.  In **Nome** e **Nome accesso utente**, digitare *&lt;user name&gt;*, quindi fare clic su **Avanti**.

4.  Digitare e confermare una password complessa.

5.  Deselezionare la casella di controllo **Cambiamento obbligatorio password all'accesso successivo**, quindi scegliere **Avanti**.

6.  Verificare che le informazioni dell'account siano corrette, quindi fare clic su **Fine**.

7.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse sul *nome utente* e scegliere **Proprietà**.

8.  Fare clic sulla scheda **Membro di**, fare clic su **Aggiungi**, digitare **administrators** e fare clic su **Controlla nomi**,quindi fare clic su **OK**.

9.  Fare clic su **OK** per chiudere la pagina **Proprietà**.

**Per disabilitare l'account Administrator predefinito**

1.  Accedere con l'account amministrativo secondario appena creato e aprire **Utenti e computer di Active Directory**.

2.  Fare clic sul contenitore **Utenti**, fare clic con il pulsante destro del mouse sul nome dell'account Administrator predefinito, quindi fare clic su **Proprietà**.

3.  Fare clic sulla scheda **Account**.

4.  Sotto **Opzioni account** scorrere l'elenco in basso e selezionare la casella di controllo **Account disabilitato**.

5.  Scegliere **OK**.

**Avviso:** Quando si disabilita l'account Administrator predefinito, è necessario essere sicuri che vi sia un altro account con i privilegi amministrativi appropriati. Se si disabilita l'account senza assicurarsi che esista un altro account disponibile, si potrebbe perdere controllo di amministrazione del dominio, il che potrebbe richiedere un ripristino del sistema o la sua reinstallazione.

#### Abilitare il blocco dell'account per gli accessi remoti da parte dell'amministratore

Un modo per impedire agli aggressori di utilizzare le credenziali e la password dell'account amministrativo predefinito consiste nel permettere che l'account di amministratore possa essere bloccato fuori dalla rete da un criterio per gli account, dopo che si è verificato un dato numero di errori di accesso. Per impostazione predefinita, l'account amministrativo predefinito non può essere bloccato; tuttavia, è possibile utilizzare **passprop.exe**, un programma dalla riga di comando contenuto nel *Resource Kit di Microsoft Windows 2000 Server*, per abilitare il blocco dell'account per accessi remoti eseguiti con l'account dell'amministratore. Quando si esegue l'utilità **passprop** con il parametro /ADMINLOCKOUT, si fa in modo che l'account dell'amministratore sia soggetto ai criteri di blocco per gli account. In Windows 2000 Server, questo si applica solo agli accessi remoti e, poiché l'account amministrativo incorporato non può essere mai bloccato sul computer locale, questo programma permette di proteggere l'account dell'amministratore da un attacco sulla rete ma ne consente ancora l'accesso interattivo.

**Avviso:** In Windows Server 2003, **passprop** permette il blocco dell'account amministrativo predefinito per gli accessi interattivi e remoti.

È possibile utilizzare con **passprop** i seguenti parametri per il blocco degli account:

passprop \[/adminlockout\] \[/noadminlockout\]

Il parametro /adminlockout mantiene bloccato l'amministratore.

Il parametro /noadminlockout rimuove il blocco dell'amministratore.

**Nota:** Quando si abilita questa impostazione e l'account è bloccato, nessuno può eseguire alcuna operazione di gestione remota con l'account dell'amministratore.

#### Creare una password complessa per l'amministratore

Utilizzare una password complessa per l'account Administrator predefinito. Una password complessa riduce al minimo la minaccia da parte di un aggressore che indovini la password e ottenga le credenziali dell'account Administrator. Una password complessa per l'account dell'amministratore dovrebbe:

-   Contenere almeno 15 caratteri.

-   Non contenere un nome di account, un nome reale o un nome di società.

-   Non contenere una parola completa tratta dal dizionario, anche se gergale, in qualsiasi lingua.

-   Essere alquanto diversa dalle password precedenti. Le password incrementali (Password1, Password2, Password3) non sono complesse.

-   Contenere caratteri tratti da almeno tre dei cinque gruppi elencati nella tabella che segue.

**Tabella 3.1 Tipi di caratteri per una password di amministrazione complessa**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipi di caratteri</p></th>
<th><p>Esempio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Lettere maiuscole.</p></td>
<td style="border:1px solid black;"><p>A, B, C...</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Lettere minuscole.</p></td>
<td style="border:1px solid black;"><p>a, b, c...</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Numeri</p></td>
<td style="border:1px solid black;"><p>0, 1, 2, 3...</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Simboli della tastiera non alfanumerici</p></td>
<td style="border:1px solid black;"><p>` ~ ! @ # $ % ^ &amp; * ( ) _ + - = { } | [ ] \ : &quot; ; ' &lt; &gt; ? , . /</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Caratteri Unicode.</p></td>
<td style="border:1px solid black;"><p>€, G, ƒ, ?</p></td>
</tr>  
</tbody>  
</table>
  
##### Utilizzare frasi di accesso invece di password
  
Il modo più semplice per creare una password complessa che non debba essere annotata è utilizzare una frase di accesso. Una frase di accesso è essenzialmente una frase che è possibile ricordare, come "Mio figlio Andrea ha tre anni in più di mia figlia Anna". È possibile creare una password ragionevolmente complessa utilizzando la prima lettera di ogni parola della frase. Ad esempio, "mfahtaipdmfa". È inoltre possibile rendere questa password ancora più complessa con una combinazione di lettere maiuscole e minuscole, numeri e caratteri speciali che somigliano a lettere. Ad esempio, se si utilizza la stessa frase memorizzabile e alcuni trucchi, la password può diventare MfAh3@i+dmfA.
  
Anche se le frasi di accesso cono vulnerabili agli attacchi basati su ricerche nei dizionari, la maggior parte del software commerciale per la scoperta delle password non controlla password con più di 14 caratteri. Se gli utenti utilizzano frasi di accesso abbastanza lunghe, la loro violazione è meno probabile e la loro memorizzazione è più facile rispetto alle password complesse tradizionali. È anche meno probabile che gli utenti annotino la password, se è facile da ricordare. Alcuni buoni esempi di frasi di accesso complesse sono:
  
-   Oggi pizz@ 4 stagi0ni & birr^!
  
-   Quanti € c0sta 1 pizz@ Margherit@?
  
Questi esempi contengono più di 20 caratteri, sono frasi di accesso molto lunghe e includono caratteri provenienti da quattro dei cinque possibili gruppi. Inoltre, non sono frasi note, ma è di gran lunga più facile ricordarle di una password di 15 caratteri che comprenda una miscela di caratteri alfanumerici, simboli e segni di punteggiatura indipendenti senza alcun significato intrinseco.
  
##### Non utilizzare password di amministrazione vuote o deboli
  
Anche se ciò costituisce un rischio significativo per la protezione, alcune organizzazioni hanno password deboli o vuote per l'account dell'amministratore. Le password deboli o vuote rappresentano una delle vulnerabilità più comuni in una rete e uno dei più facili punti di accesso per gli intrusi.
  
Quando si impostano password vuote o deboli per l'account dell'amministratore, gli utenti malintenzionati possono accedervi utilizzando combinazioni base, come "Administrator" per il nome utente e un valore vuoto o "administrator" come password. Password vuote e deboli cedono velocemente ai tentativi di individuazione della password e sono vulnerabili agli attacchi basati su ricerche nei dizionari, che provano metodicamente una parola dopo l'altra, e ai tentativi di violazione che utilizzano un elenco di caratteri comuni come A-Z e 0-9 in combinazioni lineari.
  
Anche se non è garantito che una buona password possa evitare che un intruso acceda alla rete, fornisce comunque un'eccellente prima linea di difesa.
  
##### Imporre password complesse.
  
Ci si dovrebbe assicurare che gli amministratori di rete dell'organizzazione utilizzino password complesse. In Windows 2000 Server e in Windows Server 2003, è possibile utilizzare i Criteri di gruppo per imporre l'utilizzo di password complesse.
  
Per ulteriori informazioni sulle password complesse e sicure, vedere il white paper (in inglese) [Enforcing Strong Password Usage Throughout Your Organization](http://www.microsoft.com/smallbusiness/gtm/securityguidance/articles/enforce_strong_passwords.mspx) all'indirizzo www.microsoft.com/smallbusiness/gtm/securityguidance/articles/enforce\_strong\_passwords.mspx e il white paper [Selecting Secure Passwords](http://www.microsoft.com/smallbusiness/gtm/securityguidance/articles/select_sec_passwords.mspx) (in inglese) all'indirizzo www.microsoft.com/smallbusiness/gtm/securityguidance/articles/select\_sec\_passwords.mspx.
  
##### Modificare periodicamente la password dell'amministratore
  
Le password degli account privilegiati dovrebbero essere modificate regolarmente. L'intervallo tra le modifiche dovrebbe essere deciso in base all'impatto che una compromissione dell'account potrebbe comportare per l'organizzazione. Per direttive su come definire l'impatto, fare riferimento a [The Security Risk Management Guide](http://www.microsoft.com/technet/security/guidance/secrisk/default.mspx)**(in inglese) all'indirizzo www.microsoft.com/technet/security/guidance/secrisk/default.mspx.
  
Le password degli account degli amministratori locali dovrebbero essere modificate regolarmente. È possibile automatizzare questo processo per server e workstation con lo strumento **cusrmgr.exe** incluso nel *Resource Kit di Microsoft Windows 2000 Server*. Per ulteriori informazioni sull'utilizzo di **cusrmgr.exe**, vedere l'articolo [How to Use the Cusrmgr.exe Tool to Change Administrator Account Password on Multiple Computers](http://support.microsoft.com/kb/272530) della Knowledge Base (in inglese) all'indirizzo http://support.microsoft.com/kb/272530.
  
Si dovrebbe anche modificare regolarmente la password di amministratore nella modalità ripristino servizi directory (DSRM) sui controller di dominio. Per reimpostare la password DSRM, Windows 2000 utilizza l'utilità **setpwd**. Per questa funzionalità, in Windows 2000 si utilizza l'utilità **Ntdsutil**. Entrambi gli strumenti possono essere utilizzati da una postazione remota.
  
#### Automatizzare la ricerca di password deboli
  
Le password deboli e vuote compromettono significativamente la protezione generale della rete di un'organizzazione. Le organizzazioni dovrebbero creare o acquistare software che esegua una scansione automatica per cercare le password vuote e deboli.
  
Questi tipi di strumenti adottano due metodi di base:
  
-   **Tentativi multipli di accessi alla rete utilizzando le password deboli più comuni**. Microsoft Baseline Security Analyzer (MBSA) rappresenta un esempio di strumento di questo tipo. Questo metodo è sconsigliato poiché la metodologia in linea può causare una negazione di servizio se è consentito il blocco degli account.
  
-   **Scansione delle password fuori linea**. Sono disponibili ottimi strumenti di terze parti per la scansione non in linea. Tali strumenti possono aiutare a ridurre i rischi di protezione di un'organizzazione, permettendo agli amministratori di identificare e rimediare alle vulnerabilità della protezione derivanti da password deboli o facilmente ottenibili. Di solito, questi strumenti eseguono una scansione delle password deboli e forniscono quindi una classificazione della qualità delle password, oltre a funzionalità di notifica e riparazione. Questo è il metodo raccomandato per identificare le password deboli.
  
Dopo aver identificato un account con una password vuota o debole, le misure da prendere dovrebbero seguire il protocollo di risposta stabilito dall'organizzazione. Alcuni esempi di protocollo di risposta sono:
  
-   Il sistema automatizzato sostituisce la password dell'account impostando una password complessa.
  
-   Il sistema automatizzato invia un messaggio di posta elettronica al proprietario del server per richiedere la sostituzione della password.
  
L'ultima risposta può prolungare il periodo di vulnerabilità del server.
  
##### Eseguire una scansione delle password utilizzando Microsoft Baseline Security Analyzer
  
È possibile utilizzare [Microsoft Baseline Security Analyzer (MBSA)](http://www.microsoft.com/technet/security/tools/mbsahome.mspx), disponibile all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx, per eseguire la scansione di ogni computer in rete e ricercare le password deboli.
  
Tra gli altri test della protezione, MBSA può enumerare tutti gli account utente e controllare i seguenti punti deboli delle password:
  
-   La password è vuota
  
-   La password coincide con il nome dell'account utente
  
-   La password coincide con il nome del computer
  
-   La password utilizza la parola "password"
  
-   La password utilizza la parola "admin" o "administrator"
  
In seguito a questa scansione, viene comunicata la presenza di qualsiasi account disabilitato o bloccato.
  
Per eseguire questo test, MBSA cerca di modificare la password sul computer di destinazione utilizzando ciascuna di queste password. MBSA non reimposta né modifica permanentemente la password, ma invia un avviso se la password non è abbastanza complessa e rappresenta quindi un pericolo per la protezione.
  
#### Utilizzare le credenziali amministrative solo su computer affidabili
  
Assicurarsi che gli amministratori dell'organizzazione non utilizzino mai le credenziali amministrative per accedere a un computer di cui non hanno il controllo completo. Sul computer potrebbe essere attivo un registratore di battute o di schermate, che potrebbe acquisire le credenziali e la password dell'amministratore.
  
Un registratore di battute è un programma spyware non rilevabile che viene eseguito in background sul computer di un utente. I programmatori di spyware progettano i loro registratori di battute per rimanere nascosti mentre registrano tutte le battute senza che l'utente acconsenta o ne sia a conoscenza. Queste informazioni sono quindi memorizzate in modo da essere recuperate in seguito o trasmesse all'autore del registratore di battute per essere analizzate. I registratori di battute possono registrare tutte le battute, incluse le informazioni personali come password o numeri di carte di credito. Sono inoltre in grado di registrare tutta la posta elettronica redatta o le sessioni di conversazione in linea.
  
Un registratore di schermate cattura dati in formato carattere da un computer o da un programma, esaminando il contenuto di schermate che non contengono dati da trasmettere e presentandole quindi in un formato più comprensibile, come quello di un'interfaccia utente grafica (GUI). I registratori di schermo più recenti presentano le informazioni in formato HTML, così da renderle accessibili tramite un browser.
  
#### Controllare account e password a intervalli regolari
  
I controlli regolari aiutano ad assicurare l'integrità della protezione del dominio e proteggono dall'elevazione dei privilegi. L'elevazione dei privilegi può fornire agli account utente privilegi amministrativi non autorizzati. Se non si proteggono le funzionalità amministrative, gli aggressori potrebbero generare vulnerabilità ed eludere le misure di protezione. Ad esempio, gli aggressori che dispongono di privilegi amministrativi possono creare account utente fittizi, aggiungere senza autorizzazione gli account ai gruppi, elevare i privilegi degli account esistenti, aggiungere o modificare criteri e disabilitare le impostazioni di protezione.
  
Si dovrebbero controllare regolarmente tutti gli utenti e i gruppi amministrativi a livello di dominio e tutti gli utenti e i gruppi amministrativi locali sui server sensibili. Poiché gli amministratori possono avere le capacità, ma non l'autorità, per eseguire modifiche sui propri account amministrativi, le organizzazioni devono garantire che gli account soddisfino i criteri di protezione per gli utenti amministrativi a livello di dominio. È importante controllare l'utilizzo delle credenziali privilegiate e rendersi conto che il controllo non consiste soltanto nel controllare la complessità delle password. Il controllo è anche uno strumento utile per scoprire quali attività sono state eseguite dagli account amministrativi. Utilizzare Visualizzatore eventi per visualizzare i file di registrazione relativi alla protezione creati dopo la configurazione e l'abilitazione del controllo. Controlli regolari possono anche rilevare account amministrativi inutilizzati a livello di dominio. Gli account amministrativi inutilizzati a livello di dominio costituiscono un punto vulnerabile dell'ambiente di rete, soprattutto se un aggressore li compromette senza che ciò sia notato. Si dovrebbe rimuovere qualsiasi account amministrativo inutilizzato a livello di dominio.
  
#### Vietare la delega degli account
  
Si dovrebbero designare tutti gli account utente a livello di amministratore di dominio con l'attributo **L'account è sensibile e non può essere delegato**. Quest'operazione aiuta a proteggere le credenziali dalla rappresentazione attraverso un server contrassegnato come **trusted per delega**.
  
L'autenticazione delegata si verifica quando un servizio di rete accetta una richiesta da un utente e accetta l'identità di quell'utente per avviare una nuova connessione a un secondo servizio di rete. L'autenticazione delegata è utile per applicazioni multi-tier che utilizzano la funzionalità di collegamento singolo da più computer. Ad esempio, i controller di dominio sono automaticamente trusted per delega. Se si abilita Crittografia file system (EFS) su un file server, il server deve essere trusted per delega per memorizzare i file crittografati per conto degli utenti. L'autenticazione delegata è utile anche per i programmi in cui Internet Information Services (IIS) supporta un'interfaccia Web verso un database eseguito su un altro computer, come Microsoft Outlook® Web Access (OWA) in Microsoft Exchange Server o per il supporto di pagine di registrazione Web per un'autorità di certificazione aziendale, se le pagine sono ospitate su un server Web separato.
  
Si dovrebbe negare il diritto di partecipare all'autenticazione delegata agli account di computer in Active Directory, ai computer che sono non fisicamente protetti e agli account degli amministratori di dominio. Gli account degli amministratori di dominio hanno accesso a risorse sensibili e, se compromessi, mettono seriamente a repentaglio l'organizzazione. Per ulteriori informazioni,vedere l'argomento [Enabling Delegated Authentication](http://technet.microsoft.com/en-us/library/cc780217.aspx)nel**[Windows Server 2003 Deployment Kit](http://technet.microsoft.com/en-us/library/cc739492.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/all/deployguide/en-us/dsscc\_aut\_vwcs.asp.
  
#### Controllare la procedura per l'accesso di amministrazione
  
I membri dei gruppi Administrators, Enterprise Admins e Domain Admins rappresentano gli account più potenti nell'insieme di strutture e in ogni singolo dominio. Per minimizzare i rischi per la protezione, eseguire i passaggi descritti nelle successive sezioni di questa guida per imporre credenziali amministrative difficilmente violabili.
  
##### Richiedere smart card per l'accesso amministrativo
  
Agli amministratori di dominio dovrebbe essere richiesto di utilizzare un'autenticazione a due fattori per tutte le funzioni amministrative. L'autenticazione a due fattori richiede due parti:
  
-   Un elemento posseduto dall'utente, come una smart card
  
-   Un elemento conosciuto dall'utente, come un numero di identificazione personale (PIN)
  
La necessità di entrambi i fattori attenua il rischio di un accesso non autorizzato per mezzo di credenziali a fattore unico condivise, rubate o duplicate, come nomi utente e password.
  
L'autenticazione a due fattori è un elemento importante quando si proteggono gli account di amministratore di dominio, poiché i nomi e le password utente convenzionali sono credenziali in testo leggibile, generalmente formate da serie di caratteri in linguaggio naturale. In quanto tali, potrebbero essere rubate, condivise o duplicate da un utente malintenzionato nei seguenti casi:
  
-   Un utente attendibile condivide la sua password con un utente non autorizzato o registra la password in un modo poco sicuro (ad esempio, su un foglietto adesivo attaccato al monitor).
  
-   La password viene trasmessa come testo leggibile.
  
-   Un dispositivo hardware o software viene utilizzato per catturare le battute sulla tastiera durante l'accesso.
  
Se si chiede agli amministratori di utilizzare smart card per l'accesso interattivo, si costringono gli utenti amministrativi a possedere fisicamente le schede per l'accesso e si assicura l'utilizzo di password generate casualmente e crittografate in modo complesso per gli account utente. Queste password complesse aiutano a proteggere contro il furto di password deboli per ottenere l'accesso amministrativo.
  
È possibile imporre l'utilizzo di smart card se si abilita l'opzione **Per l'accesso interattivo è necessaria una smart card** per ogni account utente amministrativo.
  
Il PIN della smart card è un codice crittografato che il singolo proprietario della scheda imposta e memorizza nella scheda. Il PIN è una stringa che l'utente deve fornire quando esegue l'autenticazione con la smart card per far sì che la chiave privata sia disponibile per l'utilizzo. Ogni chiave privata su una smart card è univoca, garantendo l'univocità dell'autenticazione.
  
L'autenticazione mediante smart card è particolarmente importante quando un amministratore di dominio utilizza l'accesso interattivo. Le smart card possono semplificare le attività degli amministratori di dominio responsabili di più server, ognuno dei quali richiede l'autenticazione. Anziché chiedere a un amministratore di avere una password diversa per ogni server su cui si deve autenticare, è possibile proteggere i server con smart card univoche con un PIN in comune.
  
**Nota:** Windows 2000 Server supporta l'utilizzo delle smart card per l'accesso remoto; tuttavia, in Windows Server 2003 viene richiesto di supportare l'utilizzo delle smart card per gli account a livello di dominio. In Windows Server 2003 è richiesto anche di utilizzare credenziali smart card con il comando **runas** del Servizio di accesso secondario.
  
La distribuzione di smart card agli amministratori di dominio e l'adozione dei principi e delle procedure descritti in questa guida può aiutare le organizzazioni a migliorare significativamente la protezione delle loro risorse di rete.
  
Per ulteriori informazioni sull'utilizzo delle smart card per l'autenticazione, consultare le seguenti risorse:
  
-   [The Smart Card Deployment Cookbook](http://technet.microsoft.com/en-us/library/dd277386.aspx) (in inglese), nel sito Web di Microsoft TechNet all'indirizzo www.microsoft.com/technet/security/topics/smrtcard/smrtcdcb/default.mspx.
  
-   [Planning a Smart Card Deployment](http://technet.microsoft.com/en-us/library/cc776850.aspx) (in inglese), all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/DepKit/f65c054e-4cb3-4a6e-84f6-8a9787819df5.mspx.
  
##### Condividere le credenziali di accesso per gli account amministrativi sensibili
  
Per ogni account considerato sensibile, ad esempio, un account che è membro dei gruppi Enterprise Admins o Domain Admins nel dominio principale di un insieme di strutture, è opportuno far sì che l'account sia condiviso da due utenti, in modo che debbano essere entrambi presenti per potervi accedere. Quando si condividono questi account, viene fornito un controllo visivo intrinseco: un utente osserva le operazioni eseguite dall'altro. Ciò impedisce inoltre che un singolo utente possa accedere privatamente al computer come amministratore per comprometterne la protezione, in quanto amministratore disonesto o sotto coercizione.
  
È possibile implementare account amministrativi condivisi che utilizzino password suddivise o smart card e PIN. Se si utilizzano credenziali basate su password per gli account amministrativi, si può dividere la password tra i due utenti che condividono l'account, in modo che ogni utente conosca solo metà della password. Ogni utente è responsabile della conservazione della propria metà della password. Ad esempio, è possibile creare un account amministrativo chiamato admin1 e fare in modo che due utenti affidabili, Gianna e Roberto, condividano l'account. Ogni utente gestisce metà della password. Perché uno di loro possa accedervi e utilizzare l'account, l'altro deve essere presente per immettere l'altra metà della password.
  
Lo svantaggio della scelta di utilizzare account amministrativi condivisi è la mancanza intrinseca di responsabilità mediante controllo. Le organizzazioni dovranno disporre di un altro controllo sul posto, ad esempio una videocamera, per garantire che gli utenti non abusino dei privilegi condivisi.
  
Se si utilizzano credenziali basate su smart card per gli account amministrativi, suddividere la proprietà della smart card e del relativo PIN tra i due utenti che condividono l'account, in modo che un utente mantenga la proprietà fisica della smart card e l'altro utente gestisca il PIN. In questo modo, entrambi gli utenti devono essere presenti per accedere all'account.
  
##### Limitare le modalità e i luoghi in cui gli amministratori di dominio possono eseguire l'accesso
  
Le organizzazioni dovrebbero limitare le modalità e i luoghi in cui un amministratore di dominio può eseguire l'accesso. Se necessario per la loro attività o il loro ruolo, gli amministratori possono accedere in modo interattivo ai controller di dominio per cui hanno i privilegi, ma si dovrebbe comunque richiedere l' autenticazione a due fattori.
  
Si dovrebbe proibire agli amministratori di dominio di accedere a qualsiasi computer che non sia specificatamente approvato per l'utilizzo da parte dell'amministratore del dominio nei casi seguenti:
  
-   Quando si utilizzano accessi interattivi
  
-   Quando si utilizza Desktop remoto
  
-   Quando si accede come servizio
  
-   Quando si accede come processo batch
  
##### Download
  
[![](images/Dd536181.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41316)
  
[](#mainsection)[Inizio pagina](#mainsection)
