---
TOCTitle: 'Distribuzione di reti 802.11 protette che utilizzano Microsoft Windows'
Title: 'Distribuzione di reti 802.11 protette che utilizzano Microsoft Windows'
ms:assetid: 'AFA3BBA5-BF62-294F-8114-DF1B20179FD3'
ms:contentKeyID: 20577390
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Bb457097(v=TechNet.10)'
---

Distribuzione di reti 802.11 protette che utilizzano Microsoft Windows
======================================================================

Aggiornato: 12 dicembre 2006

**Sommario**

In questo articolo si descrive come distribuire un accesso wireless IEEE 802.11 protetto nelle organizzazioni di medie e grandi dimensioni con autenticazione IEEE 802.1X, utilizzando punti di accesso wireless, computer client wireless Microsoft® Windows® XP e Windows Server® 2003 e un'infrastruttura di autenticazione wireless che comprende i controller di dominio del servizio directory Active Directory®, le autorità di certificazione e i server IAS (Internet Authentication Service), basati su Windows Server 2003 o Windows 2000 Server.

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Procedura di distribuzione wireless Intranet](#eeaa)
[](#edaa)[Configurazioni aggiuntive di distribuzione wireless Intranet](#edaa)
[](#ecaa)[Appendice A Utilizzare soltanto l'autenticazione del computer](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Collegamenti correlati](#eaaa)

### Introduzione

In questo articolo si descrive come creare una infrastruttura per l'autenticazione, l'autorizzazione e l'accounting di connessioni wireless protette in una organizzazione che utilizza computer client wireless Windows. Questa è la configurazione tipica per un'organizzazione che utilizza:

-   Computer client wireless in cui è in esecuzione Windows XP o Windows Server 2003.

    Windows XP e Windows Server 2003 hanno il supporto incorporato per l'accesso wireless IEEE 802.11 e l'autenticazione IEEE 802.1X utilizzando il protocollo Extensible Authentication Protocol (EAP). Windows 2000 supporta l'autenticazione IEEE 802.1X quando Windows 2000 Service Pack 4 (SP4) è installato.

-   Almeno due server IAS.

    Almeno due server IAS (uno primario e uno secondario) sono utilizzati per fornire la tolleranza di errore per l'autenticazione basata su RADIUS (Remote Authentication Dial-In User Service). Se è configurato un solo server RADIUS, in caso di momentanea non disponibilità di questo server i computer client con accesso wireless non possono connettersi. Se si utilizzano due server IAS e si configurano tutti i punti di accesso wireless (AP) o gli switch (computer client RADIUS) per i server IAS primario e secondario, i computer client RADIUS saranno in grado di rilevare se il server RADIUS primario non è disponibile e passare automaticamente al server IAS secondario.

    È possibile utilizzare IAS sia in Windows Server 2003 sia in Windows 2000 Server. Nei server IAS in cui è in esecuzione Windows 2000 deve essere installato Windows 2000 SP4. IAS non è incluso in Windows Server 2003, Web Edition.

-   Domini Active Directory.

    I domini Active Directory contengono gli account utente, gli account computer e le proprietà delle chiamate in ingresso richieste da ogni server IAS per autenticare le credenziali e valutare l'autorizzazione. Sebbene non sia un requisito, sia per ottimizzare i tempi di risposta delle autenticazioni e autorizzazioni IAS sia per minimizzare il traffico di rete, IAS deve essere installato su controller di dominio Active Directory. È possibile utilizzare sia i controller di dominio Windows Server 2003 sia quelli Windows 2000 Server. Nei controller di dominio Windows 2000 deve essere installato Windows 2000 SP4.

-   Certificati del computer installati sui server IAS.  

    Indipendentemente dal metodo di autenticazione wireless utilizzato, occorre installare i certificati di computer sui server IAS.

-   Per l'autenticazione EAP-TLS, un'infrastruttura di certificazione.

    Quando si usa il protocollo di autenticazione Extensible Authentication Protocol-Transport Layer Security (EAP-TLS) con il computer e con i certificati utente sui computer client wireless, per emettere i certificati è necessaria un'infrastruttura di certificazione, nota anche come infrastruttura a chiave pubblica (PKI).

-   Per l'autenticazione Protected EAP (PEAP) con Microsoft Challenge Handshake Authentication Protocol versione 2 (MS-CHAP v2), l'autorità di certificazione radice certifica ogni computer client wireless.

    PEAP-MS-CHAP v2 è un metodo di autenticazione protetta basato su password per le connessioni wireless. A seconda dell'autorità di emissione dei certificati di computer del server IAS, può darsi si debba installare anche i certificati di autorità di certificazione radice su ogni computer client wireless.

-   Criteri di accesso remoto wireless.

    Un criterio di accesso remoto è configurato per le connessioni wireless in modo che gli utenti possano accedere alla Intranet dell'organizzazione.

-   Punti di accesso wireless multipli.

    I punti di accesso wireless multipli di terze parti forniscono l'accesso wireless in differenti edifici di una organizzazione. I punti di accesso wireless devono supportare gli standard IEEE 802.1X, RADIUS e Wi-Fi Protected Access (WPA™) oppure Wi-Fi Protected Access 2 (WPA2™). Si raccomanda di utilizzare lo standard Wired Equivalent Privacy (WEP) soltanto temporaneamente durante le transizioni a WPA o WPA2.

Nella figura 1 viene mostrata una tipica configurazione wireless per un'organizzazione che utilizza l'autenticazione 802.1X.

![](images/Bb457097.ed802101(it-it,TechNet.10).gif)

**Figura 1   Configurazione wireless quando si utilizza l'autenticazione 802.1X.**

Per informazioni di background su tecnologie, componenti e processi di autenticazione protetta wireless, vedere [Cenni preliminari di tecnologia e componenti della distribuzione wireless](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wificomp.mspx).

[](#mainsection)[Inizio pagina](#mainsection)

### Procedura di distribuzione wireless Intranet

Per questa configurazione, attenersi alla seguente procedura:

1.  Configurare l'infrastruttura di certificazione.

2.  Configurare Active Directory per gli account e i gruppi.

3.  Configurare il server IAS primario su un computer.

4.  Configurare il server IAS secondario su un altro computer.

5.  Distribuire e configurare i punti di accesso wireless.

6.  Configurare le impostazioni Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11).

7.  Installare i certificati di computer sui computer client wireless (EAP-TLS).

8.  Installare i certificati utente sui computer client wireless (EAP-TLS).

9.  Configurare i computer client wireless per EAP-TLS.

10. Configurare i computer client wireless per PEAP-MS-CHAP v2.

#### Passaggio 1: configurare l'infrastruttura di certificazione

Nella tabella 1 si riassumono i certificati necessari per i diversi tipi di autenticazione.

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo di autenticazione</th>
<th style="border:1px solid black;" >Certificati sul computer client wireless</th>
<th style="border:1px solid black;" >Certificati sul server IAS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">EAP-TLS</td>
<td style="border:1px solid black;">Certificati di computer
Certificati utente
Certificati delle autorità di certificazione radice per le autorità di emissione di certificati di computer del server IAS</td>
<td style="border:1px solid black;">Certificati di computer
I certificati di autorità di certificazione radice per le autorità di emissione di certificati di computer client wireless e dei certificati utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PEAP-MS-CHAP v2</td>
<td style="border:1px solid black;">Certificati delle autorità di certificazione radice per le autorità di emissione di certificati di computer del server IAS</td>
<td style="border:1px solid black;">Certificati di computer</td>
</tr>
</tbody>
</table>
  
**Tabella 1  Tipi e certificati di autenticazione**
  
Indipendentemente dal metodo di autenticazione utilizzato per le connessioni wireless, EAP-TLS o PEAP-MS-CHAP v2, occorrerà installare i certificati di computer sui server IAS.
  
Per PEAP-MS-CHAP v2, non è necessario distribuire una infrastruttura di certificazione per emettere i certificati di computer e i certificati utente per ogni computer client wireless. È possibile ottenere certificati individuali per ogni server IAS dell'organizzazione da una autorità di certificazione commerciale e installarli sui server IAS. Per ulteriori informazioni, vedere il "Passaggio 3: configurare il server IAS primario" e il "Passaggio 4: configurare il server IAS secondario" in questo articolo. I computer client wireless Windows includono numerosi certificati di autorità di certificazione radice per le autorità di certificazione commerciali più note e affidabili. Se si ottengono certificati di computer da una autorità di certificazione commerciale per cui è stato già installato un certificato di autorità di certificazione radice, non occorrerà installare alcun certificato aggiuntivo sui computer client wireless Windows. Se si ottengono certificati di computer da una autorità di certificazione commerciale per cui non è stato già installato un certificato di autorità di certificazione radice, occorrerà installare i certificati di autorità di certificazione radice per le autorità di emissione dei certificati di computer installati sui server IAS su ogni computer client wireless Windows. Per ulteriori informazioni, vedere "Passaggio 10: configurare i computer client wireless per PEAP-MS-CHAP v2" in questo articolo.
  
Per l'autenticazione del computer con EAP-TLS, occorre installare un certificato di computer sul computer client wireless. Il certificato di computer installato sul computer client wireless viene utilizzato per autenticare il computer client wireless in modo che il computer possa ottenere la connettività di rete con la Intranet dell'organizzazione e gli aggiornamenti dei Criteri di gruppo della configurazione del computer prima dell'accesso utente. Per l'autenticazione utente con EAP-TLS dopo che è stata stabilita una connessione di rete e l'utente ha effettuato l'accesso, occorre utilizzare un certificato utente sul computer client wireless.
  
Il certificato di computer è installato sul server IAS in modo che, durante l'autenticazione EAP-TLS, il server IAS abbia un certificato da inviare al computer client wireless per l'autenticazione reciproca, indipendentemente dal fatto che il computer client wireless si autentichi con un certificato di computer o un certificato utente. I certificati di computer e i certificati utente presentati dal computer client wireless e dal server IAS durante l'autenticazione EAP-TLS devono essere conformi ai requisiti specificati in "Utilizzo di autorità di certificazione di terze parti" in questo articolo.
  
In Windows Server 2003, Windows XP e Windows 2000, è possibile vedere la catena di certificati dalla scheda **Percorso certificazione** nelle proprietà dello snap-in Certificati. È possibile vedere i certificati di autorità di certificazione radice installati nella cartella Autorità di certificazione principale attendibili\\Certificati e è possibile vedere i certificati delle autorità di certificazione intermedi nella cartella Autorità di certificazione intermedie\\Certificati.
  
In una tipica distribuzione di certificati in una grande organizzazione, l'infrastruttura di certificazione è configurata utilizzando una singola autorità di certificazione radice in una gerarchia a tre livelli che comprende le autorità di certificazione radice/intermedie/di emissione. Le autorità di certificazione di emissione sono configurate per emettere certificati di computer o certificati utente. Quando il certificato di computer o il certificato utente è installato sul computer client wireless, vengono installati anche il certificato dell'autorità di certificazione di emissione, i certificati dell'autorità di certificazione intermedia e il certificato dell'autorità di certificazione radice. Quando il certificato di computer o il certificato utente è installato sul server IAS, vengono installati anche il certificato dell'autorità di certificazione di emissione, i certificati dell'autorità di certificazione intermedia e il certificato dell'autorità di certificazione radice. L'autorità di certificazione di emissione per il certificato di server IAS può essere diversa dall'autorità di certificazione di emissione per i certificati del computer client wireless. In questo caso, sia il computer client wireless che il server IAS hanno tutti i certificati richiesti per eseguire la convalida del certificato per l'autenticazione EAP-TLS.
  
**Procedure consigliate** Se si utilizza l'autenticazione EAP-TLS, si consiglia di utilizzare sia i certificati utente che i certificati di computer.
  
Se si utilizza l'autenticazione EAP-TLS, non utilizzare anche PEAP-TLS. Se si consente il traffico sia dell'autenticazione protetta che di quella non protetta per lo stesso tipo di connessione di rete, il traffico di autenticazione protetto diventa suscettibile agli attacchi di spoofing.
  
Se si ha già un'infrastruttura di certificazione per l'autenticazione EAP-TLS e si utilizza RADIUS per le connessioni di accesso remoto o su rete privata virtuale (VPN), è possibile ignorare alcuni dei passaggi dell'infrastruttura di certificazione. È possibile utilizzare la stessa infrastruttura di certificazione per le connessioni wireless. Per l'autenticazione del computer, tuttavia, è necessario assicurarsi che i certificati di computer siano installati. Per i computer in cui è in esecuzione Windows XP senza service pack installati, per l'autenticazione utente devono essere memorizzati sul computer i certificati utente (invece delle smart card). Per i computer con Windows Server 2003, Windows XP con Service Pack (SP1), Windows XP con Service Pack 2 (SP2), o Windows 2000, per l'autenticazione utente è possibile utilizzare sia i certificati utente memorizzati sul computer che una smart card.
  
##### Passaggio 1a: installare un'infrastruttura di certificazione
  
Quando si installa un'infrastruttura di certificazione, attenersi alle seguenti procedure consigliate:
  
-   Pianificare l'infrastruttura a chiave pubblica (PKI) prima di distribuire le autorità di certificazione.
  
-   L'autorità di certificazione radice dovrebbe essere fuori linea e la sua chiave di firma dovrebbe essere protetta da un Hardware Security Module (HSM) tenuto in un luogo sicuro per minimizzare il rischio di compromettere la chiave.
  
-   Le grandi organizzazioni non dovrebbero emettere certificati agli utenti o ai computer direttamente dall'autorità di certificazione radice, ma dovrebbero piuttosto distribuire quanto segue:
  
    -   Un'autorità di certificazione radice fuori linea
  
    -   Autorità di certificazione intermedie fuori linea
  
    -   Autorità di certificazione di emissione in linea utilizzando Servizi certificati di Windows Server 2003 o di Windows 2000 come una autorità di certificazione globale (enterprise)
  
    Questa gerarchia di autorità di certificazione fornisce flessibilità e isola l'autorità di certificazione radice in modo da impedire agli utenti malintenzionati di comprometterne la chiave privata. Le autorità di certificazione radice e intermedie fuori linea non devono necessariamente essere le autorità di certificazione di Windows Server 2003 o di Windows 2000. Le autorità di certificazione di emissione possono essere le subordinate di un'autorità di certificazione intermedia di terze parti.
  
-   Per proteggersi contro la perdita di dati critici è indispensabile eseguire il backup del database autorità di certificazione, del certificato autorità di certificazione e delle chiavi autorità di certificazione. Il backup delle autorità di certificazione dovrebbe essere eseguito a intervalli regolari (quotidianamente, settimanalmente, mensilmente) in base al numero di certificati emessi nello stesso intervallo. Più sono i certificati emessi, più frequente deve essere il backup delle autorità di certificazione.
  
-   Può essere utile rivedere i concetti di autorizzazioni di protezione e di controllo accessi in Windows, poiché le autorità di certificazione globali emettono i certificati sulla base delle autorizzazioni di protezione del richiedente il certificato.
  
Inoltre, se si vuole approfittare della registrazione automatica per i certificati di computer, utilizzare Servizi certificati di Windows 2000 Server o di Windows Server 2003 e creare un'autorità di certificazione globale (enterprise) a livello di autorità di certificazione di emissione. Se si vuole approfittare della registrazione automatica per i certificati utente, utilizzare i Servizi certificati di Windows Server 2003, Enterprise Edition, oppure di Windows Server 2003, Datacenter Edition e creare un'autorità di certificazione globale (enterprise) a livello di autorità di certificazione di emissione.
  
Per ulteriori informazioni, vedere l'argomento dal titolo "Elenco di controllo: distribuire le autorità di certificazione e l'infrastruttura a chiave pubblica (PKI) per un'Intranet" nella Guida in linea di Windows 2000 Server o l'argomento dal titolo "Elenco di controllo: creare una gerarchia di certificazione con un'autorità di certificazione radice fuori linea" nella Guida in linea e supporto tecnico di Windows Server 2003.
  
Per ulteriori informazioni sui servizi di protezione di Windows Server 2003, vedere il [sito Web di Windows Server 2003 Security Services](http://www.microsoft.com/windowsserver2003/technologies/security/default.mspx).
  
Per impostazione predefinita, il server IAS controlla la revoca di certificato per tutti i certificati nella catena dei certificati inviata dal computer client wireless durante il processo di autenticazione EAP-TLS. Se il controllo revoca di certificato non riesce per uno qualunque dei certificati nella catena, il tentativo di connessione non è autenticato ed è rifiutato. Il controllo della revoca di certificato per un certificato può non riuscire per le seguenti cause:
  
-   Il certificato è stato revocato.
  
    L'autorità di emissione del certificato ha revocato esplicitamente il certificato.
  
-   L'elenco di revoche di certificati (CRL) per il certificato non è il accessibile o disponibile.
  
    Le autorità di certificazione mantengono gli elenchi di revoche di certificati e li pubblicano su punti di distribuzione CRL specifici. I punti di distribuzione CRL sono contenuti nella proprietà Punti di distribuzione CRL del certificato. Se non è possibile contattare i punti di distribuzione CRL per controllare la revoca di certificato, allora il controllo della revoca di certificato non riesce.
  
    Inoltre, se non ci sono i punti di distribuzione CRL nel certificato, il server IAS non può verificare che il certificato non sia stato revocato e la verifica della revoca di certificato non riesce.
  
-   L'autorità di emissione dell'elenco di revoche di certificati non ha emesso il certificato.
  
    L'autorità di certificazione di pubblicazione è inclusa nell'elenco di revoche di certificati. Se l'autorità di certificazione di pubblicazione dell'elenco di revoche di certificati non è la stessa autorità di certificazione di emissione per il certificato di cui si controlla la revoca di certificato, il controllo della revoca di certificato non riesce.
  
-   L'elenco di revoche di certificati non è attuale
  
    Ogni elenco di revoche di certificati pubblicato ha un periodo di validità. Se la data **Prossimo aggiornamento** dell'elenco di revoche di certificati è stata superata, l'elenco di revoche di certificati è considerato non più valido e il controllo della revoca di certificato non riesce. I nuovi elenchi di revoche di certificati dovrebbero essere pubblicati prima della data di scadenza dell'ultimo elenco di revoche di certificati pubblicato.
  
Le regole del controllo della revoca di certificato per IAS possono essere modificate tramite le impostazioni del registro di sistema. Per ulteriori informazioni, vedere [Troubleshooting Windows IEEE 802.11 Wireless Access](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wifitrbl.mspx) (la pagina potrebbe essere in inglese).
  
Poiché il controllo della revoca di certificato può impedire l'accesso wireless a causa della non disponibilità o della scadenza dei CRL per ogni certificato nella catena di certificati, conviene progettare l'infrastruttura a chiave pubblica (PKI) per una elevata disponibilità di CRL. Ad esempio, configurando punti multipli di distribuzione CRL per ogni autorità di certificazione nella gerarchia di certificati e configurando le pianificazioni di pubblicazione in modo da assicurare che sia sempre disponibile il CRL più attuale.
  
Il controllo della revoca di certificato è accurato tanto quanto il CRL pubblicato più recente. Ad esempio, se un certificato è revocato, per impostazione predefinita il nuovo CRL che contiene il certificato revocato di recente non viene pubblicato automaticamente. I CRL sono generalmente pubblicati in base a una pianificazione configurabile. Questo significa che un certificato revocato può ancora essere utilizzato per autenticare perché il CRL pubblicato non è attuale; non contiene il certificato revocato e quindi può ancora essere utilizzato per creare connessioni wireless. Per evitare che questo accada, l'amministratore di rete deve pubblicare manualmente il nuovo CRL con il certificato revocato di recente.
  
Per impostazione predefinita il server IAS utilizza i punti di distribuzione di CRL nei certificati. Tuttavia è anche possibile memorizzare una copia locale del CRL sul server IAS. In questo caso, viene utilizzato il CRL durante il controllo della revoca di certificato. Se viene pubblicato manualmente un nuovo CRL in Active Directory, il CRL locale sul server IAS non è più aggiornato. Il CRL locale viene aggiornato quando scade. Può venirsi a creare una situazione in cui un certificato è revocato, il CRL è pubblicato manualmente, ma il server IAS consente ancora la connessione perché il CRL locale non è stato ancora aggiornato.
  
##### Passaggio 1b: installare i certificati di computer
  
Se si utilizza l'autorità di certificazione globale (enterprise) di Servizi certificati per Windows Server 2003 o Windows 2000 come autorità di certificazione di emissione, è possibile installare un certificato di computer sul server IAS configurando i Criteri di gruppo per la registrazione automatica dei certificati di computer per i computer in un contenitore di sistema Active Directory.  
  
**Per configurare la registrazione del certificato di computer per un'autorità di certificazione globale (enterprise)**
  
1.  Aprire lo snap-in Utenti e computer di Active Directory.
  
2.  Nella struttura console, fare doppio clic su **Utenti e computer di Active Directory**, fare clic con il pulsante destro del mouse sul nome di dominio a cui appartiene l'autorità di certificazione e quindi scegliere **Proprietà**.
  
3.  Nella scheda **Criteri di gruppo**, scegliere l'oggetto Criteri di gruppo appropriato (l'oggetto predefinito è **Criterio dominio predefinito**) e scegliere **Modifica**.
  
4.  Nella struttura console, aprire, nell'ordine, **Configurazione Computer**, **Impostazioni di Windows**, **Impostazioni protezione**, **Criteri chiave pubblica**, **Impostazioni richiesta automatica certificati**.
  
5.  Fare clic con il pulsante destro del mouse su **Impostazioni richiesta automatica certificati**, scegliere **Nuovo** e quindi **Richiesta automatica certificati**.
  
6.  Viene visualizzata la procedura guidata di Richiesta automatica certificati. Scegliere **Avanti**.
  
7.  In **Modelli di certificato**, scegliere **Computer** e quindi **Avanti**.
  
    L'autorità di certificazione globale (enterprise) appare nell'elenco.
  
8.  Fare clic sull'autorità di certificazione globale (enterprise), scegliere **Avanti** e **Fine**.
  
9.  Per ottenere immediatamente un certificato di computer per l'autorità di certificazione in esecuzione in Windows 2000 Server, digitare quanto segue al prompt dei comandi:
  
    **secedit /refreshpolicy machine\_policy**
  
10. Per ottenere immediatamente un certificato di computer per l'autorità di certificazione in esecuzione in Windows Server 2003, digitare quanto segue al prompt dei comandi:
  
    **gpupdate /target:computer**
  
Dopo che il dominio è configurato per la registrazione automatica, ogni computer che è membro del dominio richiede un certificato di computer quando i Criteri di gruppo del computer vengono aggiornati. Per impostazione predefinita, il servizio Winlogon esegue il polling per verificare le modifiche nei Criteri di gruppo ogni 90 minuti. Per forzare un aggiornamento dei Criteri di gruppo del computer, riavviare il computer o digitare al prompt dei comandi **secedit /refreshpolicy machine\_policy** (per un computer in cui è in esecuzione Windows 2000) oppure **gpupdate /target:computer** (per un computer in cui è in esecuzione Windows XP o Windows Server 2003).
  
Eseguire questa procedura per ogni contenitore del sistema di dominio secondo necessità.
  
**Procedure consigliate**  Se si utilizza un'autorità di certificazione globale (enterprise) Windows Server 2003 o Windows 2000 come autorità di certificazione di emissione, configurare la registrazione automatica dei certificati di computer per installare i certificati di computer su tutti i computer. Assicurarsi che tutti i contenitori di sistema necessari del dominio siano configurati per la registrazione automatica dei certificati di computer o tramite l'ereditarietà delle impostazioni dei criteri di gruppo di un contenitore di sistema genitore o tramite configurazione esplicita.
  
##### Passaggio 1c: installare i certificati utente
  
Se si utilizza un'autorità di certificazione globale (enterprise) Windows Server 2003, Enterprise Edition, o Windows Server 2003, Datacenter Edition, come autorità di certificazione di emissione, è possibile installare i certificati utente tramite la registrazione automatica. Configurando la registrazione automatica di certificato utente per i certificati utente wireless è necessario duplicare i modelli di certificato esistenti, una funzionalità che è supportata soltanto per le autorità di certificazione globali Windows Server 2003, Enterprise Edition, o Windows Server 2003, Datacenter Edition.
  
Soltanto i computer client wireless Windows XP e Windows Server 2003 supportano la registrazione automatica del certificato utente.
  
**Per configurare la registrazione di certificato utente per l'autorità di certificazione globale (enterprise) Windows Server 2003, Enterprise Edition, o Windows Server 2003, Datacenter Edition**
  
1.  Fare clic su **Start**, **Esegui**, digitare **mmc** e fare clic su **OK**.
  
2.  Nel menu **File**, fare clic su **Aggiungi/Rimuovi Snap-in** e scegliere **Aggiungi**.
  
3.  In **Snap-in**, fare doppio clic su **Modelli di certificato**, scegliere **Chiudi** e **OK**.
  
4.  Nella struttura console, fare clic su **Modelli di certificato**. Tutti i modelli di certificato saranno visualizzati nel riquadro dettagli.
  
5.  Nel riquadro dettagli, fare clic sul modello **Utente**.
  
6.  Nel menu **Azione**, fare clic su **Duplica modello**.
  
7.  Nel campo **Nome visualizzato**, digitare **WirelessUser** (esempio).
  
8.  Assicurarsi che sia selezionata la casella di controllo **Pubblica certificato in Active Directory**.
  
9.  Fare clic sulla scheda **Protezione**.
  
10. Nel campo **Utenti e gruppi**, scegliere **Utenti dominio**.
  
11. Nell'elenco **Autorizzazioni Utenti dominio**, selezionare le caselle di controllo di autorizzazione **Registra** e **Registrazione automatica** e scegliere **OK**.
  
12. Aprire lo snap-in Autorità di certificazione.
  
13. Nella struttura console, aprire **Autorità di certificazione**, quindi il nome dell'autorità di certificazione, quindi **Modelli di certificato**.
  
14. Nel menu **Azione**, scegliere **Nuovo** e **Certificato da emettere**.
  
15. Fare clic su **WirelessUser** (esempio) e scegliere **OK**.
  
16. Aprire lo snap-in Utenti e computer di Active Directory.
  
17. Nella struttura console, fare doppio clic su **Utenti e computer di Active Directory**, fare clic con il pulsante destro del mouse sul contenitore di sistema di dominio che contiene gli account utente wireless e scegliere **Proprietà**.
  
18. Nella scheda **Criteri di gruppo** , fare clic sull'oggetto Criteri di gruppo appropriato (l'oggetto predefinito è **Criterio dominio predefinito**) e scegliere **Modifica**.
  
19. Nella struttura console, aprire **Configurazione utente**, quindi **Impostazioni di Windows**, quindi **Impostazioni protezione** e **Criteri chiave pubblica**.
  
20. Nel riquadro dettagli, fare doppio clic su **Impostazioni registrazione automatica**.
  
21. Scegliere **Registra i certificati automaticamente**.
  
22. Selezionare la casella di controllo **Rinnova i certificati scaduti, aggiorna quelli in sospeso e rimuovi i certificati revocati**.
  
23. Selezionare la casella di controllo **Aggiorna i certificati che utilizzano modelli di certificato** e scegliere **OK**.
  
Eseguire i passaggi 17-23 per ogni contenitore di sistema del dominio secondo necessità.
  
**Procedure consigliate**  Se si utilizza un'autorità di certificazione globale (enterprise) Windows Server 2003, Enterprise Edition, o Windows Server 2003, Datacenter Edition, come autorità di certificazione di emissione, configurare la registrazione automatica dei certificati utente per installare i certificati utente su tutti i computer. Assicurarsi che tutti i contenitori di sistema del dominio necessari siano configurati per la registrazione automatica dei certificati utente o tramite l'ereditarietà delle impostazioni dei criteri di gruppo di un contenitore di sistema genitore o tramite configurazione esplicita.
  
#### Passaggio 2: configurare Active Directory per gli account e i gruppi
  
Per configurare l'utente Active Directory e gli account computer e gruppi per l'accesso wireless, effettuare quanto segue:
  
1.  Se si utilizzano i controller di dominio Windows 2000, installare Windows 2000 SP3 o SP4 su tutti i controller di dominio.
  
2.  Assicurarsi che tutti gli utenti che usano connessioni wireless abbiano il corrispondente account utente.
  
3.  Assicurarsi che tutti i computer che usano connessioni wireless abbiano il corrispondente account di computer.
  
4.  Impostare l'autorizzazione di accesso remoto degli account utente e computer nel modo opportuno (**Consenti accesso** oppure **Controlla accesso tramite Criteri di accesso remoto**). L'impostazione dell'autorizzazione di accesso remoto è nella scheda **Chiamate in ingresso** nelle proprietà di un account utente o account di computer nello snap-in Utenti e computer di Active Directory.
  
5.  Organizzare gli account di accesso utente o computer wireless nei gruppi opportuni. Per un dominio in modalità nativa, è possibile usare gruppi globali universali e nidificati. Ad esempio, creare un gruppo universale chiamato WirelessUsers che contiene i gruppi globali degli utenti e computer wireless per l'accesso a Intranet.
  
    **Procedura consigliata**  Utilizzare un dominio in modalità nativa e gruppi universali e globali per organizzare gli account wireless in un gruppo solo.
  
#### Passaggio 3: configurare il server IAS primario
  
La configurazione del server IAS primario su un computer comporta quanto segue:
  
-   Configurare IAS affinché sia in grado di accedere alle informazioni di account, registrazione, porte UDP e per i computer client RADIUS corrispondenti ai punti di accesso wireless.
  
-   Configurare i criteri di accesso remoto per l'accesso wireless.
  
##### Passaggio 3a: configurare IAS
  
Per configurare il server IAS primario su un computer, procedere come segue:
  
1.  Se si utilizza la registrazione automatica del certificato di computer e IAS per Windows 2000, forzare un aggiornamento dei Criteri di gruppo del computer digitando **secedit /refreshpolicy machine\_policy** dal prompt dei comandi. Se si utilizza la registrazione automatica del certificato di computer e IAS di Windows Server 2003, forzare un aggiornamento dei Criteri di gruppo del computer digitando **gpupdate /target:computer** dal prompt dei comandi.
  
2.  Se si utilizza l'autenticazione PEAP-MS-CHAP v2 e si è ottenuto un certificato di computer da una autorità di certificazione commerciale, utilizzare lo snap-in Certificati per importarlo nella cartella Certificati (computer locale)\\ Personale\\Certificati. Per eseguire questa procedura, è necessario essere membro del gruppo Amministratori sul computer locale oppure avere ricevuto l'autorità necessaria. È anche possibile importare un certificato facendo doppio clic su un file di certificato che è memorizzato in una cartella o inviato in un messaggio di posta elettronica. Sebbene valga per i certificati creati con le autorità di certificazione di Windows, questo metodo non funziona per le autorità di certificazione di terze parti. Il metodo consigliato per importare i certificati è l'utilizzo dello snap-in Certificati.
  
    Per informazioni su come installare un certificato VeriSign, Inc. per l'autenticazione PEAP-MS-CHAP v2, vedere [Obtaining and Installing a VeriSign WLAN Server Certificate for PEAP-MS-CHAP v2 Wireless Authentication](http://www.microsoft.com/downloads/details.aspx?familyid=1971d43c-d2d9-408d-bd97-139afc60996b&displaylang=en) (in inglese).
  
3.  Installare IAS come componente opzionale di rete.
  
4.  Se si utilizza IAS per Windows 2000, installare Windows 2000 SP4.
  
5.  Il server IAS primario deve essere in grado di accedere alle proprietà dell'account nei domini opportuni. Se IAS viene installato su un controller di dominio, non è richiesta alcuna configurazione aggiuntiva per consentire a IAS di accedere alle proprietà dell'account nel dominio del controller di dominio.
  
    Se IAS non è installato su un controller di dominio, configurare il server IAS primario per leggere le proprietà degli account utente nel dominio. Per ulteriori informazioni, vedere la procedura "Abilitare il server IAS a leggere gli account utente in Active Directory" in questa sezione.
  
    Se il server IAS autentica e autorizza i tentativi di connessione wireless per gli account utente negli altri domini, verificare che gli altri domini abbiano un trust bidirezionale col dominio di cui il server IAS è membro, quindi configurare il server IAS per leggere le proprietà degli account utente negli altri domini. Per ulteriori informazioni, vedere la procedura "Abilitare il server IAS a leggere gli oggetti utente in Active Directory" in questa sezione.
  
    Se esistono account negli altri domini e quei domini non hanno un trust bidirezionale col dominio di cui il server IAS è membro, occorre configurare un proxy RADIUS tra i due domini non trusted. Se esistono account nelle altre foreste di Active Directory, occorre configurare un proxy RADIUS tra le foreste. Per ulteriori informazioni, vedere '"Autenticazione tra foreste" in questo articolo.
  
6.  Se si vogliono memorizzare le informazioni di autenticazione e accounting per l'analisi della connessione e per ricerche sulla protezione, attivare la registrazione eventi di autenticazione e accounting. IAS per Windows 2000 è in grado di registrare le informazioni in un file locale. IAS di Windows Server 2003 è in grado di registrare le informazioni in un file locale e in un database SQL (Structured Query Language) Server. Per ulteriori informazioni, vedere l'argomento dal titolo "Configura le proprietà dei file di registro" nella Guida di Windows 2000 e l'argomento dal titolo "Configurare la registrazione per l'autenticazione utente e l'accounting" nella Guida in linea e supporto tecnico di Windows Server 2003.
  
7.  Se necessario, configurare le porte UDP aggiuntive per i messaggi di autenticazione e accounting che sono inviati dai computer client RADIUS (i punti di accesso wireless). Per ulteriori informazioni, vedere la procedura "Configurare le informazioni della porta IAS" in questa sezione. Per impostazione predefinita, IAS utilizza le porte UDP 1812 e 1645 per i messaggi di autenticazione e le porte UDP 1813 e 1646 per i messaggi di accounting.
  
8.  Aggiungere i punti di accesso wireless come computer client RADIUS del server IAS. Per ulteriori informazioni, vedere la procedura "Aggiungere i computer client RADIUS" in questa sezione. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti per ogni punto di accesso wireless.
  
    Utilizzare un segreto condiviso diverso per ogni punto di accesso wireless. Ogni segreto condiviso dovrebbe essere una sequenza casuale di lettere maiuscole e minuscole, numeri e segni di interpunzione, lungo almeno 22 caratteri. Per assicurare la casualità, utilizzare un programma di generazione casuale di caratteri per creare i segreti condivisi da configurare sul server IAS e sul punto di accesso wireless.
  
    Per assicurare la massima protezione per i messaggi RADIUS, si consiglia di utilizzare Internet Protocol Security (IPsec) e Encapsulating Security Payload (EPS) con autenticazione di certificato per garantire la riservatezza e l'integrità dei dati e l'autenticazione dell'origine dati per il traffico RADIUS tra i server IAS e i punti di accesso wireless. Windows 2000 e Windows Server 2003 supportano IPsec. IPsec deve essere supportato anche dai punti di accesso wireless.
  
**Abilitare il server IAS a leggere gli account utente in Active Directory**
  
Per iscrivere il server IAS nel dominio predefinito utilizzando il Servizio di Autenticazione Internet:
  
1.  Accedere al server IAS con un account che abbia le autorizzazioni di amministratore del dominio.
  
2.  Aprire lo snap-in Servizio di Autenticazione Internet.
  
3.  Fare clic con il pulsante destro del mouse su Servizio di Autenticazione Internet, quindi fare clic su **Registra server in Active Directory**. Quando viene visualizzata la finestra di dialogo **Registra il Servizio di Autenticazione Internet in Active Directory**, scegliere **OK**.
  
Per iscrivere il server IAS nel dominio predefinito utilizzando lo strumento netsh:
  
1.  Accedere al server IAS con un account che goda delle autorizzazioni di amministratore del dominio.
  
2.  Aprire un prompt dei comandi.
  
3.  Al prompt dei comandi digitare: **netsh ras add registeredserver**
  
Per iscrivere il server IAS nel dominio predefinito utilizzando Utenti e computer di Active Directory:
  
1.  Accedere al server IAS con un account che abbia le autorizzazioni di amministratore del dominio.
  
2.  Aprire lo snap-in Utenti e computer di Active Directory.
  
3.  Nella struttura console, fare clic sulla cartella **Utenti** del dominio appropriato.
  
4.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse su **Server RAS e IAS** quindi scegliere **Proprietà**.
  
5.  Nella finestra di dialogo **Proprietà Server RAS e IAS**, nella scheda **Membri**, aggiungere il server IAS.
  
Per iscrivere il server IAS nel dominio predefinito utilizzando Utenti e computer di Active Directory:
  
1.  Accedere al server IAS con un account che abbia le autorizzazioni di amministratore del dominio.
  
2.  Aprire lo snap-in Utenti e computer di Active Directory.
  
3.  Nella struttura console, fare clic sulla cartella **Utenti** del dominio appropriato.
  
4.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse su **Server RAS e IAS** quindi scegliere **Proprietà**.
  
5.  Nella finestra di dialogo **Proprietà Server RAS e IAS**, nella scheda **Membri**, aggiungere ogni server IAS necessario.
  
Per iscrivere il server IAS in un altro dominio utilizzando lo strumento netsh:
  
1.  Accedere al server IAS con un account che abbia le autorizzazioni di amministratore del dominio.
  
2.  Aprire un prompt dei comandi.
  
3.  Al prompt dei comandi digitare: **netsh ras add registeredserver** *Domain IASServer*
  
    dove *Domain* è il nome di dominio DNS del dominio e *IASServer* è il nome del server IAS.
  
**Configurare le informazioni della porta IAS**
  
1.  Aprire lo snap-in Servizio di Autenticazione Internet.
  
2.  Fare clic con il pulsante destro del mouse su **Servizio di Autenticazione Internet** e scegliere **Proprietà**.
  
3.  Per IAS per Windows 2000, fare clic sulla scheda **RADIUS**. Per Windows Server 2003, fare clic sulla scheda **Porte**. Esaminare le impostazioni per le porte. Se le porte UDP di autenticazione e di accounting RADIUS differiscono dai valori predefiniti citati (1812 o 1645 per l'autenticazione e 1813 o 1646 per l'accounting), in **Autenticazione** e in **Accounting**, digitare le impostazioni della porta.
  
    Per utilizzare porte multiple per le richieste di autenticazione o accounting, separare le porte con una virgola.
  
**Aggiungere i computer client RADIUS**
  
1.  Aprire lo snap-in Servizio di Autenticazione Internet.
  
2.  Per IAS per Windows 2000, nella struttura console, fare clic con il pulsante destro del mouse su **Client** e scegliere **Nuovo client**. Per IAS di Windows Server 2003, nella struttura console, fare clic con il pulsante destro del mouse su **RADIUS Client** e scegliere **Nuovo client RADIUS**.
  
3.  In **Nome descrittivo**, digitare un nome descrittivo.
  
4.  In **Protocollo**, scegliere **RADIUS** e **Avanti**.
  
5.  In **Indirizzo Client (IP o DNS)**, digitare il nome DNS o l'indirizzo IP del client (il punto di accesso wireless o lo switch wireless). Se si utilizza un nome DNS, fare clic su **Verifica**. Nella finestra di dialogo **Risolvi nome DNS**, fare clic su **Risolvi** e scegliere l'indirizzo IP che si vuole associare a quel nome da **Risultati ricerca**.
  
6.  Se si intende utilizzare i punti di accesso wireless o i criteri specifici per accesso remoto tramite switch ai fini della configurazione (ad esempio, un criterio di accesso remoto che contiene gli attributi specifici per il fornitore), scegliere **Fornitore client** e selezionare il nome del produttore. Se non si conosce il produttore o quest'ultimo non è nell'elenco, scegliere **RADIUS standard**.
  
7.  In **Segreto condiviso**, digitare il segreto condiviso per il computer client, quindi digitarlo ancora in **Conferma il segreto condiviso**.
  
8.  Scegliere **Fine**.
  
    **Procedure consigliate**  Se possibile, utilizzare IPsec ESP per garantire la riservatezza dei dati per il traffico RADIUS tra il punto di accesso wireless e i server IAS. Utilizzare almeno la crittografia 3DES e, se possibile, i certificati per l'autenticazione Internet Key Exchange (IKE).
  
    Utilizzare segreti condivisi che consistano in una sequenza casuale di lettere maiuscole e minuscole, numeri e segni di interpunzione, lunga almeno 22 caratteri e utilizzare un segreto condiviso diverso per ogni punto di accesso wireless. Se possibile, utilizzare un programma di generazione casuale di stringhe per creare il segreto condiviso.
  
##### Passaggio 3b: configurare i criteri di accesso remoto wireless
  
Per configurare i criteri di accesso remoto wireless per il server IAS primario, procedere come segue:
  
1.  Per IAS per Windows 2000, creare un nuovo criterio di accesso remoto per l'accesso wireless a Intranet con le seguenti impostazioni:
  
    Nome criterio: Accesso wireless Intranet (ad esempio)
  
    Condizioni: NAS-Port-Type=Wireless-Other e Wireless-IEEE 802.11, Windows-Groups=WirelessUsers
  
    Autorizzazioni: Selezionare **Consenti l'accesso remoto**.
  
    Profilo, scheda **Autenticazione**: Se si utilizza l'autenticazione di EAP-TLS, scegliere **Extensible Authentication Protocol** e il tipo EAP **Smart Card o altro certificato**. Deselezionare tutte le altre caselle di controllo. Se sul server IAS sono installati più certificati di computer, fare clic su **Configura** e scegliere il certificato di computer appropriato. Se il certificato di computer previsto non è visualizzato, significa che il computer non supporta SChannel.
  
    Se si utilizza l'autenticazione PEAP-MS-CHAP v2, scegliere **Extensible Authentication Protocol** e il tipo EAP **PEAP (Protected EAP)** e scegliere **Configura**. Nella finestra di dialogo **Proprietà PEAP**, scegliere il certificato di computer appropriato e assicurarsi che sia selezionato **Password protetta (EAP-MSCHAP v2)** come tipo EAP.
  
    Profilo, scheda **Crittografia**: Deselezionare tutte le altre caselle di controllo eccetto la casella di controllo **Livello massimo**. In tal modo si forzano tutte le connessioni wireless a utilizzare la crittografia a 128 bit. Le impostazioni nella scheda **Crittografia** corrispondono agli attributi RADIUS MS-MPPE-Encryption-Policy e MS-MPPE-Encryption-Types e potrebbero essere supportate dal punto di accesso wireless. Se questi attributi non sono supportati, deselezionare tutte le caselle di controllo eccetto **Senza crittografia**.
  
    Per ulteriori informazioni, vedere la procedura "Aggiungere un criterio di accesso remoto" in questa sezione.
  
2.  Per IAS di Windows Server 2003, utilizzare Creazione guidata nuovo criterio di accesso remoto per creare un criterio di accesso remoto comune con le seguenti impostazioni:
  
    Nome criterio: Accesso wireless a Intranet (ad esempio)
  
    Metodo di accesso: wireless
  
    Accesso utente o di gruppo: gruppo con selezionato il gruppo WirelessUsers (esempio di nome di gruppo)
  
    Metodi di autenticazione: tipo **Smart Card o altro certificato** (per EAP-TLS) oppure tipo **PEAP (Protected EAP)** (per EAP-MS-CHAP v2)
  
3.  Se i punti di accesso wireless richiedono attributi specifici del fornitore (VSA), occorre aggiungere gli attributi VSA ai criteri di accesso remoto. Per ulteriori informazioni, vedere la procedura "Configurare gli attributi specifici del fornitore per un criterio di accesso remoto" in questa sezione.
  
4.  Per IAS per Windows 2000, eliminare i criteri di accesso remoto predefiniti chiamati **Allow access if dial-in permission is enabled** (Consenti l'accesso se l'autorizzazione di accesso remoto è attivata). Per eliminare i criteri di accesso remoto, fare clic con il pulsante destro del mouse sul nome del criterio nello snap-in Servizio di Autenticazione Internet e fare clic su **Cancella**.
  
    **Procedura consigliata**  Se si gestisce l'autorizzazione di accesso remoto degli account utente e computer in base all'account, utilizzare criteri di accesso remoto che specifichino un tipo di connessione. Se si gestisce l'autorizzazione di accesso remoto in base ai criteri di accesso remoto, utilizzare criteri di accesso remoto che specifichino un tipo di connessione e il gruppo. Il metodo consigliato è la gestione dell'autorizzazione di accesso remoto in base ai criteri di accesso remoto.
  
**Aggiungere un criterio di accesso remoto**
  
1.  Aprire lo snap-in Servizio di Autenticazione Internet.
  
2.  Nella struttura console, fare clic con il pulsante destro del mouse su **Criteri di accesso remoto** e scegliere **Nuovi Criteri di accesso remoto**.
  
**Configurare gli attributi specifici del fornitore per un criterio di accesso remoto**
  
1.  Aprire lo snap-in Servizio di Autenticazione Internet.
  
2.  Nella struttura console, fare clic su **Criteri di accesso remoto**.
  
3.  Nel riquadro dettagli, fare doppio clic sui criteri per cui si vuole configurare un attributo specifico del fornitore (VSA).
  
4.  Scegliere **Modifica profilo**, fare clic sulla scheda **Avanzate** e scegliere **Aggiungi**.
  
5.  Cercare se l'attributo specifico del fornitore è già presente nell'elenco di attributi RADIUS disponibili. Se l'attributo è presente, fare doppio clic su di esso e configurarlo per il punto di accesso wireless nel modo specificato nella documentazione.
  
6.  Se l'attributo non è nell'elenco di attributi RADIUS disponibili, scegliere **Attributi specifici fornitore** e **Aggiungi**.
  
7.  Nella finestra di dialogo **Informazioni attributi multivalore**, scegliere **Aggiungi**.
  
8.  Specificare il fornitore del punto di accesso o dello switch wireless. Per specificare il fornitore selezionando il nome dall'elenco, scegliere **Selezionare nell'elenco** quindi selezionare il fornitore del punto di accesso wireless o dello switch per cui si sta configurando il VSA. Se il fornitore non è elencato, specificarlo digitando il codice fornitore.
  
9.  Per specificare il fornitore digitando il codice fornitore, fare clic su **Immettere il codice fornitore** e digitare il codice fornitore nello spazio previsto. Vedere la RFC 1007 per un elenco SMI Network Management Private Enterprise Codes.
  
10. Specificare se l'attributo è conforme al formato VSA specificato nella RFC 2865. Se non si è sicuri della conformità, vedere la documentazione per il punto di accesso wireless.
  
11. Se l'attributo è conforme, scegliere **Sì, è conforme.** quindi **Configurazione attributo**. In **Numero attributo assegnato dal fornitore**, digitare il numero assegnato all'attributo (dovrebbe essere un numero intero da 0 a 255). In **Formato attributo**, specificare il formato dell'attributo, quindi in **Valori attributo**, digitare il valore che si assegna all'attributo.
  
12. Se l'attributo non è conforme, scegliere **No, non è conforme.** quindi **Configura attributo**. In **Valore attributo esadecimale**, digitare il valore per l'attributo.
  
    **Procedura consigliata**  Verificare se i punti di accesso o gli switch wireless hanno bisogno di VSA e configurarli durante la configurazione dei criteri di accesso remoto. Se si configurano i VSA dopo aver configurato i punti di accesso o gli switch wireless, sincronizzare nuovamente la configurazione tra il server IAS primario e il server IAS secondario.
  
#### Passaggio 4: configurare il server IAS secondario
  
Per configurare il server IAS secondario su un altro computer, procedere come segue:
  
1.  Se si utilizza la registrazione automatica del certificato di computer e IAS per Windows 2000, forzare un aggiornamento dei Criteri di gruppo del computer digitando **secedit /refreshpolicy machine\_policy** dal prompt dei comandi. Se si utilizza la registrazione automatica del certificato di computer e IAS di Windows Server 2003, forzare un aggiornamento dei Criteri di gruppo del computer digitando **gpupdate /target:computer** dal prompt dei comandi.
  
2.  Se si utilizza l'autenticazione PEAP-MS-CHAP v2 e si è ottenuto un certificato di computer da una autorità di certificazione commerciale, utilizzare lo snap-in Certificati per importarlo nella cartella Certificati (computer locale)\\ Personale\\Certificati.
  
3.  Installare IAS come componente opzionale di rete.
  
4.  Se si utilizza IAS per Windows 2000, installare Windows 2000 SP4.
  
5.  Il server IAS secondario deve essere in grado di accedere alle proprietà dell'account nei domini opportuni. Se IAS viene installato su un controller di dominio, non è richiesta alcuna configurazione aggiuntiva per consentire a IAS di accedere alle proprietà dell'account nel dominio del controller di dominio.
  
    Se IAS non è installato su un controller di dominio, per leggere le proprietà degli account utente nel dominio occorre configurare il server IAS secondario. Per ulteriori informazioni, vedere la procedura "Abilitare il server IAS a leggere gli account utente in Active Directory" descritta in precedenza.
  
    Se il server IAS autentica e autorizza i tentativi di connessione wireless per gli account utente negli altri domini, verificare che questi ultimi abbiano un trust bidirezionale col dominio di cui il server IAS secondario è membro. Quindi configurare il server IAS secondario per leggere le proprietà degli account utente negli altri domini. Per ulteriori informazioni, vedere la procedura "Abilitare il server IAS a leggere gli oggetti utente in Active Directory" descritta in precedenza.
  
    Se sono presenti account in altri domini e questi ultimi non hanno un trust bidirezionale col dominio di cui il server IAS secondario è membro, occorre configurare un proxy RADIUS tra i due domini non attendibili. Se ci sono account nelle altre foreste di Active Directory, occorre configurare un proxy RADIUS tra le foreste. Per ulteriori informazioni, vedere '"Autenticazione tra foreste" in questo articolo.
  
6.  Per copiare la configurazione dal server IAS primario al server IAS secondario, digitare **netsh aaaa show config** **&gt;** *path*\\*file*.*txt* al prompt dei comandi sul server IAS primario. Vengono così memorizzate in un file di testo le impostazioni di configurazione, comprese le impostazioni del Registro di sistema. Il percorso può essere relativo, assoluto, o un percorso di rete.
  
7.  Copiare il file creato nel passaggio 7 sul server IAS secondario. Al prompt dei comandi sul server IAS secondario, digitare **netsh exec** *path*\\*file*.*txt*. Questo comando importa tutte le impostazioni configurate sul server IAS primario nel server IAS secondario.
  
    **Nota**  Non è possibile copiare le impostazioni di IAS da un server IAS in cui è in esecuzione Windows Server 2003 a un server IAS in cui è in esecuzione Windows 2000 Server.
  
    **Procedura consigliata**  Se si modifica la configurazione del server IAS in qualunque modo, utilizzare lo snap-in Servizio di Autenticazione Internet per modificare la configurazione del server IAS primario quindi utilizzare i passaggi 7 e 8 descritti in precedenza per sincronizzare le modifiche sul server IAS secondario.
  
#### Passaggio 5: distribuire e configurare i punti di accesso wireless
  
Distribuire i punti di accesso o gli switch wireless per garantire la copertura per tutte le aree di copertura della rete wireless. Configurare i punti di accesso wireless in modo che supportino la crittografia WPA, WPA2 o WEP con autenticazione 802.1X. Configurare, inoltre, le impostazioni RADIUS sui punti di accesso wireless o sugli switch wireless come segue:
  
1.  L'indirizzo IP o il nome di un server RADIUS primario, il segreto condiviso, le porte UDP per l'autenticazione e l'accounting e infine le impostazioni di rilevamento errore.
  
2.  L'indirizzo IP o il nome di un server RADIUS secondario, il segreto condiviso, le porte UDP per l'autenticazione e l'accounting e infine le impostazioni di rilevamento errore.
  
Per bilanciare il carico di traffico RADIUS tra i due server IAS, configurare metà dei punti di accesso o degli switch wireless col server IAS primario come server RADIUS primario e il server IAS secondario come server RADIUS secondario; configurare l'altra metà dei punti di accesso o degli switch wireless col server IAS secondario come server RADIUS primario e il server IAS primario come il server RADIUS secondario.
  
Per ulteriori informazioni, vedere la documentazione per i punti di accesso e gli switch wireless.
  
Se i punti di accesso o gli switch wireless richiedono attributi specifici del fornitore (VSA) o attributi RADIUS aggiuntivi, si devono aggiungere i VSA o gli attributi ai criteri di accesso remoto dei server IAS. Per ulteriori informazioni, vedere la procedura "Configurare gli attributi specifici del fornitore per un criterio di accesso remoto" in questa sezione. Se si aggiungono i VSA o gli attributi RADIUS ai criteri di accesso remoto sul server IAS primario eseguire le fasi 7 e 8 della sezione "Passaggio 4: configurare il server IAS secondario" per copiare la configurazione di server IAS primario sul server IAS secondario.
  
#### Passaggio 6: configurare le impostazioni Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11)
  
Con l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) fornita in Windows Server 2003, è possibile specificare un elenco di reti preferite e le loro impostazioni, in modo da configurare automaticamente le impostazioni delle LAN wireless per i computer client wireless in cui è in esecuzione Windows XP con SP1, Windows XP con SP2, Windows Server 2003 senza service pack installati, o Windows Server 2003. Per ogni rete preferita, è possibile specificare impostazioni di associazione (come SSID e il metodo di autenticazione e crittografia) e le impostazioni di autenticazione 802.1X (come il tipo di EAP specifico).
  
Per configurare le impostazioni dei Criteri di gruppo di Criteri di reti senza fili (IEEE 802.11), procedere come segue:
  
1.  Aprire lo snap-in Utenti e computer di Active Directory.
  
2.  Nella struttura console, fare doppio clic su **Utenti e computer di Active Directory**, fare clic con il pulsante destro del mouse sul contenitore di sistema di dominio che contiene gli account di computer wireless e scegliere **Proprietà**.
  
3.  Nella scheda **Criteri di gruppo**, fare clic sull'oggetto Criteri di gruppo appropriato (l'oggetto predefinito è **Criterio dominio predefinito**), quindi fare clic su **Modifica**.
  
4.  Nella struttura console, aprire **Configurazione computer**, **Impostazioni di Windows**, **Impostazioni protezione** e **Criteri di rete senza fili (IEEE 802.11)**.
  
5.  Fare clic con il pulsante destro del mouse su **Criteri di rete senza fili (IEEE 802.11)** quindi scegliere **Crea criterio rete senza fili**. Nella Creazione guidata criterio rete senza fili, digitare un nome e una descrizione.
  
6.  Nel riquadro dettagli, fare doppio clic sul criterio di rete wireless creato.
  
7.  Modificare le impostazioni nella scheda **Generale** come necessario.
  
8.  Fare clic sulla scheda **Reti preferite**. Scegliere **Aggiungi** per aggiungere una rete preferita.
  
9.  Nella scheda **Proprietà di rete**, digitare il nome della rete wireless (SSID) e modificare le impostazioni principali della rete wireless secondo necessità.
  
10. Fare clic sulla scheda **IEEE 802.1x**. Modificare le impostazioni 802.1X come si desidera, specificando e configurando il tipo di EAP corretto. Scegliere **OK** per salvare le modifiche.
  
La prossima volta che i computer client wireless Windows XP con SP1, Windows XP con SP2 e Windows Server 2003 aggiorneranno i Criteri di gruppo di configurazione del computer, la loro configurazione di rete wireless verrà effettuata automaticamente.
  
##### Criteri di gruppo wireless e WPA
  
La versione dell'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) di Windows Server 2003 senza service pack installati non supporta la configurazione di impostazioni di autenticazione WPA e le impostazioni di crittografia per i computer client wireless Windows WPA. Il supporto per le impostazioni WPA configurato tramite l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) è stato aggiunto a Windows Server 2003 sia tramite Windows Server 2003 SP1 o tramite l'[aggiornamento 811233](http://support.microsoft.com/default.aspx?scid=kb;en-us;811233).
  
Per ottenere la nuova estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) in un dominio Active Directory di Windows 2000, tuttavia, lo schema di Active Directory deve essere aggiornato per includere la nuova estensione. Per aggiornare lo schema di Active Directory Windows 2000, occorre installare almeno un controller di dominio nel dominio di Active Directory Windows 2000 in cui è in esecuzione Windows Server 2003 senza service pack installati o Windows Server 2003 con SP1 (per le impostazioni di autenticazione e crittografia WPA). Al termine, utilizzare lo snap-in Criteri di gruppo da qualunque computer membro del dominio in cui è in esecuzione Windows Server 2003 senza service pack installati o Windows Server 2003 con SP1, per configurare le impostazioni Criteri di rete wireless (IEEE 802.11).
  
##### Criteri di gruppo wireless e WPA2
  
Per configurare le impostazioni di autenticazione WPA2 per i computer client wireless in cui è in esecuzione Windows XP con SP2 utilizzando l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11), i computer client devono essere membri di un dominio Active Directory di Windows Server 2003 e avere installato l'[aggiornamento relativo a client wireless per Windows XP con Service Pack 2](http://support.microsoft.com/?kbid=917021). Le impostazioni di autenticazione WPA2 nell'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) devono essere configurate dallo snap-in Editor oggetti Criteri di gruppo su un computer in cui è in esecuzione Windows Vista™ o Windows Server "Longhorn" (adesso in Beta testing).
  
Per un esempio di configurazione in ambiente di test, vedere [Guida alla valutazione delle reti wireless per Windows Vista](http://go.microsoft.com/fwlink/?linkid=79943).
  
Le impostazioni di autenticazione WPA2 configurate in questa maniera per i computer client wireless Windows XP con SP2 si applicano anche ai computer client wireless Windows Vista.
  
##### Criteri avanzati di gruppo wireless di Windows Vista
  
Windows Vista supporta una serie migliorata di impostazioni dei criteri di gruppo wireless progettate per essere usate da Windows Vista e dai computer client wireless di Windows Server "Longhorn". Windows Vista supporta sia le impostazioni dei criteri di gruppo basate su Windows XP che le impostazioni dei criteri di gruppo basate su Windows Vista. Le impostazioni dei criteri di gruppo basate su Windows Vista includono la capacità di configurare profili multipli e il loro ordine, elenchi di reti wireless che possono essere abilitate o meno e impostazioni Single Sign-On. Quando sono configurati entrambi i tipi di impostazioni wireless, i computer client wireless Windows Vista utilizzano le impostazioni di Windows Vista. Se le impostazioni wireless di Windows Vista non sono configurate, i computer client wireless Windows Vista utilizzano le impostazioni wireless di Windows XP.
  
Le impostazioni wireless basate su Windows Vista possono essere configurate in un dominio di Active Directory di Windows Server "Longhorn" utilizzando lo snap-in Editor oggetti Criteri di gruppo da un computer in cui è in esecuzione Windows Vista o Windows Server "Longhorn". Windows Server "Longhorn", tuttavia, è attualmente in fase di Beta test.
  
Per configurare e utilizzare le impostazioni wireless basate su Windows Vista in un dominio di Active Directory di Windows Server 2003, occorre estendere lo schema di Active Directory di Windows Server 2003 per supportare le nuove impostazioni wireless basate su Windows Vista. Per ulteriori informazioni e il file di estensione di directory, vedere [Active Directory Schema Extensions for Windows Vista Wireless and Wired Group Policy Enhancements](http://www.microsoft.com/technet/network/wifi/vista_ad_ext.mspx) (in inglese). Dopo aver esteso lo schema, configurare le impostazioni wireless basate su Windows Vista dallo snap-in Editor oggetti Criteri di gruppo su un computer in cui è in esecuzione Windows Vista o Windows Server "Longhorn".
  
Per un esempio di configurazione in ambiente di test, vedere [Guida alla valutazione delle reti wireless per Windows Vista](http://go.microsoft.com/fwlink/?linkid=79943).
  
#### Passaggio 7: installare i certificati di computer sui computer client wireless per EAP-TLS
  
Per l'autenticazione di un computer con EAP-TLS, occorre installare un certificato di computer sul computer client wireless.
  
Per installare un certificato di computer su un computer client wireless in cui è in esecuzione Windows Server 2003, Windows XP, o Windows 2000, connettersi all'Intranet dell'organizzazione utilizzando una porta Ethernet e procedere come segue:
  
-   Dopo che il dominio è stato configurato per la registrazione automatica dei certificati di computer, ogni computer membro del dominio richiede un certificato di computer quando i Criteri di gruppo del computer vengono aggiornati. Per forzare un aggiornamento di Criteri di gruppo di computer per un computer in cui è in esecuzione Windows Server 2003 o Windows XP, riavviare il computer o digitare **gpupdate /target:computer** al prompt dei comandi. Per forzare un aggiornamento di Criteri di gruppo di computer per un computer in cui è in esecuzione Windows 2000, riavviare il computer o digitare **secedit /refreshpolicy machine\_policy** al prompt dei comandi.
  
-   Se il dominio non è configurato per la registrazione automatica, è possibile richiedere un certificato "Computer" utilizzando lo snap-in Certificati oppure eseguire uno script CAPICOM per installare un certificato di computer.
  
In una grande organizzazione, il reparto IT può installare un certificato di computer ancora prima che il computer, generalmente un computer portatile, sia consegnato all'utente.
  
Per informazioni su CAPICOM, cercare "CAPICOM" all'indirizzo [http://msdn.microsoft.com/](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/security/security/using_capicom.asp).
  
#### Passaggio 8: installare i certificati utente sui computer client wireless per EAP-TLS
  
Per l'autenticazione utente con EAP-TLS, occorre utilizzare un certificato utente installato localmente o una smart card. Il certificato utente installato localmente deve essere ottenuto tramite registrazione automatica, registrazione Web, richiedendo il certificato tramite lo snap-in Certificati, importando un file di certificato, oppure eseguendo un programma o uno script CAPICOM.
  
I metodi i più semplici per installare certificati utente presuppongono che esista già la connettività di rete, come quando si usa una porta Ethernet. Quando l'utente si collega a Intranet, può ottenere un certificato utente tramite la registrazione automatica o inviando una richiesta di certificato utente tramite registrazione Web o Gestione certificati. Per ulteriori informazioni su come richiedere un certificato utente, vedere le procedure "Inviare una richiesta di certificato utente tramite Web" e "Richiedere un certificato" in questa sezione.
  
In alternativa, l'utente può eseguire il programma o lo script CAPICOM forniti dall'amministratore di rete. L'esecuzione del programma o dello script CAPICOM può essere automatizzata tramite lo script di accesso utente.
  
Se è stata configurata la registrazione automatica dei certificati utente, per ottenere un certificato utente l'utente wireless deve aggiornare i Criteri di gruppo di configurazione utente.
  
Se non si utilizza la registrazione automatica per i certificati utente, attenersi a una delle procedure seguenti per ottenere un certificato utente.
  
**Inviare una richiesta di certificato utente tramite Web**
  
1.  Aprire Internet Explorer.
  
2.  In Internet Explorer, connettersi a **http://***nomeserver/***certsrv**, dove *nomeserver* è il nome del server Web Windows 2000 dove si trova l'autorità di certificazione a cui si vuole accedere.
  
3.  Scegliere **Richiedi un certificato** e **Avanti**.
  
4.  Nella pagina Web **Choose Request Type** (Scelta tipo di richiesta), in **User certificate request** (Richiesta certificato utente), scegliere il tipo di certificato che si vuole richiedere e fare clic su **Avanti**.
  
5.  Dalla pagina Web **Dati di identificazione** scegliere uno dei due modi seguenti:
  
    Se appare un messaggio che avverte che tutte le informazioni di identificazione necessarie sono state raccolte e che adesso è possibile inviare la richiesta, scegliere **Invia**.
  
    Inserire le informazioni di identificazione per la richiesta di certificato e scegliere **Invia**.
  
6.  Se appare la pagina **Certificato emesso**, scegliere **Installa questo certificato**.
  
7.  Chiudere Internet Explorer.
  
**Richiedere un certificato**
  
1.  Aprire una console MMC che contiene **Certificati – Utente corrente**.
  
2.  Nella struttura console, fare clic con il pulsante destro del mouse su **Personale**, scegliere **Tutte le attività** e quindi **Richiesta nuovo certificato** per avviare la Richiesta guidata certificato.
  
3.  Nella Richiesta guidata certificato, scegliere le informazioni seguenti:
  
    Il tipo di certificato che si vuole richiedere.
  
    Se si è scelta la casella di controllo **Avanzate**:
  
    -   Il provider del servizio di crittografia (CSP) utilizzato.
  
    -   La lunghezza della chiave (in bit) per la chiave pubblica associata al certificato.
  
    -   Non abilitare la protezione avanzata chiave privata.
  
    -   Se si ha a disposizione più di un'autorità di certificazione, scegliere il nome dell'autorità di certificazione che emetterà il certificato.
  
4.  Digitare un nome descrittivo per il nuovo certificato.
  
5.  Dopo che la Richiesta guidata certificato è terminata senza errori, scegliere **OK**.
  
##### Installazione da disco floppy
  
Un altro metodo per installare un certificato utente è esportare il certificato utente in un dischetto e importarlo dal dischetto nel computer client wireless. Per una registrazione da disco floppy, procedere come segue:
  
1.  Ottenere un certificato utente per l'account utente del computer client wireless dall'autorità di certificazione tramite registrazione Web. Per ulteriori informazioni, vedere la procedura "Inviare una richiesta di certificato utente tramite Web" precedentemente descritta.
  
2.  Esportare il certificato utente dell'account utente del computer client wireless in un file pfx. Per ulteriori informazioni, vedere la procedura "Esportare un certificato" in questa sezione. In Esportazione guidata certificati di Gestione certificati, esportare la chiave privata e selezionare **Elimina la chiave privata se l'esportazione ha esito positivo**. Salvare questo file in un dischetto e consegnarlo all'utente del computer client wireless.
  
3.  Sul computer client wireless, importare il certificato utente. Per ulteriori informazioni, vedere la procedura "Importare un certificato" in questa sezione.
  
**Esportare un certificato**
  
1.  Aprire una console di MMC che contiene **Certificati - Utente corrente**.
  
2.  Aprire **Personale** e quindi **Certificati**.
  
3.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse sul certificato che si vuole esportare, scegliere **Tutte le attività** e fare clic su **Esporta**.
  
4.  In Esportazione guidata certificati, fare clic su **Esporta la chiave privata**. Questa opzione apparirà soltanto se la chiave privata è contrassegnata come esportabile e si ha accesso alla chiave privata. Scegliere **Avanti**.
  
5.  Scegliere **Scambio di informazioni personali – PKCS (.PFX )** come formato del file di esportazione e fare clic su **Avanti**.
  
6.  Nella pagina **Password**, digitare una password in **Password** e in **Conferma la password** per proteggere la chiave privata nel certificato, quindi scegliere **Avanti**.
  
7.  Nella pagina **File da esportare**, digitare il nome del file di certificato o fare clic su **Sfoglia** per specificare il nome e la posizione del file di certificato. Scegliere **Avanti**.
  
8.  Nella pagina **Completamento dell'Esportazione guidata certificati** scegliere **Fine**.
  
**Importare un certificato**
  
1.  Aprire una console di MMC che contiene **Certificati - Utente corrente**.
  
2.  Aprire **Personale** e quindi **Certificati**.
  
3.  Nel riquadro dettagli, fare clic con il pulsante destro del mouse sul certificato che si vuole esportare, scegliere **Tutte le attività** e fare clic su **Importa**.
  
4.  Digitare il nome del file che contiene il certificato da importare (oppure fare clic su **Sfoglia** per cercare il file).
  
5.  Se il file è PKCS \#12, procedere come segue:
  
    Digitare la password utilizzata per crittografare la chiave privata.
  
    (Facoltativo) Se si vuole essere in grado di utilizzare la protezione avanzata chiave privata, selezionare la casella di controllo **Abilita protezione avanzata chiave privata**.
  
    (Facoltativo) Se si vuole eseguire un backup o trasferire le chiavi successivamente, selezionare la casella di controllo **Contrassegna la chiave come esportabile**.
  
6.  Eseguire una delle operazioni seguenti:
  
    Se il certificato deve essere collocato automaticamente in un archivio certificati in base al tipo di certificato, scegliere **Selezionare automaticamente l'archivio certificati secondo il tipo di certificato**.
  
    Se si vuole specificare dove il certificato deve essere memorizzato, scegliere **Mettere tutti i certificati nel seguente archivio**, fare clic su **Sfoglia** e selezionare l'archivio certificati da utilizzare.
  
#### Passaggio 9: configurare i computer client wireless per EAP-TLS
  
Se si sono configurate le impostazioni Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) e si è specificato l'uso dell'autenticazione EAP-TLS (il tipo EAP **Smart Card o altro certificato**) per la rete wireless, non è richiesta nessuna altra configurazione per i computer client wireless in cui è in esecuzione Windows XP con SP1, Windows XP con SP2 o Windows Server 2003.
  
Per configurare manualmente l'autenticazione EAP-TLS su un computer client wireless in cui è in esecuzione Windows XP con SP1, Windows XP con SP2 o Windows Server 2003, procedere come segue:
  
1.  Ottenere le proprietà della connessione wireless nella cartella Connessioni di rete. Fare clic sulla scheda **Reti senza fili** quindi scegliere il nome della rete wireless nell'elenco di reti preferite e face clic su **Proprietà**.
  
2.  Fare clic sulla scheda **Autenticazione** e selezionare **Abilita controllo accesso alla rete mediante IEEE 802.1X** e il tipo EAP **Smart Card o altro certificato**. Quest'ultimo è attivato per impostazione predefinita.
  
3.  Scegliere **Proprietà**. Nelle proprietà del tipo EAP **Smart Card o altro certificato**, scegliere **Utilizza un certificato su questo computer** per utilizzare un certificato utente basato sul Registro di sistema o **Utilizza la smart card** per un certificato utente basato su smart card.
  
    Se si vuole convalidare il certificato di computer del server IAS, selezionare **Convalida certificato server** (attivato per impostazione predefinita). Se si vuole specificare i nomi dei server di autenticazione che devono eseguire la convalida, selezionare **Connetti ai server seguenti** e digitare i nomi.
  
4.  Scegliere **OK** per salvare le modifiche al tipo EAP Smart Card o altro tipo di certificato.
  
Per configurare l'autenticazione EAP-TLS su un computer client wireless in cui è in esecuzione Windows XP senza service pack installati, procedere come segue:
  
1.  Ottenere le proprietà della connessione wireless nella cartella Connessioni di rete. Fare clic sulla scheda **Autenticazione** e selezionare **Abilita controllo accesso alla rete mediante IEEE 802.1X** e il tipo EAP **Smart Card o altro certificato**. Quest'ultimo è attivato per impostazione predefinita.
  
2.  Scegliere **Proprietà**. Nelle proprietà del tipo EAP **Smart Card o altro certificato**, scegliere **Utilizza un certificato su questo computer**.
  
    Se si vuole convalidare il certificato di computer del server IAS, selezionare **Convalida certificato server** (attivato per impostazione predefinita).
  
    Per assicurarsi che il nome del server DNS termini con una stringa specifica, selezionare **Connetti soltanto se il nome del server finisce con** e digitare la stringa. Per le distribuzioni tipiche dove si utilizza più di un server IAS, digitare la parte del nome DNS che è comune a tutti i server IAS. Per esempio, se si hanno due server IAS chiamati IAS1.example.microsoft.com e IAS2.example.microsoft.com, digitare la stringa "example.microsoft.com". Assicurarsi di digitare la stringa corretta, altrimenti l'autenticazione non riesce.
  
3.  Scegliere **OK** per salvare le modifiche al tipo EAP Smart Card o altro certificato.
  
Per configurare l'autenticazione EAP-TLS su un computer client wireless in cui è in esecuzione Windows 2000 SP4, procedere come segue:
  
1.  Ottenere le proprietà della connessione wireless nella cartella Connessioni remote e di rete. Fare clic sulla scheda **Autenticazione** e selezionare **Abilita controllo accesso alla rete mediante IEEE 802.1X** e il tipo EAP **Smart Card o altro certificato**. Quest'ultimo è attivato per impostazione predefinita.
  
2.  Scegliere **Proprietà**. Nelle proprietà del tipo EAP **Smart Card o altro certificato**, scegliere **Utilizza un certificato su questo computer** per utilizzare un certificato utente basato sul Registro di sistema o **Utilizza la smart card** per un certificato utente basato su smart card.
  
    Se si vuole convalidare il certificato di computer del server IAS, selezionare **Convalida il certificato server** (attivato per impostazione predefinita). Se si vuole specificare i nomi dei server di autenticazione che devono eseguire la convalida, selezionare **Connetti ai server seguenti** e digitare i nomi.
  
3.  Scegliere **OK** per salvare le modifiche al tipo EAP Smart Card o altro certificato.
  
#### Passaggio 10: configurare i computer client wireless per PEAP-MS-CHAP v2
  
Se si sono configurate le impostazioni Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) e si è specificato l'utilizzo dell'autenticazione PEAP-MS-CHAP v2 per la rete wireless (il tipo **PEAP (Protected EAP)**) con metodo di autenticazione **Password protetta (EAP-MSCHAP v2)**), non sono necessarie altre configurazioni per i computer client wireless in cui è in esecuzione Windows XP con SP1, Windows XP con SP2 o Windows Server 2003.
  
Per configurare manualmente l'autenticazione PEAP-MS-CHAP v2 su un computer client wireless in cui è in esecuzione Windows XP con SP1, Windows XP con SP2 o Windows Server 2003, procedere come segue:
  
1.  Ottenere le proprietà della connessione wireless nella cartella Connessioni di rete. Fare clic sulla scheda **Reti senza fili**, poi fare clic sul nome della rete wireless nell'elenco di reti preferite e fare clic su **Proprietà**.
  
2.  Fare clic sulla scheda **Autenticazione** e selezionare **Attiva il controllo di accesso alla rete utilizzando IEEE 802.1X** e il tipo EAP **PEAP (Protected EAP)**.
  
3.  Scegliere **Proprietà**. Nella finestra di dialogo di **Proprietà PEAP**, scegliere **Convalida certificato server** per convalidare il certificato di computer del server IAS (attivato per impostazione predefinita). Se si vuole specificare i nomi dei server di autenticazione che devono eseguire la convalida, selezionare **Connetti ai server seguenti** e digitare i nomi. In **Selezionare il metodo di autenticazione**, fare clic su **Password protetta (EAP-MSCHAP v2)**.
  
Per configurare l'autenticazione PEAP-MS-CHAP v2 su un computer client wireless in cui è in esecuzione Windows 2000 SP4, procedere come segue:
  
1.  Ottenere le proprietà della connessione wireless nella cartella Connessioni remote e di rete.
  
2.  Fare clic sulla scheda **Autenticazione** e selezionare **Abilita controllo accesso alla rete mediante IEEE 802.1X** e il tipo EAP **PEAP (Protected EAP)**.
  
3.  Scegliere **Proprietà**. Nella finestra di dialogo di **Proprietà PEAP**, scegliere **Convalida certificato server** per convalidare il certificato di computer del server IAS (attivato per impostazione predefinita). Se si vuole specificare i nomi dei server di autenticazione che devono eseguire la convalida, selezionare **Connetti a questi server** e digitare i nomi. In **Selezionare il metodo di autenticazione**, fare clic su **Password protetta (EAP-MSCHAP v2)**.
  
    **Nota** Per impostazione predefinita, l'autenticazione PEAP-MS-CHAP v2 utilizza le credenziali di accesso Windows per l'autenticazione wireless. Se ci si connette a una rete wireless che utilizza PEAP-MS-CHAP v2 e si vogliono specificare credenziali diverse, scegliere **Configura** e deselezionare la casella di controllo **Utilizza automaticamente nome utente e password di Windows**.
  
    Sebbene la finestra di dialogo **Proprietà PEAP** per Windows XP con SP1, Windows XP con SP2, Windows Server 2003 e Windows 2000 SP4 abbia una casella di controllo **Abilita riconnessione rapida**, IAS per Windows 2000 non supporta la riconnessione rapida. IAS per Windows Server 2003 supporta la riconnessione rapida.
  
Se il certificato di autorità di certificazione radice che ha emesso i certificati di computer installati sui server IAS è già installato come certificato di autorità di certificazione radice su un computer client wireless, non sono necessarie altre configurazioni. Se l'autorità di certificazione di emissione è un'autorità di certificazione radice globale in linea di Windows 2000 Server o Windows Server 2003, ne consegue che il certificato di autorità di certificazione radice è automaticamente installato su ogni membro di dominio tramite i Criteri di gruppo di configurazione del computer.
  
Come verifica, ottenere le proprietà del certificato di computer sul server IAS utilizzando lo snap-in Certificati e vedere la catena di certificati nella scheda **Percorso certificazione**. Il certificato al primo posto del percorso è il certificato di autorità di certificazione radice. Utilizzare lo snap-in Certificati di un computer client wireless per ogni sistema operativo Windows per assicurarsi che il certificato sia nell'elenco delle Autorità di certificazione principale attendibili nella cartella Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati.
  
Se non c'è, occorre installare il certificato (o i certificati) di autorità di certificazione radice di emissione (delle autorità di emissione) dei certificati di computer dei server IAS su ogni computer client wireless per i sistemi operativi Windows che non li hanno.
  
Il modo più semplice di installare un certificato radice di autorità di certificazione su tutti i computer client wireless è il seguente:
  
1.  Utilizzare lo snap-in Certificati su un server IAS per esportare in un file il certificato di autorità di certificazione radice dell'autorità di certificazione di emissione di certificati di computer sui server IAS (\*.PB7). È possibile trovare il certificato di autorità di certificazione radice nella cartella Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati.
  
2.  Aprire lo snap-in Utenti e computer di Active Directory.
  
3.  Nella struttura console, fare doppio clic su **Utenti e computer di Active Directory**, fare clic con il pulsante destro del mouse sul contenitore di sistema del dominio appropriato e scegliere **Proprietà**.
  
4.  Nella scheda **Criteri di gruppo**, fare clic sull'oggetto Criteri di gruppo appropriato (l'oggetto predefinito è **Criterio dominio predefinito**), quindi scegliere **Modifica**.
  
5.  Nella struttura console, aprire **Configurazione computer**, quindi **Impostazioni di Windows**, **Impostazioni protezione** e **Criteri chiave pubblica**.
  
6.  Fare clic con il pulsante destro del mouse su **Autorità di certificazione principale attendibili** quindi scegliere **Importa**.
  
7.  In Importazione guidata certificati, specificare il file che è stato salvato nel passaggio 1.
  
8.  Ripetere i passaggi 3-7 per tutti i contenitori di sistema appropriati.
  
La volta successiva che i Criteri di gruppo di configurazione del computer verranno aggiornati dai computer client wireless, il certificato di autorità di certificazione radice della autorità di certificazione di emissione di certificati di computer sui server IAS sarà installato nell'archivio certificati di computer locale.
  
In alternativa, è possibile utilizzare lo snap-in Certificati per importare i certificati di autorità di certificazione radice nella cartella Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati su ogni computer client wireless.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazioni aggiuntive di distribuzione wireless Intranet
  
Nella sezione sono descritte le seguenti configurazioni aggiuntive di distribuzione wireless Intranet:
  
-   Accesso Internet per partner commerciali
  
-   Utilizzo di autorità di certificazione di terze parti
  
-   Autenticazione tra foreste
  
-   Utilizzo dei proxy RADIUS per autenticazioni di scala
  
#### Accesso Internet per partner commerciali
  
Di seguito si descrive il comportamento della maggior parte dei punti di accesso wireless attualmente in uso in riferimento alla ricezione di messaggi RADIUS di autorizzazione e rifiuto di accesso:
  
-   Quando il punto di accesso wireless riceve un messaggio di autorizzazione di accesso, la connessione è consentita.
  
-   Quando il punto di accesso wireless riceve un messaggio di rifiuto di accesso, la connessione è negata.
  
Per consentire che un partner commerciale, un fornitore, o un altro che non sia un dipendente di avere accesso a una rete separata utilizzando la stessa infrastruttura wireless che consente ai dipendenti di accedere al server Intranet dell'organizzazione, alla richiesta di connessione deve essere restituito un messaggio di autorizzazione di accesso dal server RADIUS. Per ottenere un messaggio di autorizzazione di accesso dal server RADIUS, occorre utilizzare l'accesso come utente ospite oppure il partner commerciale, il fornitore, o un altro non dipendente devono avere un account e certificati validi.
  
##### Utilizzo dell'accesso come utente ospite
  
L'accesso come utente ospite si utilizza quando i computer client wireless si connettono senza inviare un'identità utente. Il computer client wireless non fornisce un nome utente o credenziali al punto di accesso wireless. Il punto di accesso wireless non include, pertanto, nel messaggio di richiesta di accesso l'identità utente (l'attributo Nome utente) o gli attributi di credenziali. Quando riceve un messaggio di richiesta di accesso che non contiene attributi di identità utente o credenziali, il server IAS verifica se l'accesso non autenticato è abilitato per il criterio di accesso remoto che corrisponde al tentativo di connessione. Se non è incluso un attributo di identità utente, il server IAS utilizza l'account Ospite per ottenere le proprietà di connessione remota dell'account utente e l'appartenenza al gruppo. Se un attributo di identità utente è contenuto ma gli attributi di credenziale non sono presenti, il server IAS utilizza l'account indicato per ottenere le proprietà di connessione remota dell'account utente e l'appartenenza al gruppo.
  
L'accesso limitato alla rete per i computer client con accesso come utente ospite è supportato sui punti di accesso wireless tramite filtraggio IP o VLAN. Per specificare un identificatore di LAN virtuale per l'accesso non autenticato, configurare gli attributi Tunnel-Type e Tunnel-Pvt-Group-ID nelle proprietà avanzate dei criteri di accesso remoto appropriati.
  
Per ulteriori informazioni su accessi non autenticati e accesso come utente ospite con IAS, vedere la Guida Windows 2000 Server o la Guida e supporto tecnico Windows Server 2003.
  
##### Utilizzo dell'accesso convalidato
  
Per l'accesso convalidato per i partner commerciali, i fornitori, o altri non dipendenti, si devono creare gli account computer e gli account utente e emettere certificati per ogni partner commerciale, ogni fornitore o ogni altro non dipendente. Quindi creare gruppi con questi account come membri in modo che si possano gestire gli accessi utilizzando criteri di accesso remoto di gruppo. Ad esempio, creare un gruppo WirelessInternetUsers che contiene gruppi globali di partner commerciali, fornitori, o account computer o utente di altri non dipendenti.
  
Per configurare uni criterio di accesso remoto wireless per l'accesso Internet per i partner commerciali, i fornitori, o altri non dipendenti, creare un nuovo criterio personalizzato di accesso remoto per l'accesso wireless Internet con le impostazioni seguenti:
  
-   Nome criterio: Accesso wireless Internet (esempio)
  
-   Condizioni: NAS-Port-Type=Wireless-Other o Wireless-IEEE 802.11, Windows-Groups=WirelessInternetUsers
  
-   Autorizzazioni: Selezionare **Consenti l'accesso remoto**.
  
-   Profilo, scheda **Autenticazione**: Per IAS per Windows 2000, scegliere **Extensible Authentication Protocol** e il tipo EAP **Smart Card o altro certificato**. Deselezionare tutte le altre caselle di controllo. Se si hanno certificati di computer multipli installati sul server IAS, fare clic su **Configura** quindi scegliere il certificato di computer appropriato.
  
    Per IAS di Windows Server 2003, deselezionare tutte le altre caselle di controllo. Scegliere **Metodi EAP** e aggiungere il tipo EAP **Smart Card o altro certificato**. Se si hanno certificati di computer multipli installati sul server IAS, fare clic su **Modifica** quindi scegliere il certificato di computer appropriato.
  
-   Profilo, scheda **Crittografia**: Se il punto di accesso wireless supporta gli attributi RADIUS MS-MPPE-Encryption-Policy e MS-MPPE-Encryption-Types, deselezionare tutte le altre caselle di controllo tranne **Livello massimo**. In tal modo si forzano tutte le connessioni wireless a utilizzare la crittografia a 128 bit. Se questi attributi non sono supportati, deselezionare tutte le caselle di controllo eccetto **Senza crittografia**.
  
-   Profilo, scheda **Avanzate** (se il punto di accesso wireless supporta VLAN):
  
    -   Aggiungere l'attributo Tunnel-Type con valore di "Virtual LANs (VLAN)".
  
    -   Aggiungere l'attributo Tunnel-Pvt-Group-ID con il valore VLAN ID della VLAN che è connessa a Internet.
  
    Se i punti di accesso wireless richiedono attributi specifici del fornitore (VSA), si devono aggiungere gli attributi VSA agli opportuni criteri di accesso remoto. Per ulteriori informazioni, vedere la procedura "Configurare gli attributi specifici del fornitore per un criterio di accesso remoto" descritta in precedenza.
  
#### Utilizzo di autorità di certificazione di terze parti
  
È possibile utilizzare autorità di certificazione di terze parti per emettere i certificati per l'accesso wireless a patto che i certificati installati possano essere convalidati e abbiano le proprietà necessarie.
  
##### Certificati sui server IAS
  
Per i certificati di computer installati sui server IAS, deve essere verificato quanto segue:
  
-   Devono essere installati nell'archivio certificati del computer locale.
  
-   Devono avere una corrispondente chiave privata. Quando si visualizzano le proprietà del certificato con lo snap-in Certificati, nella scheda **Generale** si dovrebbe vedere il testo **L'utente possiede una chiave privata corrispondente al certificato**.
  
-   Il provider del servizio di crittografia per i certificati supporta SChannel. In caso contrario, il server IAS non può utilizzare il certificato e non è selezionabile dalle proprietà del tipo EAP **Smart Card o altro certificato** nella scheda **Autenticazione** nelle proprietà di un profilo per un criterio di accesso remoto.
  
-   Devono contenere lo scopo del certificato di autenticazione server (noto anche come Enhanced Key Usage, EKU). Un EKU è identificato utilizzando un identificatore di oggetto (OID). L'OID per l'autenticazione server è "1.3.6.1.5.5.7.3.1".
  
-   Devono contenere il nome di dominio completo (FQDN) dell'account computer del server IAS nella proprietà Nome alternativo soggetto.
  
Inoltre, i certificati di autorità di certificazione radice delle autorità di certificazione che hanno emesso i certificati utente e computer del computer client wireless devono essere installati nella cartella Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati.
  
##### Certificati sul computer client wireless
  
Per i certificati utente e computer installati sul computer client wireless, deve essere verificato quanto segue:
  
-   Devono avere una corrispondente chiave privata.
  
-   Devono contenere l'EKU di autenticazione client (OID "1.3.6.1.5.5.7.3.2")
  
-   I certificati di computer devono essere installati nell'archivio certificati del computer locale.
  
-   I certificati di computer devono contenere il nome di dominio completo dell'account del computer client wireless nella proprietà Nome alternativo soggetto.
  
-   I certificati utente devono essere installati nell'archivio certificati di Utente corrente.
  
-   I certificati utente devono contenere il nome universale principale (UPN) dell'account utente nella proprietà Nome alternativo soggetto.
  
Inoltre, i certificati di autorità di certificazione radice delle autorità di certificazione che hanno emesso i certificati di computer del server IAS devono essere installati nella cartella Certificati (computer locale)\\Autorità di certificazione principale attendibili\\Certificati oppure nella cartella Certificati (Utente corrente)\\Autorità di certificazione principale attendibili\\Certificati.
  
#### Configurare le impostazioni del server proxy
  
I certificati emessi dalle autorità di certificazione di terze parti, come VeriSign, Inc., possono contenere un URL Elenco di revoche di certificati (CRL) che punta a un sito Web Internet. Se il server IAS non è in grado di raggiungere il sito Web per eseguire la verifica delle revoche di certificati, non convalida i certificati del computer client wireless per l'autenticazione EAP-TLS.
  
In varie organizzazioni, per accedere a Internet nelle reti viene utilizzato un server proxy, come Microsoft Internet Security and Acceleration Server (ISA). La configurazione delle impostazioni del server proxy è di solito effettuata tramite le opzioni Dynamic Host Configuration Protocol (DHCP). Molti server IAS, tuttavia, hanno una configurazione di indirizzo IP statico e quindi potrebbero non essere configurati con le impostazioni di server proxy appropriate per accedere a Internet. Il risultato è che i server IAS non possono eseguire il controllo della revoca del certificato per un certificato del computer locale o per i certificati del computer client wireless e l'autenticazione può non riuscire per tutte le connessioni wireless.
  
Per configurare un server IAS con le opportune impostazioni di server proxy in modo che possa accedere a Internet, procedere come segue:
  
1.  Sul server IAS, accedere utilizzando un account che abbia le autorizzazioni di amministratore locale.
  
2.  Aprire un prompt dei comandi.
  
3.  Al prompt dei comandi digitare **time** e premere INVIO.
  
4.  Al prompt **Immettere nuova ora:** premere INVIO.
  
5.  Al prompt dei comandi, digitare **at***\[ora+1 minuto*\]**/interactive "cmd.exe"** e premere INVIO. Ad esempio, se l'ora attuale dal passaggio 4 è 13:31, il comando è **at 13:32/interactive"cmd.exe"**.
  
6.  Dopo un minuto, si apre un nuovo prompt dei comandi. I comandi eseguiti da questo prompt vengono eseguiti nel contesto di protezione del sistema locale. Anche IAS viene eseguito nel contesto di protezione del sistema locale. Per tale motivo, occorre configurare le impostazioni del server proxy dal contesto di protezione del sistema locale in modo che si applichino a IAS. In caso contrario, le impostazioni del server proxy si applicano soltanto all'account utente che è stato utilizzato per l'accesso al server IAS nel passaggio 1.
  
7.  Dal nuovo prompt dei comandi, digitare **“%programfiles%\\Internet Explorer\\Iexplore.exe”** (comprese le virgolette) e premere INVIO. In tal modo si apre Internet Explorer nel contesto di protezione di sistema locale.
  
8.  Scegliere **Strumenti**, quindi scegliere **Opzioni Internet**.
  
9.  Fare clic sulla scheda **Connessioni** e scegliere **Impostazioni LAN**.
  
10. In **Server proxy**, selezionare **Utilizza un server proxy per le connessioni LAN**.
  
11. Digitare il nome o l'indirizzo IP del server proxy in **Indirizzo**, quindi digitare il numero di porta Web (generalmente 80) in **Porta**. Ad esempio, se il nome del server proxy è CorpProxy e si utilizza la porta 80 per il traffico Web, digitare **corpproxy** in **Indirizzo** e **80** in **Porta**.
  
12. Scegliere **OK** per salvare le impostazioni del server proxy.
  
13. Scegliere **OK** per chiudere la finestra di dialogo **Opzioni Internet**.
  
14. Chiudere Internet Explorer.
  
15. Chiudere il nuovo prompt dei comandi nuovo che è stato aperto nel passaggio 6.
  
Un altro modo di configurare le impostazioni del server proxy è utilizzare lo strumento ProxyCfg.exe dal prompt dei comandi aperto nel passaggio 6. ProxyCfg.exe è incluso in Windows Server 2003. Per una versione di ProxyCfg.exe che funzioni con Windows 2000 Server, vedere [830605 - Disponibilità dello strumento di configurazione Proxycfg.exe per WinHTTP 5.1](http://support.microsoft.com/default.aspx?scid=kb;en-us;830605). Per ulteriori informazioni su come utilizzare ProxyCfg.exe, vedere [ProxyCfg.exe, uno strumento di configurazione proxy](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/winhttp/http/proxycfg_exe__a_proxy_configuration_tool.asp) (la pagina potrebbe essere in inglese).
  
#### Autenticazione tra foreste
  
Poiché IAS utilizza Active Directory per convalidare le credenziali e ottenere le proprietà dell'account utente e computer, un proxy RADIUS deve essere collocato tra i punti di accesso wireless e i server IAS quando gli account utente e gli account di computer per i computer client wireless utente e computer esistono nei seguenti database di autenticazione:
  
-   Due foreste di Active Directory diverse.
  
-   Due domini diversi non reciprocamente attendibili.
  
-   Due domini diversi che hanno attendibilità unidirezionale.
  
La discussione seguente presuppone una configurazione tra più foreste.
  
Quando un computer client di accesso invia le credenziali utente, spesso è incluso un nome utente. Nel nome utente sono presenti due elementi:
  
-   identificazione del nome dell'account utente
  
-   identificazione della posizione dell'account utente
  
Ad esempio, per il nome utente user1@microsoft.com, user1 è il nome dell'account utente e microsoft.com è la posizione dell'account utente. L'identificazione della posizione dell'account utente è nota come area di autenticazione. Ci sono diverse forme di nomi dell'area di autenticazione:
  
-   Il nome dell'area di autenticazione può essere un prefisso.
  
    Per microsoft\\user1, "microsoft" è il nome di un dominio Windows NT® 4.0.
  
-   Il nome dell'area di autenticazione può essere un suffisso.
  
    Per user1@microsoft.com, microsoft.com è sia un nome di dominio DNS sia il nome di un dominio Active Directory.
  
    **Nota**  Non è necessario utilizzare un proxy RADIUS se si utilizza PEAP-MS-CHAP v2 e i nomi utente stile Windows NT 4.0 (ad esempio, microsoft\\user1).
  
Il nome utente è passato dal computer client wireless al punto di accesso wireless durante la fase di autenticazione del tentativo di connessione. Questo nome utente diventa l'attributo RADIUS User-Name nel messaggio di richiesta di accesso che è inviato dal punto di accesso wireless al server RADIUS configurato, che in questa configurazione è un proxy RADIUS. Quando il proxy RADIUS riceve il messaggio di richiesta di accesso, le regole configurate o i criteri sul proxy RADIUS determinano a quale server IAS viene inoltrato il messaggio di richiesta di accesso. Nella figura 2 vengono mostrati i proxy RADIUS IAS utilizzati per inoltrare i messaggi RADIUS tra i punti di accesso wireless e i server IAS multipli in due foreste di Active Directory diverse.
  
![](images/Bb457097.ed802102(it-it,TechNet.10).gif)
  
**Figura 2   Utilizzo dei proxy RADIUS IAS per l'autenticazione tra foreste**
  
La configurazione seguente è per un'organizzazione che utilizza:
  
-   Domini Active Directory.
  
    I domini Active Directory contengono gli account utente, le password e le proprietà delle connessioni remote che ogni server IAS richiede per autenticare le credenziali e valutare l'autorizzazione.
  
-   Almeno due server IAS in ogni foresta.
  
    Almeno due server IAS (uno primario e uno secondario) sono utilizzati per fornire la tolleranza all'errore per l'autenticazione RADIUS, l'autorizzazione e l'accounting in ogni foresta. Se fosse configurato un solo server RADIUS, in caso di momentanea non disponibilità di questo server i computer client con accesso per quella foresta non potrebbero connettersi. Se si utilizzano due server IAS e si configurano i proxy RADIUS IAS sia per il server IAS primario sia per quello secondario, i proxy RADIUS IAS possono rilevare quando il server RADIUS primario non è disponibile e automaticamente trasferirsi al server IAS secondario.
  
-   Criteri di accesso remoto.
  
    I criteri di accesso remoto sono configurati per specificare i diversi tipi di vincoli di connessione per gli utenti, in base all'appartenenza al gruppo.
  
-   Almeno due proxy RADIUS IAS.
  
    Almeno due proxy RADIUS IAS sono utilizzati per fornire la tolleranza di errore per le richieste RADIUS che sono inviate dai punti di accesso wireless.
  
Per configurare IAS per quest'esempio, completare i passaggi seguenti:
  
1.  Configurare le foreste di Active Directory per gli account e i gruppi.
  
2.  Configurare il server IAS primario su un computer nella prima foresta.
  
3.  Configurare il server IAS secondario su un altro computer nella prima foresta.
  
4.  Configurare il server IAS primario su un computer nella seconda foresta.
  
5.  Configurare il server IAS secondario su un altro computer nella seconda foresta.
  
6.  Configurare il proxy RADIUS IAS primario.
  
7.  Configurare il proxy RADIUS IAS secondario.
  
8.  Configurare l'autenticazione RADIUS e l'accounting per i punti di accesso wireless.
  
IAS per Windows 2000 non supporta il proxy RADIUS. È possibile, tuttavia, utilizzare IAS per Windows Server 2003 in modo che svolga la funzione di proxy RADIUS in questa configurazione. Per ulteriori informazioni, vedere l'argomento "Autenticazione tra foreste" nella Guida e supporto tecnico di Windows Server 2003.
  
##### Configurare le foreste di Active Directory per gli account e i gruppi.
  
Per configurare Active Directory per gli account utente e i gruppi, procedere come segue:
  
1.  Su ogni controller di dominio Windows 2000, installare Windows 2000 SP4.
  
2.  Assicurarsi che tutti gli utenti che usano connessioni wireless abbiano il corrispondente account utente. Assicurarsi che tutti i computer che effettuano connessioni wireless abbiano il corrispondente account di computer.
  
3.  Impostare l'autorizzazione all'accesso remoto per gli account utente e computer nel modo opportuno.
  
4.  Organizzare gli account nei gruppi appropriati per approfittare dei criteri di accesso remoto basati sui gruppi.
  
##### Configurare il server IAS primario su un computer nella prima foresta.
  
Per configurare il server IAS primario su un computer nella prima foresta, procedere come segue:
  
1.  Se si utilizza IAS per Windows 2000, installare IAS come componente di rete facoltativo su un computer nella prima foresta, quindi installare Windows 2000 SP4. Se si utilizza IAS per Windows Server 2003, installare IAS come componente di rete facoltativo su un computer nella prima foresta.
  
2.  Quindi configurare il server IAS per leggere le proprietà degli account utente nel dominio.
  
3.  Se il server IAS autentica i tentativi di connessione wireless per gli account utente negli altri domini, verificare che gli altri domini abbiano un trust bidirezionale col dominio di cui il server IAS è membro, quindi configurare il server IAS per leggere le proprietà degli account utente negli altri domini.
  
4.  Se necessario, attivare la registrazione per gli eventi di accounting e autenticazione.
  
5.  Aggiungere i proxy RADIUS IAS come computer client RADIUS del server IAS. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti.
  
6.  Creare i criteri di accesso remoto appropriati per i computer client wireless nella prima foresta.
  
##### Configurare il server IAS secondario su un altro computer nella prima foresta.
  
Per configurare il server IAS secondario su un altro computer nella prima foresta, procedere come segue:
  
1.  Se si utilizza IAS per Windows 2000, installare IAS come componente di rete facoltativo su un altro computer nella prima foresta, quindi installare Windows 2000 SP4. Se si utilizza IAS per Windows Server 2003, installare IAS come componente di rete facoltativo su un altro computer nella prima foresta,
  
2.  quindi configurare il server IAS secondario per leggere le proprietà degli account utente nel dominio.
  
3.  Se il server IAS autentica i tentativi di connessione per gli account utente negli altri domini, verificare che gli altri domini abbiano un trust bidirezionale col dominio di cui il server IAS secondario è membro. Quindi configurare il server IAS secondario per leggere le proprietà degli account utente negli altri domini.
  
4.  Copiare la configurazione del server IAS primario sul server IAS secondario.
  
##### Configurare il server IAS primario su un computer nella seconda foresta.
  
Per configurare il server IAS primario su un computer nella seconda foresta, procedere come segue:
  
1.  Se si utilizza IAS per Windows 2000, installare IAS come componente di rete facoltativo su un computer nella seconda foresta, quindi installare Windows 2000 SP4. Se si utilizza IAS per Windows Server 2003, installare IAS come componente di rete facoltativo su un computer nella seconda foresta.
  
2.  Configurare il server IAS primario per leggere le proprietà degli account utente nei contenitori di sistema del dominio appropriato.
  
3.  Se il server IAS autentica i tentativi di connessione per gli account utente negli altri domini, verificare che gli altri domini abbiano un trust bidirezionale col dominio di cui il server IAS è membro, quindi configurare il server IAS per leggere le proprietà degli account utente negli altri domini.
  
4.  Se necessario, attivare la registrazione per gli eventi di accounting e autenticazione.
  
5.  Aggiungere i proxy RADIUS IAS come computer client RADIUS del server IAS. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti.
  
6.  Creare il criterio di accesso remoto appropriato per i computer client wireless nella seconda foresta.
  
##### Configurare il server IAS secondario su un altro computer nella seconda foresta.
  
Per configurare il server IAS secondario su un altro computer nella seconda foresta, procedere come segue:
  
1.  Se si utilizza IAS per Windows 2000, installare IAS come componente di rete facoltativo su un computer nella seconda foresta, quindi installare Windows 2000 SP4. Se si utilizza IAS per Windows Server 2003, installare IAS come componente di rete facoltativo su un altro computer nella seconda foresta.
  
2.  Configurare il server IAS secondario per leggere le proprietà degli account utente nei contenitori di sistema del dominio appropriato.
  
3.  Se il server IAS autentica i tentativi di connessione per gli account utente negli altri domini, verificare che questi ultimi abbiano un trust bidirezionale col dominio di cui il server IAS secondario è membro, quindi configurare il server IAS secondario per leggere le proprietà degli account utente negli altri domini.
  
4.  Copiare la configurazione del server IAS primario nella seconda foresta al server IAS secondario.
  
##### Configurare il proxy RADIUS IAS primario
  
Per configurare il proxy RADIUS IAS primario, procedere come segue:
  
1.  Su un computer in cui è in esecuzione Windows Server 2003, installare IAS come componente di rete facoltativo. Il computer in cui è installato IAS non deve essere dedicato a inoltrare i messaggi RADIUS. Ad esempio, è possibile installare IAS su un file server.
  
2.  Se necessario, configurare porte UDP aggiuntive per i messaggi RADIUS che sono inviati dai punti di accesso wireless. Per impostazione predefinita, IAS utilizza le porte UDP 1812 e 1645 per l'autenticazione e le porte UDP 1813 e 1646 per l'accounting.
  
3.  Aggiungere i punti di accesso wireless come computer client RADIUS del server proxy RADIUS IAS. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti.
  
4.  Creare un criterio di richiesta di connessione che inoltra i messaggi di richiesta RADIUS (basati sul nome area di autenticazione degli account nella prima foresta) ai server IAS nella prima foresta. Utilizzare Creazione guidata nuovo criterio richiesta di connessione per creare un criterio richiesta di connessione che inoltra le richieste di connessione a un gruppo di server RADIUS remoti e dove il nome area di autenticazione corrisponde a quello degli account utente nella prima foresta. Deselezionare la casella di controllo che rimuove il nome area di autenticazione per l'autenticazione. Nella Creazione guidata nuovo criterio richiesta di connessione, utilizzare Creazione guidata nuovo gruppo server RADIUS remoto per creare un gruppo di server RADIUS remoto con i membri che includono i due server IAS nella prima foresta.
  
5.  Creare un criterio di richiesta di connessione che inoltra i messaggi di richiesta RADIUS (basati sul nome area di autenticazione degli account nella seconda foresta) ai server IAS nella prima foresta. Utilizzare Creazione guidata nuovo criterio richiesta di connessione per creare un criterio richiesta di connessione che inoltra le richieste di connessione a un gruppo di server RADIUS remoti e dove il nome area di autenticazione corrisponde al nome area di autenticazione degli account utente nella seconda foresta. Deselezionare la casella di controllo che rimuove il nome area di autenticazione per l'autenticazione. Nella Creazione guidata nuovo criterio richiesta di connessione, utilizzare Creazione guidata nuovo gruppo server RADIUS remoto per creare un gruppo di server RADIUS remoto con i membri che includono i due server IAS nella seconda foresta.
  
6.  Eliminare il criterio richiesta connessione predefinito denominato **Utilizza autenticazione Windows per tutti gli utenti**.
  
##### Configurare il proxy RADIUS IAS secondario.
  
Per configurare il proxy IAS secondario su un altro computer, procedere come segue:
  
1.  Su un altro computer in cui è in esecuzione Windows Server 2003, installare IAS come componente di rete facoltativo.
  
2.  Copiare la configurazione del proxy RADIUS IAS primario al proxy RADIUS IAS secondario.
  
##### Configurazione dell'autenticazione e dell'accounting RADIUS sui punti di accesso wireless
  
Configurare le impostazioni RADIUS sui punti di accesso wireless di terze parti nel modo seguente:
  
1.  L'indirizzo IP o il nome di un server RADIUS primario, il segreto condiviso comune, le porte UDP per l'autenticazione e l'accounting e le impostazioni di rilevamento errore.
  
2.  L'indirizzo IP o il nome di un server RADIUS secondario, il segreto condiviso comune, le porte UDP per l'autenticazione e l'accounting e le impostazioni di rilevamento errore.
  
Per bilanciare il carico di traffico RADIUS tra i due server proxy RADIUS IAS, configurare metà dei punti di accesso wireless col proxy RADIUS IAS primario come server RADIUS primario e il proxy RADIUS IAS secondario come server RADIUS secondario e l'altra metà dei punti di accesso wireless col proxy RADIUS IAS secondario come server RADIUS primario e il proxy RADIUS IAS primario come server RADIUS secondario.
  
Per ulteriori informazioni, vedere la documentazione per i punti di accesso wireless.
  
#### Utilizzare i proxy RADIUS per autenticazioni su larga scala
  
Quando si esegue l'autenticazione per molti computer client wireless utilizzando EAP-TLS e i certificati, il volume di traffico di autenticazione necessario per mantenere i computer client wireless connessi può essere notevole. Per una distribuzione molto vasta, sarebbe meglio tentare di distribuire il carico di traffico di autenticazione tra più server IAS. Poiché non è possibile affidarsi ai punti di accesso wireless per distribuire adeguatamente e coerentemente il traffico di autenticazione tra server IAS multipli, i proxy RADIUS IAS intermedi possono svolgere questo compito.
  
Senza i proxy RADIUS, ogni punto di accesso wireless invia le richieste RADIUS a uno o più server RADIUS e rileva i server RADIUS non disponibili. Un punto di accesso wireless è in grado di bilanciare o meno il carico di traffico RADIUS tra server RADIUS multipli. Utilizzando i proxy RADIUS IAS, si usa un bilanciamento del carico coerente per distribuire il carico di autenticazione, autorizzazione e accounting tra tutti i server IAS dell'organizzazione. Inoltre si ha a disposizione uno schema coerente di rilevamento degli errori e i server RADIUS possono scambiarsi facilmente i ruoli.
  
La configurazione seguente è per un'organizzazione che utilizza:
  
-   Domini Active Directory.
  
    I domini Active Directory contengono gli account utente, le password e le proprietà delle connessioni remote richieste da ogni server IAS per autenticare le credenziali utente e valutare l'autorizzazione.
  
-   Server IAS multipli.
  
    Per bilanciare il carico RADIUS di traffico di autenticazione, autorizzazione e accounting, ci sono server IAS multipli.
  
-   Criteri di accesso remoto.
  
    I criteri di accesso remoto sono configurati per specificare, in base all'appartenenza al gruppo, i diversi tipi di limiti di connessione per gli utenti.
  
-   Due proxy RADIUS IAS.
  
    Almeno due proxy RADIUS IAS sono utilizzati per fornire la tolleranza di errore per le richieste RADIUS che sono inviate dai punti di accesso wireless.
  
Nella figura 3 viene mostrato l'uso di server proxy RADIUS IAS per bilanciare il carico di traffico RADIUS dai punti di accesso wireless tramite i server IAS multipli.
  
![](images/Bb457097.ed802103(it-it,TechNet.10).gif)
  
**Figura 3  Utilizzo dei proxy RADIUS IAS per bilanciare il carico di traffico di autenticazione**
  
Per configurare IAS per questo esempio, completare i passaggi seguenti:
  
1.  Configurare le foreste di Active Directory per gli account e i gruppi utente.
  
2.  Configurare IAS come server RADIUS su più computer.
  
3.  Configurare il proxy RADIUS IAS primario.
  
4.  Configurare il proxy RADIUS IAS secondario.
  
5.  Configurare l'autenticazione e l'accounting RADIUS sui punti di accesso wireless
  
IAS per Windows 2000 non supporta il proxy RADIUS. È possibile, tuttavia, utilizzare IAS per Windows Server 2003 in modo che svolga la funzione di proxy RADIUS in questa configurazione. Per ulteriori informazioni, vedere l'argomento "Utilizzare i proxy IAS per bilanciare il carico" nella Guida e supporto tecnico di Windows Server 2003.
  
##### Configurare Active Directory per gli account e i gruppi.
  
Per configurare Active Directory per gli account utente e i gruppi, procedere come segue:
  
1.  Su ogni controller di dominio Windows 2000, installare Windows 2000 SP4.
  
2.  Assicurarsi che tutti gli utenti che usano connessioni wireless abbiano il corrispondente account utente. Assicurarsi che tutti i computer che usano connessioni wireless abbiano il corrispondente account di computer.
  
3.  Impostare l'autorizzazione all'accesso remoto per gli account utente e computer nel modo opportuno.
  
4.  Organizzare gli account nei gruppi appropriati per approfittare dei criteri di accesso remoto basati sui gruppi.
  
##### Configurare IAS come un server RADIUS su più computer.
  
Per configurare IAS come un server RADIUS su ogni computer, procedere come segue:
  
1.  Se si utilizza IAS per Windows 2000, installare IAS come componente di rete facoltativo e installare poi Windows 2000 SP4. Se si utilizza IAS per Windows Server 2003, installare IAS come componente di rete facoltativo.
  
2.  Configurare ogni server IAS per leggere le proprietà degli account utente nei contenitori di sistema del dominio appropriato.
  
3.  Se necessario, attivare la registrazione per gli eventi di accounting e autenticazione.
  
4.  Aggiungere i proxy RADIUS IAS come computer client RADIUS. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti.
  
5.  Creare il criterio di accesso remoto appropriato per l'accesso di rete wireless.
  
##### Configurare il proxy RADIUS IAS primario.
  
Per configurare il proxy RADIUS IAS primario, procedere come segue:
  
1.  Su un computer in cui è in esecuzione Windows Server 2003, installare IAS come componente di rete facoltativo. Il computer su cui IAS è installato non deve essere dedicato a inoltrare i messaggi RADIUS. Ad esempio, è possibile installare IAS su un file server.
  
2.  Se necessario, configurare porte UDP aggiuntive per i messaggi RADIUS che sono inviati dai punti di accesso wireless. Per impostazione predefinita, IAS utilizza le porte UDP 1812 e 1645 per l'autenticazione e le porte UDP 1813 e 1646 per l'accounting.
  
3.  Aggiungere i punti di accesso wireless come computer client RADIUS del server IAS. Verificare che si stiano configurando il nome o l'indirizzo IP e i segreti condivisi corretti.
  
4.  Utilizzare Creazione guidata nuovo gruppo server RADIUS remoto per creare un gruppo remoto personalizzato di server RADIUS. Aggiungere ogni server RADIUS IAS come membro del gruppo remoto di server RADIUS e configurare ogni membro del gruppo con priorità 1 e peso 50 (impostazioni predefinite).
  
5.  Creare un criterio di richiesta di connessione che invii i messaggi di richiesta RADIUS ai server IAS in cui il nome area di autenticazione corrisponde agli account nel dominio. Utilizzare Creazione guidata nuovo criterio richiesta di connessione per creare un criterio richiesta di connessione che inoltra le richieste di connessione a un server RADIUS remoto e dove il nome area di autenticazione corrisponde al nome area di autenticazione degli account utente nella foresta. Deselezionare la casella di controllo che rimuove il nome area di autenticazione per l'autenticazione. Scegliere il gruppo di server RADIUS remoto precedentemente creato come gruppo per l'inoltro delle richieste di connessione.
  
6.  Eliminare il criterio richiesta connessione predefinito denominato **Utilizza autenticazione Windows per tutti gli utenti**.
  
##### Configurare il proxy RADIUS IAS secondario.
  
Per configurare il proxy IAS secondario su un altro computer, procedere come segue:
  
1.  Su un altro computer in cui è in esecuzione Windows Server 2003, installare IAS come componente di rete facoltativo.
  
2.  Copiare la configurazione del proxy RADIUS IAS primario al proxy RADIUS IAS secondario.
  
##### Configurare l'autenticazione e l'accounting RADIUS sui punti di accesso wireless
  
Configurare le impostazioni RADIUS sui punti di accesso wireless di terze parti nel modo seguente:
  
1.  L'indirizzo IP o il nome del server RADIUS primario, il segreto condiviso comune, le porte UDP per l'autenticazione e l'accounting e le impostazioni di rilevamento errore.
  
2.  L'indirizzo IP o il nome del server RADIUS secondario, il segreto condiviso comune, le porte UDP per l'autenticazione e l'accounting e le impostazioni di rilevamento errore.
  
Per bilanciare il carico di traffico RADIUS tra i due proxy RADIUS IAS, configurare metà dei punti di accesso wireless col proxy RADIUS IAS primario come server RADIUS primario e il proxy RADIUS IAS secondario come server RADIUS secondario e l'altra metà dei punti di accesso wireless col proxy RADIUS IAS secondario come server RADIUS primario e il proxy RADIUS IAS primario come server RADIUS secondario.
  
Per ulteriori informazioni, vedere la documentazione per i punti di accesso wireless.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice A Utilizzare soltanto l'autenticazione del computer
  
Alcuni amministratori di rete vogliono utilizzare soltanto l'autenticazione del computer. Se si utilizza soltanto l'autenticazione del computer, un computer client wireless deve eseguire un'autenticazione 802.1X a livello di computer con un punto di accesso wireless utilizzando o un certificato di computer (autenticazione EAP-TLS) o il nome account e la password del computer (autenticazione PEAP-MS-CHAP v2) prima di poter accedere alla rete dell'organizzazione. Con l'autenticazione del solo computer, solamente i computer validi possono connettersi alla rete wireless. I computer che non hanno un account di computer nel dominio dell'organizzazione non possono connettersi. In questo modo si evita che gli utenti portino computer da casa e si connettano alla LAN wireless dell'organizzazione. I computer per uso personale rappresentano un pericolo per la rete dell'organizzazione perché non sono gestiti come i computer membri e possono introdurre virus o altri programmi dannosi nella rete dell'organizzazione.
  
Per ulteriori informazioni sull'autenticazione computer e l'autenticazione utente, vedere [Windows XP Cenni preliminari di tecnologia e componenti per la distribuzione wireless](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wificomp.mspx).
  
È possibile configurare l'autenticazione del solo computer utilizzando l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11) o tramite il Registro di sistema.
  
#### Configurare l'autenticazione del solo computer utilizzando l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11)
  
Per configurare l'autenticazione del solo computer utilizzando l'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11), scegliere **Solo computer** in **Autenticazione computer** nella scheda **802.1x** per la rete preferita che corrisponde alla rete wireless prescelta. Nella figura 8 è riportato un esempio.
  
![](images/Bb457097.ed802104(it-it,TechNet.10).gif)
  
**Figura 4  Scegliere autenticazione del solo computer nell'estensione Criteri di gruppo di Criteri di rete senza fili (IEEE 802.11)**
  
Per ulteriori informazioni, vedere [Configurare le impostazioni wireless utilizzando i criteri di gruppo di Windows Server 2003](http://www.microsoft.com/technet/community/columns/cableguy/cg0703.mspx) (la pagina potrebbe essere in inglese).
  
#### Abilitare l'autenticazione del solo computer utilizzando il Registro di sistema
  
Per configurare l'autenticazione del solo computer attraverso il Registro di sistema, tutti i computer client wireless di Windows devono avere la seguente serie di valori del registro di sistema:
  
HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\EAPOL\\Parameters\\General\\Global\\AuthMode=2
  
Con AuthMode impostato su 2, viene tentata solo l'autenticazione del computer. Non viene mai tentata l'autenticazione dell'utente.
  
Per aggiungere questa impostazione del registro di sistema su tutti i computer in cui è in esecuzione Windows, è possibile utilizzare il seguente strumento:
  
-   Regini.exe da [Windows 2000 Server Resource Kit Tools](http://www.microsoft.com/windows2000/techinfo/reskit/rktour/server/s_tools.asp) 
  
-   Reg.exe da [Windows Server 2003 Resource Kit Tools](http://www.microsoft.com/downloads/details.aspx?familyid=9d467a69-57ff-4ae7-96ee-b18c4790cffd&displaylang=en)
  
In entrambi i casi, si crea un file di script che viene letto dallo strumento che aggiunge un'impostazione al registro di sistema. Lo strumento deve essere eseguito nel contesto di protezione di un account di amministratore locale.
  
È anche possibile utilizzare il software di gestione di rete per modificare le impostazioni del Registro di sistema sui computer gestiti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
È possibile eseguire l'autenticazione protetta wireless sia con EAP-TLS che con PEAP-MS-CHAP v2. Per EAP-TLS, occorre distribuire un'infrastruttura di certificazione in grado di emettere certificati di computer ai server IAS e sia certificati di computer sia certificati utente ai computer client e agli utenti wireless. Per PEAP-MS-CHAP v2, basta installare i certificati di computer sui server IAS, a patto che gli opportuni certificati di autorità di certificazione radice siano già installati sui computer client wireless. In entrambi i casi, occorre gestire gli utenti e i gruppi di Active Directory per l'accesso wireless, configurare i server IAS come server RADIUS per i punti di accesso wireless e configurare i punti di accesso wireless come computer client RADIUS per i server IAS. È possibile configurare anche l'accesso a Internet per i partner commerciali, utilizzare autorità di certificazione di terze parti e i proxy RADIUS IAS per l'autenticazione tra foreste o per bilanciare il carico.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Collegamenti correlati
  
Per ulteriori informazioni, vedere le risorse seguenti:
  
-   [Sito Web Wireless Networking (in inglese)](http://www.microsoft.com/technet/itsolutions/network/wifi/default.mspx)
  
-   [Sito Web Internet Authentication Service (in inglese)](http://www.microsoft.com/technet/itsolutions/network/ias/default.mspx)
  
-   [Internet Authentication Service per Windows 2000 Server (in inglese)](http://www.microsoft.com/windows2000/technologies/communications/ias/)
  
-   [Sito Web Servizi di protezione di Windows Server 2003 (in inglese)](http://www.microsoft.com/windowsserver2003/technologies/security/default.mspx)
  
-   [Sito Web Infrastruttura a chiave pubblica per Windows Server 2003](http://www.microsoft.com/windowsserver2003/technologies/pki/default.mspx)
  
-   [Cenni preliminari di tecnologia e componenti della distribuzione wireless](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wificomp.mspx)
  
-   [Procedure consigliate e raccomandazioni per la distribuzione wireless](http://www.microsoft.com/technet/prodtechnol/winxppro/deploy/wideprec.mspx)
  
-   [Ricerca guasti per l'accesso wireless IEEE 802.1 con Microsoft Windows](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wifitrbl.mspx)
  
-   [Windows 2000 Service Pack 4](http://www.microsoft.com/windows2000/downloads/servicepacks/default.asp)
  
[](#mainsection)[Inizio pagina](#mainsection)
