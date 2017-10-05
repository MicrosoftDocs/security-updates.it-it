---
TOCTitle: 'Capitolo 10: Voci aggiuntive di registro'
Title: 'Capitolo 10: Voci aggiuntive di registro'
ms:assetid: 'd635616a-3c5c-4234-8946-e29c142cf692'
ms:contentKeyID: 20200881
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536282(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 10: Voci aggiuntive di registro

In questo capitolo vengono fornite ulteriori informazioni relative alle voci del Registro di sistema (anche chiamati *valori del Registro di sistema*) per il file del modello di protezione di base non definiti all'interno del file del modello amministrativo (.adm). Nel file .adm sono definiti i criteri di sistema e le restrizioni per il desktop, la shell e la protezione per Microsoft Windows Server 2003.

##### In questa pagina

[](#egaa)[Editor di configurazione della protezione personalizzato](#egaa)
[](#efaa)[Voci del Registro relative a TCP/IP](#efaa)
[](#eeaa)[Varie voci del Registro di sistema](#eeaa)
[](#edaa)[Voci di registro disponibili in Windows XP con SP2 e Windows Server 2003 con SP1](#edaa)
[](#ecaa)[Voci di registro disponibili in Windows XP con SP2](#ecaa)
[](#ebaa)[Voci di registro disponibili in Windows Server 2003 con SP1](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Editor di configurazione della protezione personalizzato

Quando si carica lo snap-in Modelli di protezione di Microsoft Management Console (MMC) e si visualizzano i modelli di protezione, le voci indicate nelle seguenti tabelle non sono rappresentate. Queste voci sono state aggiunte al file .inf utilizzando una versione personalizzata dell'Editor di configurazione della protezione (SCE, Security Configuration Editor). Possono essere visualizzate o modificate anche con un editor di testi come Blocco note. Saranno applicate ai computer quando si scaricano i criteri, a prescindere dal fatto che l'interfaccia utente di SCE sia stata modificata o meno.

Queste voci sono incluse nei modelli di protezione per l'automazione delle modifiche. Se il criterio viene rimosso, queste voci non vengono rimosse automaticamente insieme ad esso, ma devono essere modificate manualmente, utilizzando uno strumento di modifica del Registro di sistema, come Regedt32.exe. La cartella di lavoro di Microsoft Excel "Windows Default Security and Services Configuration" della presente guida, riporta le impostazioni predefinite.

#### Modifica dell'interfaccia utente dell'Editor di configurazione della protezione

L'Editor SCE viene utilizzato per definire i modelli di protezione che possono essere applicati a singoli computer o a un numero non definito di computer attraverso i Criteri di gruppo. I modelli di protezione possono contenere criteri password, criteri di blocco, criteri protocollo di autenticazione Kerberos, criteri di controllo, impostazioni del registro eventi, valori del Registro di sistema, modalità di avvio servizio, autorizzazioni per servizi, diritti utente, restrizioni per l'appartenenza ai gruppi, autorizzazioni del Registro di sistema e autorizzazioni del file system. L''Editor SCE viene visualizzato in molti snap-in di MMC e in Strumenti di amministrazione. È utilizzato dallo snap-in Modelli di protezione e dallo snap-in Configurazione e analisi della protezione. Lo snap-in Editor Criteri di gruppo lo utilizza per la porzione di Impostazioni di protezione della struttura Configurazione computer. Viene utilizzata inoltre per: Impostazioni protezione locale, Criterio di protezione del controller di dominio e anche per gli strumenti Criterio di protezione del dominio.

In questa guida sono comprese le voci supplementari aggiunte all'Editor SCE modificando il file seregvl.inf (nella cartella **%systemroot%\\inf**) e registrando nuovamente il file scecli.dll. Le impostazioni di protezione originali e le impostazioni aggiuntive compaiono in **Criteri locali\\Protezione** negli snap-in e negli strumenti menzionati in precedenza nella presente guida. È necessario aggiornare il file sceregvl.inf e ripetere la registrazione del file scecli.dll in tutti i computer in cui si modificano i modelli di protezione e i Criteri di gruppo forniti con questa guida e descritti nelle sezioni riportate di seguito. Tuttavia, le informazioni sulla personalizzazione del file sceregvl.inf utilizzano funzionalità disponibili soltanto in Microsoft Windows XP Professional con Service Pack 1 (SP1) e in Windows Server 2003: non tentare di installarlo in versioni precedenti di Windows.

Una volta modificato e registrato il file sceregvl.inf, i valori personalizzati del Registro di sistema vengono visualizzati nelle interfacce utente di SCE del computer. Le nuove impostazioni vengono visualizzate in fondo all'elenco di elementi nell'interfaccia utente di SCE e sono precedute dal testo "MSS": MSS sta per "Microsoft Solutions for Security", che è il nome del gruppo che ha creato questa guida. Sarà quindi possibile creare modelli o criteri di protezione per definire questi nuovi valori del Registro di sistema. Questi modelli o criteri possono essere quindi applicati a qualsiasi computer a prescindere dal fatto che il file Sceregvl.inf sia stato modificato sul computer di destinazione o meno. Nei successivi avvii dell'interfaccia utente di SCE vengono visualizzati i valori personalizzati del Registro di sistema.

Le istruzioni su come modificare l'interfaccia utente di SCE sono fornite nelle seguenti procedure. Se sono state già effettuate altre personalizzazioni all'Editor SCE, è necessario seguire alcune istruzioni manuali. Uno script viene fornito per consentire di aggiungere impostazioni con una minima interazione da parte dell'utente e anche se al suo interno ha funzioni che permettono di rilevare e correggere l'errore, queste potrebbero non funzionare. Se non vengono eseguite correttamente, è necessario stabilire la causa dell'errore e correggere il problema o seguire le istruzioni manuali. Un altro script è fornito per ripristinare l'interfaccia utente di SCE allo stato predefinito. Questo script rimuoverà tutte le impostazioni personalizzate e riporterà l'Editor SCE alla visualizzazione dell'installazione predefinita di Windows XP con SP2 o Windows Server 2003 con SP1.

**Per aggiornare manualmente il file sceregvl.inf**

1.  Per aprire il file **Values-sceregvl.txt** dalla cartella di **SCE Update** contenuta nel download di questa guida, utilizzare un editor di testi, come ad esempio Blocco note.

2.  Aprire un'altra finestra nell'editor di testi, quindi aprire il file **%systemroot%\\inf\\sceregvl.inf**.

3.  Passare nella parte inferiore della sezione "\[Register Registry Values\]" nel file **sceregvl.inf.** Copiare e incollare il testo dal file **Values-sceregvl.txt**, senza interruzioni di pagina, in questa sezione del file **sceregvl.inf.**

4.  Chiudere il file **values-sceregvl.txt** e aprire il file **strings-sceregvl.txt** dalla cartella **SCE Update** del download.

5.  Passare nella parte inferiore della sezione "\[Strings\]" nel file **sceregvl.inf.** Copiare e incollare il testo dal file Strings-sceregvl.txt, senza interruzioni di pagina, in questa sezione del file **sceregvl.inf**.

6.  Salvare il file **sceregvl.inf** e chiudere l'editor di testo.

7.  Aprire una finestra del prompt dei comandi e immettere il comando **regsvr32 scecli.dll** per registrare di nuovo la DLL.

Nei successivi avvii dell'interfaccia utente di SCE vengono visualizzati i valori personalizzati del Registro di sistema.

**Per aggiornare automaticamente il file sceregvl.inf**

1.  Per rendere effettivo il funzionamento dello script, i file **Values-sceregvl.txt,Strings-sceregvl.txt,** e **Update\_SCE\_with\_MSS\_Regkeys.vbs** situati nella cartella **Aggiornamento SCE** contenuta nel download di questa guida, devono trovarsi tutti nella stessa posizione.

2.  Eseguire lo script **Update\_SCE\_with\_MSS\_Regkeys.vbs** sul computer da aggiornare.

3.  Seguire i prompt su schermo

Questa procedura rimuoverà solamente le voci personalizzate realizzate con lo script descritto nella procedura precedente, **Update\_SCE\_with\_MSS\_Regkeys.vbs**. È inoltre possibile annullare le modifiche effettuate con lo script di aggiornamenti automatici.

**Per annullare le modifiche effettuate dallo script Update\_SCE\_with\_MSS\_Regkeys.vbs**

1.  Eseguire lo script **Rollback\_SCE\_for\_MSS\_Regkeys.vbs** sul computer da aggiornare.

2.  Seguire i prompt su schermo

Questa procedura rimuoverà *qualsiasi* voce personalizzata aggiunta all'interfaccia utente di SCE, tra cui quelle della presente guida e tutte le altre voci che possono esser state fornite nelle versioni precedenti della presente guida o di altre guide per la protezione.

**Per ripristinare lo stato predefinito dell'Editor SCE per Windows XP con SP2 o Windows Server 2003 con SP1**

1.  Per rendere effettivo il funzionamento dello script, i file **sceregvl\_W2K3\_SP1.inf.txt,** **sceregvl\_XPSP2.inf.txt,** e **Restore\_SCE\_to\_Default.vbs** situati nella cartella di **Aggiornamento SCE** contenuta nel download di questa guida, devono trovarsi tutti nella stessa posizione.

2.  Eseguire lo script **Restore\_SCE\_to\_Default.vbs** sul computer da aggiornare.

3.  Seguire i prompt su schermo

**Per ripristinare manualmente l'interfaccia utente di SCE allo stato predefinito**

1.  Fare clic su **Start**, **Esegui**, digitare **regedit.exe** e premere INVIO per aprire l'Editor del Registro di sistema.

2.  Passare a **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\SecEdit\\Reg Values**.

3.  Ciascuna sottochiave presente in questa posizione rappresenta un elemento nella sezione di Opzioni di Protezione dell'Editor SCE. Prestare la massima attenzione nell'eliminazione di tutte le sottochiavi. **Non eliminare la chiave principale** (Reg Values), ma soltanto le sottochiavi contenute al suo interno.

4.  Aprire un prompt dei comandi e immettere il comando **regsvr32 scecli.dll** per registrare di nuovo la DLL dell'interfaccia utente di SCE.

5.  Gli avvii successivi di SCE consentiranno di visualizzare esclusivamente i valori originali del Registro di sistema contenuti nella versione di Windows

[](#mainsection)[Inizio pagina](#mainsection)

### Voci del Registro relative a TCP/IP

Per prevenire gli attacchi di tipo Denial of Service (DoS), è necessario mantenere aggiornato il computer con le correzioni per la protezione più recenti e proteggere con particolare attenzione lo stack dei protocolli TCP/IP nei computer Windows Server 2003 esposti a possibili attacchi. La configurazione dello stack TCP/IP è ottimizzata per gestire il traffico standard delle reti Intranet. Se si connette un computer direttamente a Internet, è consigliabile rafforzare la protezione dello stack TCP/IP contro agli attacchi DoS.

Gli attacchi DoS diretti allo stack TCP/IP di solito appartengono a due classi: attacchi che utilizzano una quantità eccessiva di risorse del sistema aprendo, ad esempio, numerose connessioni TCP; o attacchi che inviano pacchetti appositamente congegnati per causare un errore nello stack di rete o nell'intero sistema operativo. Queste impostazioni del Registro di sistema consentono di proteggersi dagli attacchi diretti allo stack TCP/IP.

Al file del modello presente in **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\** sono state aggiunte le impostazioni del Registro di sistema della tabella riportata di seguito. Ulteriori informazioni su ciascuna impostazione sono disponibili nelle sottosezioni che seguono la tabella e alla pagina "[Microsoft Windows Server 2003 TCP/IP Implementation Details](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/networking/tcpip03.mspx)" (in inglese) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/networking/tcpip03.mspx.](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/networking/tcpip03.mspx)

**Tabella 10.1 Voci del Registro relative a TCP/IP in Windows Server 2003 con SP1 e Windows XP con SP2**

 
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
<th style="border:1px solid black;" >Predefinito XP SP2</th>
<th style="border:1px solid black;" >Predefinito 2003 SP1</th>
<th style="border:1px solid black;" >Valore di massima protezione (decimale)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">DisableIPSourceRouting</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">EnableDeadGWDetect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">EnableICMPRedirect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">KeepAliveTime</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">7200000</td>
<td style="border:1px solid black;">7200000</td>
<td style="border:1px solid black;">300.000</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PerformRouterDiscovery</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SynAttackProtect</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TcpMaxConnectResponseRetransmissions</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TcpMaxDataRetransmissions</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">3</td>
</tr>
</tbody>
</table>
  
#### DisableIPSourceRouting: IP source routing protection level (protects against packet spoofing)
  
Questa voce è presente come **MSS: (DisableIPSourceRouting) IP source routing protection level (protects against packet spoofing)** nell'interfaccia utente di SCE. Il source routing IP è un meccanismo che consente al mittente di determinare il routing IP che un datagramma deve seguire sulla rete.
  
##### Vulnerabilità
  
L'autore di un attacco potrebbe utilizzare dei pacchetti con origine routing per nascondere la propria identità e posizione. L'origine routing consente a un computer che invia un pacchetto di specificare la route da seguire.
  
##### Contromisura
  
Configurare la voce **MSS: (DisableIPSourceRouting) IP source routing protection level (protects against packet spoofing)** su un valore **Highest protection,** **source routing is completely disabled**.
  
I possibili valori del Registro di sistema sono:
  
-   0, 1, o 2. La configurazione predefinita è 1 (i pacchetti con origine di routing non sono inoltrati).
  
Nell'interfaccia utente di SCE viene visualizzato il seguente elenco di opzioni:
  
-   No additional protection, source routed packets are allowed.
  
-   Medium, source routed packets ignored when IP forwarding is enabled.
  
-   Highest protection, source routing is completely disabled.
  
-   Non definito.
  
##### Impatto potenziale
  
Se si imposta questo valore su **2**, tutti i pacchetti in ingresso con origine routing verranno scartati.
  
#### EnableDeadGWDetect consente il rilevamento automatico di gateway di rete inattivi (potrebbe provocare DoS)
  
Questa voce è presente come **MSS: (EnableDeadGWDetect) Allow automatic detection of dead network gateways (could lead to DoS)** nell'interfaccia utente di SCE. Quando si attiva il rilevamento dei gateway inattivi, se si evidenziano delle difficoltà per un certo numero di connessioni, l'IP potrebbe spostarsi su un gateway di backup.
  
##### Vulnerabilità
  
L'autore di un attacco potrebbe forzare il server a cambiare gateway, attivandone magari uno non desiderato. Potrebbe essere un'operazione particolarmente difficile, per questo il valore di questa voce è ridotto.
  
##### Contromisura
  
Configurare la voce **MSS: (EnableDeadGWDetect) Allow automatic detection of dead network gateways (could lead to DoS)** su **Disabilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 1 (abilitato) su Windows Server 2003.
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disabilitato
  
-   Non definito
  
##### Impatto potenziale
  
Configurando questo valore su **0**, Windows non rileva più i gateway inattivi e attiva automaticamente un gateway alternativo.
  
#### EnableICMPRedirect consente ai reindirizzamenti di ICMP di sostituire le route generate con OSPF
  
Questa voce è presente come **MSS: (EnableICMPRedirect) Allow ICMP redirects to override OSPF generated routes** nell'interfaccia utente di SCE. I reindirizzamenti del protocollo ICMP (Internet Control Message Protocol) provocano la canalizzazione delle route dell'host da parte dello stack. Tali route sostituiscono quelle generate da OSPF (Open Shortest Path First).
  
##### Vulnerabilità
  
Questo comportamento è normale. Il problema è che il periodo di timeout di 10 minuti per le route canalizzate e reindirizzate ICMP crea una situazione della rete durante la quale il traffico non viene più instradato in modo corretto verso l'host interessato.
  
##### Contromisura
  
Configurare la voce **MSS: (EnableICMPRedirect) Allow ICMP redirects to override OSPF generated routes** su **Disabilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 1 (attivato).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disattivato
  
-   Non definito
  
##### Impatto potenziale
  
Quando è configurato come router di confine sistema autonomo (ASBR, Autonomous System Boundary Router), il servizio Routing e Accesso remoto (RRAS, Routing Remote Access Service) non importa in modo corretto le route di subnet di interfaccia collegate. Invece il router inserisce le route host nelle route OSPF. Poiché non è possibile utilizzare il router OSPF come router ASBR, l'importazione delle route di subnet di interfaccia collegate in OSPF produce delle tabelle di routing confuse con percorsi di routing inverosimili.
  
#### KeepAliveTime: How often keep-alive packets are sent in milliseconds (300,000 is recommended)
  
Questa voce è presente come **MSS: (KeepAliveTime) How often keep-alive packets are sent in milliseconds (300,000 is recommended)** nell'interfaccia utente di SCE. Con questo valore è possibile controllare la frequenza dei tentativi da parte del TCP di verificare se una connessione inattiva è ancora intatta, tramite l'invio di un pacchetto keep-alive. Se il computer remoto è ancora raggiungibile, il pacchetto keep-alive verrà riconosciuto.
  
##### Vulnerabilità
  
L'autore di un attacco che riesca a connettersi ad applicazioni di rete potrebbe provocare una condizione di DoS attivando molte connessioni.
  
##### Contromisura
  
Configurare la voce **MSS: (KeepAliveTime) How often keep-alive packets are sent in milliseconds (300.000 is recommended)** su **300000** **o 5 minuti**.
  
I possibili valori del Registro di sistema sono:
  
-   Da 1 a 0xFFFFFFFF. Il valore predefinito è 7.200.000 (due ore).
  
Nell'interfaccia utente di SCE viene visualizzato il seguente elenco di opzioni:
  
-   150000 o 2,5 minuti
  
-   300000 o 5 minuti **(consigliato)**
  
-   600000 o 10 minuti
  
-   1200000 o 20 minuti
  
-   2400000 o 40 minuti
  
-   3600000 o 1 ora
  
-   7200000 o 2 ore **(valore predefinito)**
  
-   Non definito
  
##### Impatto potenziale
  
I pacchetti keep-alive non vengono inviati da Windows per impostazione predefinita. Tuttavia, alcune applicazioni possono configurare il flag dello stack TCP che richiede pacchetti keep-alive. Per tali configurazioni, è possibile ridurre il valore dalle 2 ore predefinite a 5 minuti in modo da disconnettere più rapidamente le sessioni inattive.
  
#### PerformRouterDiscovery: Allow IRDP to detect and configure Default Gateway addresses (could lead to DoS)
  
Questa voce è presente come **MSS: (PerformRouterDiscovery) Allow IRDP to detect and configure Default Gateway addresses (could lead to DoS)** nell'interfaccia utente di SCE. Questa impostazione viene utilizzata per abilitare o disabilitare l'IRDP (Internet Router Discovery Protocol). L'IRDP consente al computer di rilevare e configurare automaticamente gli indirizzi di gateway predefiniti in base all'interfaccia secondo quanto descritto in RFC 1256.
  
##### Vulnerabilità
  
L'autore di un attacco che avesse acquisito il controllo di un computer che insiste sul medesimo segmento della rete potrebbe configurare un computer della rete in modo da simulare un router. Gli altri computer con l'IRDP attivato tenterebbero quindi di instradare il traffico verso il computer già compromesso.
  
##### Contromisura
  
Configurare la voce **MSS: (PerformRouterDiscovery) Allow IRDP to detect and configure Default Gateway addresses (could lead to DoS)** su **Disabilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   0, 1, o 2. La configurazione predefinita è 2 (attivare solo se DHCP invia l'opzione PerformRouterDiscovery).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   0 (disabilitato)
  
-   1 (abilitato)
  
-   2 (abilitare solo se DHCP invia l'opzione PerformRouterDiscovery)
  
-   Non definito
  
##### Impatto potenziale
  
Disabilitando questa voce si impedisce a Windows Server 2003 (che supporta l'IRDP) di rilevare e configurare automaticamente gli indirizzi di gateway predefiniti sul computer.
  
#### SynAttackProtect livello di protezione Syn (protezione contro DoS)
  
Questa voce è presente come **MSS: (SynAttackProtect) Syn attack protection level (protects against DoS)** nell'interfaccia utente di SCE. Questa voce comporta l'adeguamento da parte del TCP della ritrasmissione di SYN-ACK. Configurando questa voce, si riduce il sovraccarico di trasmissioni incomplete in caso di attacco di tipo richiesta di connessione (SYN).
  
Questa voce può consentire di configurare Windows per l'invio di messaggi di scoperta router come broadcast e non multicast, come descritto in RFC 1256. Per impostazione predefinita, se la scoperta router è attivata, le richieste di scoperta router sono inviate al gruppo multicast di tutti i router (224.0.0.2).
  
##### Vulnerabilità
  
Nel caso di un attacco SYN flood, il pirata informatico invia un flusso costante di pacchetti SYN al server. Il server lascia parzialmente aperte le connessioni fino alla saturazione, rendendo impossibile la risposta alle richieste legittime.
  
##### Contromisura
  
Configurare la voce **MSS: (SynAttackProtect) Syn attack protection level (protects against DoS)** su **Connections time out sooner if a SYN attack is detected**.
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 1 (abilitato) per Windows Server 2003 SP1 e 0 (disabilitato) per Windows XP SP2.
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Connections time-out more quickly if a SYN attack is detected
  
-   No additional protection, use default settings
  
-   Non definito
  
##### Impatto potenziale
  
Questo valore aggiunge un ulteriore ritardo alle indicazioni della connessione, mentre le richieste di connessione TCP subiscono un rapido timeout quando è in corso un attacco SYN. Se si configura questa voce del Registro di sistema, le finestre scalabili e i parametri TCP configurati per ciascuna scheda, compresi RTT (Round Trip Time) iniziale e dimensioni della finestra, non funzioneranno più. Quando il computer è attaccato, le opzioni delle finestre scalabili (RFC 1323) e dei parametri TCP configurati per ciascuna scheda, RTT iniziale e dimensioni della finestra, su qualsiasi socket non saranno più abilitati. Queste opzioni non possono essere abilitate perché la protezione è attiva, la voce di cache route non è interrogata prima dell'invio del SYN-ACK e le opzioni Winsock non sono disponibili in questa fase di connessione.
  
#### (TCPMaxConnectResponseRetransmissions) ritrasmissione di SYN-ACK quando una richiesta di connessione non viene riconosciuta
  
Questa voce è presente come **MSS: (TcpMaxConnectResponseRetransmissions) SYN-ACK retransmissions when a connection request is not acknowledged** nell'interfaccia utente di SCE. Questa voce determina il numero di volte che TCP ritrasmette un SYN prima di annullare il tentativo. Il timeout di ritrasmissione viene raddoppiato a ogni ritrasmissione successiva in una determinata connessione. Il valore iniziale di timeout è tre secondi.
  
##### Vulnerabilità
  
Nel caso di un attacco SYN flood, il pirata informatico invia un flusso costante di pacchetti SYN al server. Il server lascia parzialmente aperte le connessioni fino alla saturazione, rendendo impossibile la risposta alle richieste legittime.
  
##### Contromisura
  
Configurare la voce **MSS: (TcpMaxConnectResponseRetransmissions) SYN-ACK retransmissions when a connection request is not acknowledged** su **3 seconds,** **half-open connections dropped after nine seconds**.
  
I possibili valori del Registro di sistema sono:
  
-   0-0xFFFFFFFF. La configurazione predefinita è 2.
  
Nell'interfaccia utente di SCE, viene visualizzato il seguente elenco di opzioni, corrispondenti rispettivamente a un valore di 0, 1, 2 e 3:
  
-   No retransmission, half-open connections dropped after 3 seconds
  
-   3 seconds, half-open connections dropped after 9 seconds
  
-   3 e 6 secondi, connessioni parziali interrotte dopo 21 secondi
  
-   3, 6 e 9 secondi, connessioni parziali interrotte dopo 45 secondi
  
-   Non definito
  
##### Impatto potenziale
  
Se questo valore è maggiore o uguale a **2**, lo stack impiega internamente la protezione SYN-ATTACK. Se il valore è minore di **2**, lo stack non legge alcun valore nel Registro di sistema per la protezione SYN-ATTACK. Con questa voce è possibile ridurre il periodo di tempo predefinito necessario per la pulitura di una connessione TCP parzialmente aperta. Un sito oggetto di un pesante attacco può ricorrere anche a valori molto bassi, fino a **1**. Anche **0** è un valore valido. Tuttavia, se il parametro viene impostato su **0**, non verrà più ritrasmesso alcun SYN-ACK e si verificherà un timeout dopo 3 secondi. Con valori così bassi, è possibile che le richieste di connessione legittime provenienti da client distanti non vengano accettate.
  
#### TcpMaxDataRetransmissions: How many times unacknowledged data is retransmitted (3 recommended, 5 is default)
  
Questa voce è presente come **MSS: (TcpMaxDataRetransmissions) How many times unacknowledged data is retransmitted (3 recommended,** **5 is default)** nell'interfaccia utente di SCE. Questa voce determina il numero di volte che TCP ritrasmette un singolo segmento di dati (non di connessione) prima di annullare la connessione. Il timeout di ritrasmissione viene raddoppiato a ogni ritrasmissione successiva in una determinata connessione. Viene reimpostato in caso di risposta. Il valore di timeout di base viene determinato dinamicamente dalla durata del percorso misurata nella connessione.
  
##### Vulnerabilità
  
Un utente malintenzionato potrebbe esaurire le risorse di un computer di destinazione se non sono mai stati inviati messaggi di riconoscimento dei dati trasmessi dal computer di destinazione.
  
##### Contromisura
  
Configurare la voce **MSS: (TcpMaxDataRetransmissions) How many times unacknowledged data is retransmitted (3 recommended;** **5 is default)** su **3.** I possibili valori del Registro di sistema sono:
  
-   Da 0 a 0xFFFFFFFF. La configurazione predefinita è 5.
  
Nell'interfaccia utente di SCE questa impostazione può essere modificata mediante una casella di testo:
  
-   Un numero definito dall'utente
  
-   Non definito
  
##### Impatto potenziale
  
Il TCP avvia un timer di ritrasmissione quando ciascun segmento in uscita viene passato all'IP. Se non viene ricevuto alcun riconoscimento per i dati di un determinato segmento prima della scadenza del timer, il segmento verrà ritrasmesso fino a tre volte.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Varie voci del Registro di sistema
  
Sono consigliate anche le voci del Registro di sistema riportate nella seguente tabella. Nelle sottosezioni che seguono la tabella sono fornite ulteriori informazioni su ciascuna voce, compresa la posizione di ogni impostazione della chiave del Registro di sistema.
  
**Tabella 10.2 Voci del Registro di sistema non relative a TCP/IP in Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Voce di registro</th>
<th style="border:1px solid black;" >Formato</th>
<th style="border:1px solid black;" >Valore di massima protezione (decimale)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">MSS: (AutoAdminLogon) Enable Automatic Logon (not recommended)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">Non definito, tranne per gli ambienti estremamente sicuri, che dovrebbero utilizzare 0.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (AutoReboot) Consente a Windows di effettuare il riavvio dopo un blocco di sistema (non consigliato per gli ambienti ad alta sicurezza)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">Non definito, tranne per gli ambienti estremamente sicuri, che dovrebbero utilizzare 0.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (AutoShareWks) Enable Administrative Shares (not recommended except for highly secure environments)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">Non definito, tranne per gli ambienti estremamente sicuri, che dovrebbero utilizzare 1.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (DisableSavePassword) Impedisce il salvataggio della password dial-up (consigliato)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (Hidden) Hide Computer From the Browse List (not recommended except for highly secure environments)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">Non definito, tranne per gli ambienti estremamente sicuri, che dovrebbero utilizzare 1.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering (recommended)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1 per i computer che eseguono Windows XP, 3 per i computer che eseguono Windows Server 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NoDriveTypeAutoRun) Disable Autorun for all drives (recommended)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0xFF</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers (Only recommended for servers)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames (recommended)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended)</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)</td>
<td style="border:1px solid black;">Stringa</td>
<td style="border:1px solid black;">0</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS: (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">0</td>
</tr>
</tbody>
</table>
  
#### Disattivare l'accesso automatico: disattivare l'accesso automatico
  
Questa voce è presente come **MSS: (AutoAdminLogon) Enable Automatic Logon (not recommended)** nell'interfaccia utente di SCE. Questa voce consente di stabilire se attivare o meno la funzione di accesso automatico (questa voce è separata dalla funzionalità della schermata Welcome in Windows XP; disabilitando tale funzionalità, non si verificheranno conseguenze sulla voce). Per impostazione predefinita, la voce non è abilitata. L'accesso automatico utilizza il dominio, il nome utente e la password memorizzati nel Registro di sistema, in modo da consentire l'accesso degli utenti al computer quando questo viene avviato. La finestra di dialogo di accesso non viene visualizzata.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Come attivare l'accesso automatico in Windows](http://support.microsoft.com/kb/315231/it)", all'indirizzo <http://support.microsoft.com/kb/315231/it>.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\**  
**CurrentVersion\\Winlogon\\**
  
.
  
##### Vulnerabilità
  
Se un computer è configurato in modo da effettuare l'accesso automatico, chiunque accede fisicamente al computer può inoltre avere accesso a tutti i dati memorizzati nel computer, comprese le reti a cui il computer è connesso. Inoltre, se l'accesso automatico viene attivato, la password non crittografata è memorizzata nel Registro di sistema. La chiave specifica del Registro di sistema che memorizza tale impostazione è leggibile in remoto dal gruppo **Authenticated Users**. Di conseguenza, questa voce è appropriata solo se il computer è protetto fisicamente e se si garantisce che gli utenti non attendibili non visualizzino in remoto il Registro di sistema.
  
##### Contromisura
  
Non configurare la voce **MSS: (AutoAdminLogon) Enable Automatic Logon (not recommended)** se non su computer ad elevato livello di protezione, in cui deve essere impostata su **Disabilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 0 (abilitato).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disattivato
  
-   Non definito
  
##### Impatto potenziale
  
Nessuno. Per impostazione predefinita questa voce non è abilitata.
  
#### Configura il riavvio automatico dopo un blocco del sistema
  
Questa voce è presente come **MSS: (AutoReboot) Allow Windows to automatically restart after a system crash (recommended except for highly secure environments)** nell'interfaccia utente di SCE. Determina se riavviare automaticamente o meno il computer dopo un blocco.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Control\\CrashControl\\**
  
.
  
##### Vulnerabilità
  
Esiste il problema che un computer possa rimanere bloccato in una sequenza infinita di operazioni non riuscite e di riavvii. Tuttavia, l'alternativa a questa voce non potrebbe essere più interessante, il computer smetterà semplicemente di funzionare.
  
##### Contromisura
  
Configurare la voce **MSS: (AutoReboot) Allow Windows to automatically restart after a system crash (recommended except for highly secure environments)** su **Disattivato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 1 (abilitata).
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Come configurare tecniche di ripristino in Windows XP](http://support.microsoft.com/kb/307973/it)" all'indirizzo <http://support.microsoft.com/kb/307973/it>.
  
Nella IU SCE, sono disponibili le seguenti opzioni:
  
-   Attivato
  
-   Disattivato
  
-   Non definito
  
##### Impatto potenziale
  
Il computer non verrà riavviato automaticamente dopo un errore di sistema.
  
#### Attiva le condivisioni amministrative
  
Questa voce è presente come **MSS: (AutoShareWks) Enable Administrative Shares (not recommended except for highly secure environments)** nell'interfaccia utente di SCE. Per impostazione predefinita, Windows XP Professional crea automaticamente condivisioni amministrative come ad esempio C$ e IPC$.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Creazione ed eliminazione di condivisioni nascoste o amministrative nei computer client](http://support.microsoft.com/kb/314984/it)" all'indirizzo <http://support.microsoft.com/kb/314984/it>.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\LanmanServer\\**  
**Parameters\\**
  
.
  
##### Vulnerabilità
  
Poiché queste condivisioni amministrative incorporate sono note e presenti nella maggior parte dei computer Windows, utenti malintenzionati le utilizzano spesso come obiettivi per attacchi di tipo "brute force", per poter determinare la password, ma anche per altri tipi di attacco.
  
##### Contromisura
  
Non configurare la voce **MSS: (AutoShareWks) Enable Administrative Shares (not recommended except for highly secure environments)** se non in computer ad elevato livello di protezione, dove deve essere impostata su **Attivato.**
  
I possibili valori del Registro di sistema sono:
  
?    1 o 0. La configurazione predefinita è 1 (abilitata).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
●    Attivato
  
●    Disattivato
  
●    Non Definito
  
##### Impatto potenziale
  
L'eliminazione di queste condivisioni può causare problemi agli amministratori e ai programmi o servizi che dipendono da queste condivisioni. Ad esempio, sia Microsoft Systems Management Server (SMS) sia Microsoft Operations Manager 2000 richiedono condivisioni amministrative per una corretta installazione e un funzionamento adeguato. Inoltre, molte utilità di backup di rete di terze parti richiedono condivisioni amministrative.
  
#### Disabilita salvataggio della password dial-up
  
Questa voce viene visualizzata come **MSS: (DisableSavePassword) Prevent the dial-up passsword from being saved (recommended)** nell'interfaccia utente di SCE. Determina se salvare o meno le password associate alla rubrica telefonica delle connessioni di rete. Se l'utente ha molte voci della rubrica del telefono, le password salvate accumulate possono causare un leggero ritardo dopo l'immissione delle credenziali dell'utente nella finestra di dialogo **Connessione a**.
  
È possibile aggiungere questo valore di registro al modello in
  
**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\**  
**Parameters\\**
  
.
  
##### Vulnerabilità
  
Un pirata informatico che ruba il computer di un utente mobile può connettersi automaticamente alla rete dell'organizzazione se la casella di controllo **Salva password** è abilitata per la voce dial-up.
  
##### Contromisura
  
Configurare la voce **MSS: (DisableSavePassword) Prevent the dial-up password from being saved (recommended)** su **Disattivato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 0 (abilitato).
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Disattivare l'opzione Registra password in Accesso remoto](http://support.microsoft.com/kb/172430/it)" all'indirizzo <http://support.microsoft.com/kb/172430/it>.
  
Nella IU SCE, sono disponibili le seguenti opzioni:
  
-   Attivato
  
-   Disattivato
  
-   Non definito
  
##### Impatto potenziale
  
Gli utenti non saranno in grado di memorizzare automaticamente le loro credenziali di accesso per connessioni VPN e remote.
  
#### Occultamento del computer dagli elenchi delle risorse di rete: nasconde il computer dagli elenchi
  
Questa voce è presente come **MSS: (Hidden) Hide Computer From the Browse List (not recommended except for highly secure environments)** nell'interfaccia utente di SCE. È possibile configurare un computer in modo da non inviare annunci ai browser sul dominio. In questo modo il computer viene nascosto dall'elenco e quindi non annuncia più la propria presenza agli altri computer nella stessa rete.
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Nascondere un computer con Windows 2000 dall'elenco di ricerca](http://support.microsoft.com/kb/321710/it)" all'indirizzo <http://support.microsoft.com/kb/321710/it>.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Lanmanserver\\**  
**Parameters\\**
  
.
  
##### Vulnerabilità
  
Un pirata informatico che conosce il nome di un computer può ottenere più facilmente maggiori informazioni sul computer. È possibile attivare questa voce per rimuovere un metodo che un pirata informatico potrebbe utilizzare per raccogliere le informazioni sui computer nella rete. Abilitando questa voce è inoltre possibile ridurre il traffico di rete. La vulnerabilità è tuttavia ridotta perché i pirati informatici possono utilizzare metodi alternativi per identificare e localizzare i potenziali obiettivi.
  
##### Contromisura
  
Non configurare la voce **MSS: (Hidden) Hide Computer From the Browse List (not recommended except for highly secure environments)** se non in computer ad elevato livello di protezione, dove deve essere impostata su **Abilitato.**
  
I possibili valori del Registro di sistema sono:
  
?    1 o 0. La configurazione predefinita è 0 (abilitato).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
●    Attivato
  
●    Disattivato
  
●    Non definito
  
##### Impatto potenziale
  
Il computer non sarà più presente negli elenchi delle risorse di rete sugli altri computer della stessa rete.
  
#### Enable IPSec to protect Kerberos RSVP Traffic: Enable NoDefaultExempt for IPSec Filtering
  
Questa voce è presente come **MSS: (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering (recommended)** nell'interfaccia utente di SCE. Le esenzioni predefinite ai filtri dei criteri IPsec sono descritte nella guida in linea di Microsoft Windows Server 2003 e Windows XP. Questi filtri consentono il funzionamento di IKE (Internet Key Exchange) e del protocollo di autenticazione Kerberos. I filtri consentono inoltre alla qualità del servizio (QoS) di rete di essere segnalata (RSVP) sia quando il traffico di dati è protetto da IPsec sia quando il traffico potrebbe non essere protetto da IPsec, come ad esempio il traffico multicast e broadcast.
  
Per ulteriori informazioni, vedere l'articolo pubblicato su TechNet dal titolo "[Specifying Default Exemptions to IPSec Filtering](http://technet.microsoft.com/en-us/library/cc756041.aspx)" (in inglese) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/DepKit/c9a7d986-5b9a-4e01-bb80-82d5e3a87d5c.mspx.](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/depkit/c9a7d986-5b9a-4e01-bb80-82d5e3a87d5c.mspx) Consultare inoltre l'articolo della Microsoft Knowledge Base "[È possibile utilizzare le esenzioni predefinite IPsec per eludere la protezione IPsec in alcuni scenari](http://support.microsoft.com/kb/811832/it)" all'indirizzo <http://support.microsoft.com/kb/811832/it>.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\IPSEC\\**
  
.
  
##### Vulnerabilità
  
L'utilizzo di IPsec è in aumento per il filtraggio di pacchetti host-firewall di base, specialmente negli scenari esposti a Internet e l'impatto di tali esenzioni predefinite non è stato completamente compreso. Di conseguenza, alcuni amministratori di IPsec possono creare i criteri IPsec che credono essere ad elevata protezione, ma che in realtà non lo sono contro gli attacchi informatici in ingresso che utilizzano le esenzioni predefinite. I pirati informatici potrebbero contraffare il traffico di rete che sembra essere formato da pacchetti legittimi del protocollo Kerberos, RSVP o IKE ma che invece li porterà ad altri servizi di rete dell'host.
  
##### Contromisura
  
Non configurare la voce **MSS: (NoDefaultExempt) Enable NoDefaultExempt for IPSec Filtering (recommended)** se non sui computer che utilizzano i filtri IPsec, dove deve essere impostata su **Attivato**.
  
I possibili valori del Registro di sistema sono:
  
-   In base alla configurazione predefinita di Windows 2000 e Windows XP, un valore 0 specifica che il traffico multicast, broadcast, RSVP, Kerberos e IKE (ISAKMP) sono esenti da filtri IPsec. Questa impostazione deve essere utilizzata solo se è necessaria la compatibilità con un criterio IPsec già esistente oppure con Windows 2000 e Windows XP.
  
-   Un valore 1 specifica che il protocollo Kerberos e il traffico RSVP non sono esenti da filtri IPsec, ma che sono esenti il traffico IKE, broadcast e multicast. Questa impostazione è il valore consigliato per Windows 2000 e Windows XP.
  
-   Un valore 2 specifica che il protocollo Kerberos e il traffico RSVP non sono esenti da filtri IPsec, ma che sono esenti il traffico IKE, broadcast e multicast. Questa impostazione è disponibile solo in Windows Server 2003.
  
-   Un valore 3 specifica che soltanto il traffico IKE è esente dai filtri IPsec. Questa impostazione è disponibile in Windows Server 2003, che contiene il comportamento predefinito anche se per impostazione predefinita la chiave di registro non è presente.
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   0
  
-   1
  
-   2
  
-   3
  
##### Impatto potenziale
  
Dopo aver abilitato questa voce, i criteri di protezione già presenti per poter funzionare correttamente potrebbero dover essere modificati. Per ulteriori dettagli, fare riferimento all'articolo della Microsoft Knowledge Base "[È possibile utilizzare le esenzioni predefinite IPsec per eludere la protezione IPsec in alcuni scenari](http://support.microsoft.com/kb/811832/it)" all'indirizzo <http://support.microsoft.com/kb/811832/it>, illustrato precedentemente in questa sezione.
  
#### Disable Autorun: Disable Autorun for all drives
  
Questa voce è presente come **MSS: (NoDriveTypeAutoRun) Disable Autorun for all drives (recommended)** nell'interfaccia utente di SCE. La funzionalità di esecuzione automatica inizia a leggere in un’unità del computer non appena si inserisce un supporto in essa. Di conseguenza, il file di installazione dei programmi e l'audio su supporti audio vengono avviati immediatamente.
  
Per disabilitare l'esecuzione automatica per tutte le unità, è possibile aggiungere questo valore del registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\**  
**Policies\\Explorer\\**
  
.
  
In alternativa, per disabilitare l'esecuzione automatica per le unità CD/DVD, è possibile aggiungere questo valore del registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Cdrom\\**
  
.
  
##### Vulnerabilità
  
Per impedire l'avvio di un eventuale programma dannoso quando viene inserito un supporto, i Criteri di gruppo disabilitano l'esecuzione automatica su tutte le unità.
  
Un pirata informatico che accede fisicamente al sistema potrebbe inserire un CD o un DVD con codice dannoso e il computer lo potrebbe eseguire automaticamente.
  
##### Contromisura
  
Configurare la voce **MSS: (NoDriveTypeAutoRun) Disable Autorun for all drives (recommended)** su **255,** **disable Autorun for all drives.**
  
I possibili valori del Registro di sistema sono:
  
-   Un intervallo di valori esadecimali
  
Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[La funzionalità di esecuzione o di riproduzione automatica non funziona quando si inserisce un CD nell'apposita unità](http://support.microsoft.com/kb/330135/it)" all'indirizzo <http://support.microsoft.com/kb/330135/it>.
  
Nella IU SCE, sono disponibili le seguenti opzioni:
  
-   Null, allow Autorun
  
-   255, disable Autorun for all drives
  
-   Non definito
  
##### Impatto potenziale
  
I CD con la funzionalità di esecuzione automatica attivata non vengono più eseguiti. Le utilità di masterizzazione CD potrebbero inoltre non funzionare correttamente poiché vi è la possibilità che i CD vuoti non vengano riconosciuti. Le applicazioni multimediali come Windows Media Player non saranno in grado di riconoscere i nuovi CD e DVD inseriti e gli utenti dovranno quindi avviarli manualmente.
  
#### Configurazione del rilascio dei nomi NetBIOS (NoNameReleaseOnDemand): consente al computer di ignorare le richieste di rilascio del nome NetBIOS eccetto per i server WINS
  
Questa voce è presente come **MSS: (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers (Only recommended for servers)** nell'interfaccia utente di SCE. NetBIOS su TCP/IP (NetBT) è un protocollo di rete che, fra l’altro, consente di risolvere facilmente i nomi NetBIOS registrati in computer basati su Windows negli indirizzi IP configurati in tali computer. Questo valore determina se il computer deve rilasciare il suo nome NetBIOS quando riceve una richiesta di rilascio di nome.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Netbt\\Parameters\\**
  
.
  
##### Vulnerabilità
  
Il protocollo NetBT non è progettato per utilizzare l'autenticazione e perciò è vulnerabile allo spoofing. Lo spoofing fa in modo che una trasmissione sembri provenire da un utente diverso rispetto all'utente che ha realmente eseguito l'azione. Un utente malintenzionato potrebbe sfruttare la natura non autenticata del protocollo per inviare a un computer un datagramma con nomi in conflitto obbligandolo a rinunciare al nome e a non rispondere alle query.
  
Un attacco del genere potrebbe provocare problemi di connessione intermittente sul computer preso di mira, o persino impedire l'utilizzo delle risorse di rete, degli accessi al dominio, del comando net send o ulteriori risoluzioni dei nomi NetBIOS.
  
Per ulteriori informazioni, consultare l'articolo della Microsoft Knowledge Base "[Un problema di protezione a livello di NetBIOS può causare conflitti di nomi duplicati sulla rete](http://support.microsoft.com/kb/269239/it)" all'indirizzo <http://support.microsoft.com/kb/269239/it>.
  
##### Contromisura
  
Configurare la voce **MSS: (NoNameReleaseOnDemand) Allow the computer to ignore NetBIOS name release requests except from WINS servers (Only recommended for servers)** su **Abilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 1 (abilitato).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disabilitato
  
-   Non definito
  
In alternativa, è possibile disabilitare l'utilizzo di WINS nell'ambiente e controllare che tutte le applicazioni utilizzino il DNS per i servizi di risoluzione dei nomi. Questa è una strategia da adottare a lungo termine; per molte organizzazioni non è pratico adottarla come soluzione a breve termine. Le organizzazioni che eseguono ancora WINS di solito hanno dipendenze dell'applicazione che non possono essere risolte rapidamente senza aggiornamenti e distribuzioni di software, operazioni che richiedono un'attenta pianificazione e un impegno significativo in termini di tempo.
  
Se non si è in grado di distribuire questa contromisura e si desidera garantire la risoluzione dei nomi NetBIOS, è necessario "pre-caricare" in nomi NetBIOS nel file LMHOSTS su alcuni computer. Per ulteriori informazioni sulla pre-carica del file LMHOSTS, consultare l'articolo della Microsoft Knowledge Base "Un problema di protezione a livello di NetBIOS può causare conflitti di nomi duplicati sulla rete" illustrato precedentemente in questa sezione.
  
**Nota**: la manutenzione del file LMHOSTS nella maggior parte degli ambienti richiede molto lavoro. Microsoft consiglia l'utilizzo di WINS a quello di LMHOSTS.
  
##### Impatto potenziale
  
Un pirata informatico, inviando una richiesta attraverso la rete, potrebbe chiedere a un computer di rilasciare il nome NetBIOS. Come per tutte le modifiche che influiscono sulle applicazioni, Microsoft consiglia di testare questa modifica in un ambiente non produttivo prima di renderla effettiva in un ambiente produttivo.
  
#### Disabilitazione della creazione automatica di nomi file in formato 8.3: consente al computer di bloccare la creazione di nomi file in formato 8.3
  
Questa voce è presente come **MSS: (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames (recommended)** nell'interfaccia utente di SCE. Windows Server 2003 supporta i nomi di file 8.3 per garantire la compatibilità con le applicazioni a 16 bit (il formato di denominazione 8.3 consente di assegnare a un file un nome lungo al massimo otto caratteri).
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Control\\FileSystem\\**
  
.
  
##### Vulnerabilità
  
Consentendo il formato di denominazione dei file 8.3, un pirata informatico può utilizzare solo otto caratteri per fare riferimento al nome di un file che potrebbe essere lungo 20 caratteri. Ad esempio, un file denominato questofilehaunnomelungo.doc, può essere individuato usando il nome file in formato 8.3, ovvero questo~1.doc. Se non si utilizzano applicazioni a 16 bit, è possibile disattivare questa funzionalità. Disabilitando la creazione di nomi brevi su una partizione NTFS si aumentano anche le prestazioni di enumerazione delle directory.
  
I pirati informatici potrebbero utilizzare i nomi di file brevi per accedere a file di dati e applicazioni con nomi di file lunghi altrimenti difficili da individuare. Se un pirata informatico riesce ad accedere al file system può accedere ai dati o eseguire applicazioni.
  
##### Contromisura
  
Configurare la voce **MSS: (NtfsDisable8dot3NameCreation) Enable the computer to stop generating 8.3 style filenames (recommended)** su **Abilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita è 0 (abilitato).
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disabilitato
  
-   Non definito
  
##### Impatto potenziale
  
Le applicazioni a 16 bit dell'organizzazione non saranno in grado di accedere ai file i cui nomi non hanno il formato 8.3. Alcune applicazioni a 32 bit fanno affidamento sulla presenza di nomi brevi, in quanto questi non contengono spazi incorporati e non devono essere racchiusi tra virgolette quando vengono utilizzati nelle righe di comando. Le routine di installazione potrebbero non funzionare in alcuni programmi, in quanto quelli progettati per essere eseguiti in architetture CPU potrebbero essere applicazioni a 16 bit. Abilitando questa voce, l'installazione di Exchange 2000 SP2 non sarà eseguita. Se questa voce è abilitata e il percorso della variabile di sistema %temp% comprende uno spazio, l'installazione dei service pack per SQL 2000 non sarà eseguita. Una soluzione semplice per questo problema è quella di definire nuovamente la variabile con un percorso privo di spazi (ad esempio C:\\temp).
  
**Nota**: se si applica questa voce a un server che contiene già file con nomi file creati automaticamente in formato 8.3, questi non vengono rimossi. Per rimuovere i nomi di file esistenti in formato 8.3, è necessario copiarli su altri supporti, eliminarli dalla posizione originale e, successivamente, ricopiarveli.
  
#### Abilitazione dell'ordine di ricerca Safe DLL: abilita l'ordine di ricerca Safe DLL: (consigliato)
  
Questa voce è presente come **MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended)** nell'interfaccia utente di SCE. È possibile configurare la ricerca delle DLL (Dynamic Link Library) richieste dai processi in esecuzione in due modi:
  
Se SafeDllSearchMode è configurato su 1, l'ordine di ricerca è il seguente:
  
-   La directory di caricamento dell'applicazione.
  
-   La directory di sistema.
  
-   La directory di sistema a 16 bit. Nessuna funzione è in grado di ottenere il percorso di questa directory, anche se la ricerca viene comunque eseguita.
  
-   La directory di Windows.
  
-   La directory corrente.
  
-   Le directory che sono elencate nella variabile di ambiente di PATH.
  
Se SafeDllSearchMode è configurato su 0, l'ordine di ricerca è il seguente:
  
-   La directory di caricamento dell'applicazione.
  
-   La directory corrente.
  
-   La directory di sistema.
  
-   La directory di sistema a 16 bit. Nessuna funzione è in grado di ottenere il percorso di questa directory, anche se la ricerca viene comunque eseguita.
  
-   La directory di Windows.
  
-   Le directory che sono elencate nella variabile di ambiente di PATH.
  
È possibile aggiungere questo valore di registro al file di modello in
  
**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\**
  
.
  
##### Vulnerabilità
  
Se un utente esegue inavvertitamente del codice dannoso confezionato con file aggiuntivi contenenti versioni modificate delle DLL del sistema, queste potrebbero essere caricate aumentando così il tipo e la serietà del danno.
  
##### Contromisura
  
Configurare la voce **MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended)** su **Abilitato.**
  
I possibili valori del Registro di sistema sono:
  
-   1 o 0. La configurazione predefinita per Windows XP  è 0, mentre è 1 per Windows Server 2003.
  
Nell'interfaccia utente di SCE vengono visualizzate le seguenti opzioni:
  
-   Attivato
  
-   Disabilitato
  
-   Non definito
  
##### Impatto potenziale
  
Le applicazioni saranno costrette a cercare le DLL prima nel percorso di sistema. Ciò potrebbe causare problemi di stabilità o di prestazioni alle applicazioni che richiedono le versioni univoche delle DLL incluse nei programmi.
  
#### Protezione da password immediata dello screen saver: tempo in secondi prima della scadenza del periodo di prova dello screen saver (consigliato: 0)
  
Questa voce è presente come **MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)** nell'interfaccia utente di SCE. Se è impostato il blocco dello screen saver, tra l’avvio dello screen saver e il blocco automatico effettivo della console intercorre un periodo di tempo.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\**  
**Winlogon\\**
  
.
  
##### Vulnerabilità
  
Il periodo di prova predefinito consentito prima che il blocco dello screen saver abbia effetto è di cinque secondi. Lasciando invariata l'impostazione predefinita del periodo di prova il computer risulta vulnerabile a un potenziale attacco da parte di qualcuno fisicamente vicino alla console che tenta di accedere al computer prima che il blocco abbia effetto. Per regolare la durata del periodo di prova è possibile inserire una voce nel Registro di sistema.
  
##### Contromisura
  
Configurare la voce **MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)** su **0.**
  
I possibili valori del Registro di sistema sono:
  
-   da 0 a 255. Il valore predefinito è di 5 secondi.
  
Nell'interfaccia utente di SCE per questa voce viene visualizzata una casella di testo:
  
-   Un numero definito dall'utente
  
-   Non definito
  
##### Impatto potenziale
  
Quando si attiva lo screen saver per riavviare le sessioni della console gli utenti dovranno inserire la password.
  
#### Messaggio di avviso per il raggiungimento del limite massimo nel registro di protezione: limite in percentuale del registro eventi di protezione raggiunto il quale viene creato un messaggio di avviso
  
Questa voce è presente come **MSS: (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning** nell'interfaccia utente di SCE. Questa opzione è stata introdotta con Windows Server 2003 e il Service Pack 3 di Windows 2000 e consente di generare un controllo della protezione nel registro eventi di protezione quando raggiunge la soglia definita dall'utente. Se, ad esempio, questo valore è impostato su 90, quando viene raggiunto il 90 percento della capacità del registro viene registrata una voce per l’ID evento 523 con il seguente testo:
  
The security event log is 90 percent full.
  
**Nota**: questa impostazione non ha effetto se il Registro eventi di protezione è configurato per sovrascrivere gli eventi quando è necessario.
  
È possibile aggiungere questo valore di registro al file di modello nella sottochiave
  
**HKEY\_LOCAL\_MACHINE\\ SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Security\\**
  
.
  
##### Vulnerabilità
  
Se il registro di protezione ha raggiunto il 90 percento della capacità e il computer non è stato configurato per sovrascrivere gli eventi quando è necessario, gli eventi più recenti non vengono registrati. Se il registro è pieno e il computer è stato configurato per effettuare l'arresto quando non è più possibile registrare gli eventi nel registro di protezione, il computer si arresta e non è più possibile fornire i servizi di rete.
  
##### Contromisura
  
Impostare la voce **MSS: (WarningLevel) Percentage threshold for the security event log at which the system will generate a warning** su **90**.
  
I possibili valori del Registro di sistema sono:
  
-   da 0 a 100. La configurazione predefinita è 0 (non viene creato nessun avviso).
  
Nella IU SCE, sono disponibili le seguenti opzioni:
  
-   50%
  
-   60%
  
-   70%
  
-   80%
  
-   90%
  
-   Non definito
  
##### Impatto potenziale
  
Questa impostazione consente di generare un evento di controllo quando il registro di protezione raggiunge la soglia di riempimento del 90 percento a meno che il registro non sia configurato per sovrascrivere gli eventi se necessario.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Voci di registro disponibili in Windows XP con SP2 e Windows Server 2003 con SP1
  
Le voci di registro descritte in precedenza in questo capitolo vengono applicate a Microsoft Windows XP con SP1 e Windows Server 2003.
  
La versione di Windows XP SP2 e di Windows Server 2003 SP1 ha fornito ulteriori voci di registro relative alla protezione che possono essere configurate per soddisfare i requisiti di protezione specifici dell'ambiente.
  
Le voci di registro riportate di seguito sono presenti in Windows Server 2003 con SP1 e in Windows XP con SP2.
  
#### RestrictRemoteClients
  
Quando un'interfaccia è registrata tramite RpcServerRegisterIf, RPC consente a limitare l'accesso all'interfaccia da parte dell'applicazione server, normalmente attraverso una richiamata di sicurezza. La chiave di registro **RestrictRemoteClients** impone a RPC l'esecuzione di controlli di protezione su tutte le interfacce, anche se l'interfaccia non dispone di richiamata di sicurezza registrata. I client RPC che utilizzano la sequenza del protocollo named pipe (ncacn\_np) non sono soggetti a queste restrizioni. La sequenza del protocollo named pipe non può essere limitata, a causa di numerosi problemi di compatibilità con le versioni precedenti.
  
La chiave di registro **RestrictRemoteClients** può avere uno dei tre valori DWORD:
  
-   **0**. È il valore predefinito in Windows Server 2003 con SP1, e consente al computer di ignorare la restrizione di interfaccia RPC. L'imposizione di restrizioni RPC appropriate compete esclusivamente all'applicazione server. Questa configurazione equivale alla configurazione delle versioni precedenti di Windows.
  
-   **1.** È il valore predefinito in Windows XP con SP2. Il runtime RPC rifiuta tutte le chiamate anonime remote ad eccezione delle chiamate provenienti da named pipe (ncacn\_np).
  
-   **2.** Il runtime RPC rifiuta tutte le chiamate anonime remote, senza alcuna eccezione. Questa configurazione non consente al computer di ricevere chiamate anonime remote mediante RPC.
  
Gli sviluppatori possono modificare le loro applicazioni in modo da passare i flag al sottosistema RPC che indica se il client o il server accetteranno le richieste RPC anonime.
  
##### Vulnerabilità
  
Le interfacce RPC che consentono la connessione non autenticata possono essere utilizzate in modalità remota per sfruttare il sovraccarico del buffer e il diffondersi di codice dannoso.
  
##### Contromisura
  
La configurazione predefinita del valore **RestrictRemoteClients** in Windows Server 2003 con SP1 e Windows XP con SP2 consente la compatibilità con le versioni precedenti. Per aumentare la protezione contro i worm che potrebbero tentare di sfruttare in remoto gli overflow del buffer nei servizi RPC, configurare **RestrictRemoteClients** su **1** o **2.**
  
##### Impatto potenziale
  
Abilitando la chiave di registro **RestrictRemoteClients**, l'interfaccia di mapping degli endpoint RPC non sarà accessibile in modo anonimo. Questa restrizione è un miglioramento di protezione significativo, ma modifica la risoluzione degli endpoint. Attualmente, un client RPC che tenta di effettuare una chiamata utilizzando un endpoint dinamico interroga prima il mapping degli endpoint RPC sul server per determinare l'endpoint al quale connettersi. Questa query è effettuata in modo anonimo, anche se la chiamata del client RPC utilizza la protezione RPC. Le chiamate anonime all'interfaccia di mapping degli endpoint RPC non saranno eseguite su Windows Server 2003 con SP1 se la chiave **RestrictRemoteClients** è impostata su 1 o superiore. Il runtime del client RPC deve, pertanto, essere modificato per eseguire una query non autenticata dall'agente di mapping degli endpoint. Se è impostata la chiave **EnableAuthEpResolution**, il runtime del client RPC utilizzerà NTLM per autenticare il mapping degli endpoint. Questa query autenticata viene inviata solo se la chiamata del client RPC utilizza l'autenticazione RPC.
  
Quando la chiave è abilitata, alcune applicazioni e servizi potrebbero non funzionare correttamente. Quindi è essenziale testarla accuratamente prima di distribuirla nell'ambiente. Se si sta per attivare questa chiave, è necessario utilizzare inoltre la chiave **EnableAuthEpResolution** in modo da abilitare l'autenticazione per il mapping degli endpoint RPC.
  
#### EnableAuthEpResolution
  
Le chiamate anonime all'interfaccia del mapping degli endpoint RPC non saranno eseguite per impostazione predefinita su Windows XP con SP2, a causa del valore predefinito della nuova chiave **RestrictRemoteClients**. Il runtime del client RPC deve, pertanto, essere modificato per eseguire una query non autenticata dall'agente di mapping degli endpoint. A questo fine, configurare la chiave **EnableAuthEpResolution** su 1. Se l'impostazione è configurata, il runtime del client RPC utilizzerà NTLM per autenticare il mapping degli endpoint. Questa query autenticata viene inviata solo se la chiamata del client RPC utilizza l'autenticazione RPC.
  
##### Vulnerabilità
  
Le interfacce RPC che consentono la connessione non autenticata possono essere utilizzate in modalità remota per sfruttare il sovraccarico del buffer e il diffondersi di codice dannoso.
  
##### Contromisura
  
Per aumentare la protezione contro i worm che potrebbero sfruttare in remoto gli overflow del buffer nei servizi RPC, configurare **RestrictRemoteClients** secondo la procedura descritta nella sezione precedente, quindi utilizzare **EnableAuthEpResolution** in modo da abilitare l'autenticazione NTLM per le richieste del computer RPC.
  
##### Impatto potenziale
  
I clienti che non dispongono del set di chiavi **EnableAuthEpResolution** non saranno in grado di effettuare le richieste di servizio RPC dei server in cui **RestrictRemoteClients** è abilitata. Questa restrizione può causare l'arresto dei servizi basati su RPC.
  
#### RunInvalidSignatures
  
Per impostazione predefinita, Windows Server 2003 con SP1 e Windows XP con SP2 impedisce l'installazione di oggetti con codice firmato che dispongono di firme non valide. Queste firme potrebbero non essere valide, perché il codice è stato modificato oppure perché il certificato di firma è scaduto o è presente in un elenco delle revoche dei certificati (CRL, Certificate Revocation List). Internet Explorer 6.0 ha già bloccato l'installazione di codice con firme non valide, ma il service pack estende questo comportamento a tutte le applicazioni.
  
##### Vulnerabilità
  
Un controllo firmato Microsoft ActiveX che è stato manomesso potrebbe essere scaricato ed eseguito da un'applicazione, rischiando di compromettere il computer.
  
##### Contromisura
  
Il valore predefinito di **RunInvalidSignatures** blocca questa vulnerabilità.
  
##### Impatto potenziale
  
Le applicazioni che dipendono da controlli legittimi firmati non funzioneranno se le loro firme per un qualsiasi motivo sono ritenute non valide. In un'applicazione la cui firma non è valida, è possibile modificare la configurazione della chiave per consentire il download e l'esecuzione del controllo. Questo procedimento potrebbe tuttavia creare una vulnerabilità nella protezione. È preferibile contattare gli sviluppatori del controllo utilizzato nell'applicazione in modo da ottenere una versione con una firma valida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Voci di registro disponibili in Windows XP con SP2
  
Le voci di registro riportate di seguito sono presenti solamente in Windows XP con SP2.
  
#### Voci di registro del Centro sicurezza PC per XP
  
I valori del registro per il Centro sicurezza PC, che stabiliscono la ricezione o meno di avvisi da parte dell'utente per una determinata funzione, sono tre. Se una chiave ha valore 0 o è inesistente, vengono abilitati l'icona di notifica e il sistema di avviso per quella funzionalità. Se esiste un valore diverso da 0, l'icona di notifica e il sistema di avviso della funzione è disattivato.
  
Tutti e tre i valori sono collocati in **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\**  
**Security Center**. I valori sono:
  
-   **AntiVirusDisableNotify**
  
-   **FirewallDisableNotify**
  
-   **UpdatesDisableNotify**
  
##### Vulnerabilità
  
Gli utenti che disattivano le funzioni di avviso del Centro sicurezza PC potrebbero non ricevere avvisi corretti se l'antivirus, il firewall o i servizi di aggiornamento automatico installati sui loro computer per qualche motivo non funzionano adeguatamente.
  
##### Contromisura
  
Per imporre all'ambiente una configurazione di avviso appropriata, è necessario applicare una voce di registro Criteri di gruppo.
  
##### Impatto potenziale
  
Questi valori di registro sono visibili nell'interfaccia utente del Centro sicurezza PC se è attivata la funzionalità Centro sicurezza PC. Gli utenti con accesso al livello di amministratore locale potranno modificare i valori del Centro sicurezza PC.
  
#### StorageDevicePolicies\\WriteProtect
  
Per impostazione predefinita, gli utenti possono installare le periferiche di archiviazione USB sui loro computer Windows XP e leggere da o scrivere in queste periferiche senza alcuna restrizione. In SP2, Microsoft ha aggiunto la possibilità per gli amministratori di imporre agli utenti restrizioni di scrittura verso periferiche di archiviazione a blocchi USB.
  
Per imporre agli utenti restrizioni di scrittura è possibile aggiungere il valore **WriteProtect** DWORD a **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\StorageDevicePolicies** impostato su **1.** Quando questo valore è configurato, il driver di Windows per le periferiche di archiviazione a blocchi USB rifiuterà le richieste di scrittura verso le periferiche installate.
  
##### Vulnerabilità
  
Un pirata informatico potrebbe copiare i dati in una periferica USB rimovibile e rubarli.
  
##### Contromisura
  
Quando il valore **WriteProtect** è 1, Windows XP con SP2 bloccherà le operazioni di scrittura sulle periferiche di archiviazione a blocchi USB installate.
  
##### Impatto potenziale
  
Questa chiave di registro consente di attenuare in parte un pericolo molto serio. Esistono tuttavia molti altri modi in cui un abile pirata informatico potrebbe rubare i dati utilizzando una periferica USB. Ad esempio, una periferica USB può essere programmata per essere enumerata come periferica di archiviazione non a blocchi (come una stampante o una periferica CD-ROM) e non dovrà quindi superare questo controllo. Le organizzazioni che desiderano prevenire il furto di dati riservati da parte di utenti o pirati informatici, insieme ai controlli di accesso fisico e ad altre misure di restrizione di accesso a periferiche di scrittura USB, possono utilizzare questa voce come parte di una strategia di protezione più ampia.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Voci di registro disponibili in Windows Server 2003 con SP1
  
Le voci di registro riportate di seguito sono presenti solamente in Windows Server 2003 with SP1.
  
#### UseBasicAuth
  
DAV (Distributed Authoring and Versioning) è un protocollo basato su HTTP che consente l'accesso remoto ai file system e ai file server. Per accedere alle risorse sui server DAV, gli utenti possono utilizzare percorsi UNC. Tuttavia, il redirector WebDAV in Windows Server 2003 comunica con i server Web che supportano DAV mediante HTTP e non può utilizzare sessioni HTTP protette SSL. Quando questi siti Web consentono di utilizzare l'autenticazione base, le richieste DAV trasmetteranno le credenziali di autenticazione dell'utente non crittografate.
  
In Windows Server 2003 con SP1, il redirector WebDAV è stato modificato per non inviare mai le credenziali utente con l'autenticazione di base. Questa modifica può influenzare le applicazioni o i processi aziendali che dipendono dal redirector DAV predefinito del computer (Microsoft Office utilizza il proprio client DAV indipendente e non è influenzato da questa voce).
  
Windows Server 2003 SP1 introduce la sottochiave **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WebClient\\**  
**Parameters\\UseBasicAuth**. Se il suo valore è 1, il redirector WebDAV del computer può comunicare con i server Web che supportano soltanto l'autenticazione di base.
  
##### Vulnerabilità
  
Un pirata informatico potrebbe creare un server Web che utilizza autenticazioni di base, quindi indurre gli utenti a tentare di collegarsi con un inganno e così acquisirne le credenziali.
  
##### Contromisura
  
Per impostazione predefinita, il redirector WebDAV di Windows Server 2003 non utilizzerà l'autenticazione di base, che blocca efficacemente questa vulnerabilità.
  
##### Impatto potenziale
  
Le applicazioni che per accedere alle risorse Web utilizzano il redirector WebDAV incorporato non potranno essere eseguite se il server Web supporta solamente l'autenticazione di base. Per risolvere questo problema, è possibile configurare il server Web in modo che possa supportare ulteriori metodi di autenticazione protetta o attivare il valore **UseBasicAuth.** Tuttavia, il meccanismo consigliato è quello di configurare nuovamente il server Web, non consentendo l'esposizione delle credenziali degli utenti.
  
#### DisableBasicOverClearChannel
  
Il redirector WebDAV fa parte dello stack del file system remoto. Quando gli utenti tentano di aprire gli URL su computer remoti, se il server remoto supporta l'autenticazione di base le loro credenziali possono essere esposte. Un pirata informatico può essere in grado di ingannare un utente e di dirigerlo verso un sito Web che richiede credenziali (tramite DAV) e utilizza l'autenticazione di base. Se l'utente risponde, le sue credenziali verrebbero esposte su un host non attendibile.
  
La voce di registro **UseBasicAuth** controlla se l'autenticazione di base può essere utilizzata per le richieste WebDAV. Configurando il valore **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WebClient\\**  
**Parameters\\ DisableBasicOverClearChannel** su 1, viene bloccato l'utilizzo dell'autenticazione di base con le altre risorse Web.
  
##### Vulnerabilità
  
Un pirata informatico potrebbe creare un server Web che utilizza autenticazioni di base, quindi indurre gli utenti a tentare di collegarsi con un inganno e così acquisirne le credenziali.
  
##### Contromisura
  
Configurare il valore **DisableBasicOverClearChannel** su 1 nei computer client, in modo da limitare la possibilità di connettersi a server HTTP mediante l'utilizzo dell'autenticazione di base.
  
##### Impatto potenziale
  
Molte periferiche incorporate (come i router, i server di stampa, e i dispositivi di copia) che forniscono l'accesso HTTP, come alcune applicazioni aziendali, supportano esclusivamente l'autenticazione di base. Configurando **DisableBasicOverClearChannel** su 1, i computer client non saranno in grado di effettuare l'autenticazione su queste periferiche o applicazioni.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni su alcune delle voci trattate in questo capitolo:
  
-   Per informazioni dettagliate sul caricamento di DLL in Windows e su come le DLL vengono influenzate dalla voce SafeDllSearchMode, consultare "[Dynamic-Link Library Search Order](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dllproc/base/dynamic-link_library_search_order.asp)" (in inglese) all'indirizzo [http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dllproc/base/dynamic-link\_library\_search\_order.asp.](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dllproc/base/dynamic-link_library_search_order.asp)
  
-   Per ulteriori informazioni sulla configurazione delle voci per la disabilitazione dei driver della periferica di input/output (I/O) di Microsoft, consultare l'articolo della Microsoft Knowledge Base "[Come utilizzare i Criteri di gruppo per disabilitare i driver USB, CD-ROM, floppy disk e LS-120](http://support.microsoft.com/kb/555324/it)" all'indirizzo <http://support.microsoft.com/kb/555324/it>.
  
-   Per ulteriori informazioni sull'architettura di base per la creazione, la modifica e l'esecuzione dei modelli di protezione, consultare "[How Security Settings Extension Works](http://technet.microsoft.com/en-us/library/cc785052.aspx)" (in inglese) all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/TechRef/f546e58e-8473-4985-a05d-0b038dea4a9f.mspx.](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/techref/f546e58e-8473-4985-a05d-0b038dea4a9f.mspx) L'articolo contiene informazioni dettagliate sull'archiviazione dei Criteri di gruppo, sulle precedenze e su come alcune impostazioni persistono anche quando un particolare Criterio di gruppo non viene più applicato a un computer, spesso definito come "contrassegno permanente".
  
-   Per ulteriori informazioni su come personalizzare l'interfaccia utente dell'Editor di configurazione della protezione, consultare l'articolo della Microsoft Knowledge Base "[Come aggiungere le impostazioni di Registro di sistema personalizzato a Editor di configurazione della protezione](http://support.microsoft.com/kb/214752/it)" all'indirizzo <http://support.microsoft.com/kb/214752/it>.
  
-   Per ulteriori informazioni sugli attacchi di rete più diffusi, vedere "[Common Types of Network Attacks](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/cnet/cndb_ips_ddui.mspx?mfr=true)", estratto da *Windows*  *2000 Server Resource Kit*, disponibile in linea all'indirizzo:[http://www.microsoft.com/resources/documentation/Windows/2000/server/reskit/en-us/cnet/cndb\_ips\_ddui.asp.](http://www.microsoft.com/resources/documentation/windows/2000/server/reskit/en-us/cnet/cnbd_trb_gdhe.asp)
  
-   Per ulteriori informazioni su come irrobustire lo stack TCP/IP di Windows Server 2003, consultare l'articolo della Microsoft Knowledge Base "[Rendere più forte lo stack TCP/IP rispetto ad attacchi di tipo "denial of service" in Windows Server 2003](http://support.microsoft.com/kb/324270/it)" all'indirizzo [http://support.microsoft.com/kb/324270/it.](http://support.microsoft.com/kb/324270/it)
  
**Download**
  
[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti e suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)
  
[](#mainsection)[Inizio pagina](#mainsection)
