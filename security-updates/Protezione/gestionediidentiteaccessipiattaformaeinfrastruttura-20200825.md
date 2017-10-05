---
TOCTitle: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
Title: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
ms:assetid: '0d1934c8-4ef6-48da-802f-3d71b0e53ca9'
ms:contentKeyID: 20200825
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536226(v=TechNet.10)'
---

Piattaforma e infrastruttura
============================

### Capitolo 5: Implementazione dell'infrastruttura

Aggiornato: 29 aprile 2004

I capitoli precedenti in questo documento offrono informazioni sui tipici problemi, requisiti e layout di un'infrastruttura per la gestione di identità e accessi. In questo capitolo vengono fornite le linee guida per la modalità di preparazione dell'infrastruttura di Contoso Pharmaceuticals. Inoltre vengono presentati strumenti e modelli utilizzabili per stabilire l'ambiente di base, che costituisce un prerequisito di implementazione per gli altri documenti di questa serie.

Queste linee guida sono state create per permettere ai consulenti e ai clienti di stabilire gli scenari relativi alla soluzione Microsoft di Gestione di identità e accessi in un laboratorio o in un ambiente di verifica funzionale.

### Strumenti e modelli

Gli script e i file di configurazione di esempio per questo documento sono disponibili presso la pagina di download [*Serie Microsoft di Gestione di identità e accessi*](http://technet.microsoft.com/it-it/library/dd536198.aspx), nel sito Web Microsoft.com all'indirizzo:
http://go.microsoft.com/fwlink/?LinkId=14842. Utilizzare gli esempi per attenersi alle linee guida del capitolo.

**Nota:** gli esempi vengono forniti a scopo esclusivamente illustrativo. Assicurarsi di esaminare, personalizzare e testare questi strumenti prima di utilizzarli in un ambiente reale.

Di seguito vengono descritti tutti i file contenuti nella sezione **Piattaforma e infrastruttura** della directory **Tools and Templates**.

#### Cartella: Baseline

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome file</th>
<th style="border:1px solid black;" >Scopo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ADBaseline.vbs</td>
<td style="border:1px solid black;">Uno script Microsoft® Visual Basic® che crea diverse unità organizzative, gruppi e utenti di Contoso Pharmaceuticals in un insieme di strutture per il servizio directory Microsoft Active Directory®, come richiesto dai documenti successivi in questa serie.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ExchangeBaseline.vbs</td>
<td style="border:1px solid black;">Uno script Microsoft Visual Basic che crea i necessari archivi delle cassette postali e gruppi di archiviazione Exchange di Contoso per supportare gli utenti Contoso nell'Intranet.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IntranetADData.txt</td>
<td style="border:1px solid black;">Un file contenente le unità organizzative, i gruppi e gli utenti Active Directory di base nell'Intranet in formato delimitato dal punto e virgola. Gli scripti ADBaseline.vbs ed ExchangeBaselin.vbs utilizzano questo file.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ExtranetADData.txt</td>
<td style="border:1px solid black;">Un file contenente le unità organizzative, i gruppi e gli utenti Active Directory di base nell'Extranet in formato delimitato dal punto e virgola. Lo script ADBaseline.vbs utilizza questo file.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Panoramica dei servizi dell'infrastruttura
  
L'infrastruttura di gestione identità e accessi di Contoso Pharmaceuticals è stata realizzata secondo le indicazioni della guida [Microsoft Systems Architecture (MSA) 2.0 Service Blueprints](http://www.microsoft.com/resources/documentation/msa/2/all/solution/en-us/msa20rak/vmhtm44.mspx) nell'*MSA Reference Architecture Kit* (in inglese), sul sito Web Microsoft.com, all'indirizzo:  
http://www.microsoft.com/resources/documentation/msa/2/  
all/solution/en-us/msa20rak/vmhtm44.mspx.
  
In particolare, Contoso ha implementato i seguenti servizi Microsoft a supporto delle proprie iniziative di gestione di identità e accessi:
  
-   **Servizi di rete**, compresi i servizi DNS (Domain Name System) e DHCP (Dynamic Host Configuration Protocol) forniti da Microsoft Windows Server™ 2003.
  
-   **Servizi directory**, compresi un insieme di strutture Active Directory nell'Intranet e un insieme di strutture Active Directory nell'Extranet forniti da Windows Server 2003.
  
-   **Servizi certificati**, compresa un'infrastruttura a chiave pubblica (PKI), a tre livelli, fornita da Windows Server 2003.
  
-   **Servizi per applicazioni Web**, forniti da IIS (Internet Information Services) 6.0, incluso in Windows Server 2003.
  
-   **Servizi middleware**, forniti da Microsoft .NET Framework e in esecuzione su Windows Server 2003.
  
-   **Servizi proxy e firewall**, forniti da Microsoft Internet Security and Acceleration (ISA) Server 2000 e in esecuzione in Windows Server 2003.
  
    **Nota:** Contoso Pharmaceuticals ha deciso di utilizzare account shadow nell'insieme di strutture Active Directory dell'Extranet, anziché implementare un trust fra tale insieme e quello dell'Intranet, come descritto nella guida di MSA 2.0.
  
Inoltre Contoso ha distribuito [Solution Accelerator for MSA Enterprise Messaging](http://go.microsoft.com/fwlink/?linkid=23350) (in inglese), come descritto in Microsoft TechNet all'indirizzo:  
http://go.microsoft.com/fwlink/?LinkId=23350. A scopo di verifica, i servizi di messaggistica di Contoso vengono eseguiti su un solo computer, dotato del sistema operativo Windows Server 2003 che esegue anche Microsoft Exchange 2003.
  
#### Protezione dell'infrastruttura
  
Tutti i server Windows Server 2003 nell'ambiente di Contoso sono stati configurati in modo protetto seguendo le indicazioni appropriate della [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140), sul sito Web Microsoft.com, disponibile all'indirizzo: http://go.microsoft.com/fwlink/?linkid=14845.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Implementazione di base
  
Nell'ambiente di Contoso Pharmaceuticals alcuni gruppi, utenti e altri dettagli della configurazione di base sono necessari per garantire la corretta operatività degli scenari relativi alle soluzioni descritti in questa serie.
  
Questa sezione illustra come configurare l'ambiente di base di Contoso a partire dai servizi descritti in precedenza in questo documento, includendo:
  
-   Un computer nell'Intranet che esegue Exchange Server 2003, dove sono contenute le necessarie caselle di posta degli utenti e i gruppi di archiviazione del dominio Intranet.
  
-   Un insieme di strutture Active Directory nell'Intranet contenente le unità organizzative, i gruppi e gli utenti necessari.
  
-   Un insieme di strutture Active Directory nell'Extranet contenente le unità organizzative, i gruppi e gli utenti necessari.
  
#### Popolamento dell'ambiente Exchange di Contoso
  
L'ambiente Exchange di Contoso rappresenta il sistema di posta principale per gli utenti della società. Per poter creare utenti Contoso, devono esistere i necessari archivi di caselle di posta e gruppi di archiviazione. Eseguire questo script da un prompt dei comandi aperto, utilizzando cscript.exe come host di scripting.
  
##### Utilizzo dello script ExchangeBaseline.vbs
  
Eseguire lo script ExchangeBaseline.vbs utilizzando il file eseguibile cscript come host di scripting. Assicurarsi che lo script venga eseguito al prompt dei comandi come segue:
  
CSCRIPT.EXE ExchangeBaseline.vbs *&lt;param1&gt;*
  
Lo script assume il parametro seguente:
  
**/s** - obbligatorio. Indica il server Exchange di destinazione per la connessione.
  
Di seguito viene riportata una riga di comando di esempio per l'esecuzione di questo script:
  
Cscript.exe ExchangeBaseline.vbs /s *&lt;nomehost&gt;*
  
**Nota:** l'esecuzione dello script può richiedere alcuni minuti a causa del processo Microsoft Exchange utilizzato per installare gli archivi di cassette postali.
  
**Per configurare l'ambiente Exchange**
  
1.  Accedere al server Exchange di Contoso con privilegi amministrativi.
  
2.  Fare clic su **Start**, **Esegui**, quindi al prompt **Apri** digitare:  
    cmd.exe e premere **INVIO**.
  
3.  Eseguire il file **ExchangeBaseline.vbs** utilizzando cscript.exe come host di scripting.
  
4.  Al prompt dei comandi, assicurarsi di aver digitato lo script come segue:
  
5.  Cscript.exe ExchangeBaseline.vbs /s *FFL-NA-MSG-01*
  
    **Nota:** sostituire FFL-NA-MSG-01 con il nome del server Exchange.
  
6.  Assicurarsi che lo script restituisca per tutte le operazioni il seguente messaggio di conferma:  
    Operazione completata.
  
In caso di errori durante l'esecuzione dello script, risolvere il problema ed eseguire di nuovo lo script.
  
#### Popolamento dell'insieme di strutture Active directory nell'Intranet
  
L'insieme di strutture Active Directory na.contoso.com è la directory principale dell'Intranet di Contoso. Lo script ADBaseline.vbs creerà le unità organizzative, gli utenti e i gruppi necessari per gli scenari delle soluzioni Contoso in questa serie.
  
##### Utilizzo dello script ADBaseline.vbs
  
Eseguire lo script ADBaseline.vbs utilizzando il file eseguibile cscript come host di scripting. Assicurarsi che lo script venga eseguito al prompt dei comandi come segue:
  
CSCRIPT ADBaseline.vbs *&lt;param1&gt; &lt;param2&gt; &lt;param3&gt; &lt;param4&gt;*
  
Lo script assume i parametri seguenti:
  
**/t** - obbligatorio. Indica l'ambiente di destinazione da preparare, ovvero l'Intranet per questo scenario.
  
**/s** - obbligatorio. Indica il controller di dominio di destinazione per Active Directory.
  
**/m** - solo per Intranet. Indica il server Exchange di destinazione per il binding. Il parametro viene ignorato per l'Extranet.
  
**/f** - facoltativo. Indica il file di dati di destinazione che contiene le informazioni utente dell'Intranet di Contoso. Per impostazione predefinita, lo script utilizza il file **IntranetADData.txt**.
  
Di seguito viene riportata una riga di comando di esempio per l'esecuzione di questo script:
  
Cscript.exe ADBaseline.vbs /t intranet /s *&lt;controller di dominio&gt;*  
/m *&lt;server Exchange&gt;* /f IntranetADData.txt
  
Questo script è eseguibile anche in remoto. In tal caso, assicurarsi che la workstation faccia parte del dominio di destinazione e di essere connessi come amministratore del dominio.
  
**Per configurare l'insieme di strutture na.corp.contoso.com**
  
1.  Accedere al dominio del server Exchange di Contoso con privilegi amministrativi.
  
    **Nota:** è necessario eseguire lo script dal server Exchange per accedere alle librerie Exchange necessarie e creare le caselle di posta degli utenti di destinazione.
  
2.  Fare clic su **Start**, **Esegui**, quindi al prompt **Apri** digitare:  
    cmd.exe e premere **INVIO**.
  
3.  Al prompt dei comandi, eseguire lo script **ADBaseline.vbs** utilizzando il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false"> Cscript.exe ADBaseline.vbs /t intranet /s FFL-NA-DC-01 /m FFL-NA-MSG-01 /f IntranetADData.txt   
```
  
    **Nota:** sostituire FFL-NA-DC-01 con il nome del controller di dominio Intranet e FFL-NA-MSG-01 con il nome del server Exchange.
  
4.  Assicurarsi che lo script restituisca per tutte le operazioni il seguente messaggio di conferma:  
    Operazione completata.
  
In caso di errori durante l'esecuzione dello script, risolvere il problema ed eseguire di nuovo lo script.
  
#### Popolamento dell'insieme di strutture Active Directory nell'Extranet
  
Il dominio Active Directory perimeter.contoso.com è l'insieme di strutture dell'Extranet di Contoso. Come nella procedura precedente, utilizzare lo script ADBaseline.vbs per popolare l'insieme di strutture.
  
**Per configurare l'insieme di strutture perimeter.contoso.com**
  
1.  Accedere al controller di dominio perimeter.contoso.com di Contoso con privilegi di amministratore di dominio.
  
2.  Fare clic su **Start**, **Esegui**, quindi al prompt **Apri** digitare cmd.exe e premere **OK**.
  
3.  Al prompt dei comandi, eseguire lo script **ADBaseline.vbs** utilizzando il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false"> Cscript.exe ADBaseline.vbs /t extranet /s FFL-CP-DC-01 /f ExtranetADData.txt   
```
  
    **Nota:** sostituire FFL-CP-DC-01 con il nome del controller di dominio Extranet.
  
4.  Assicurarsi che lo script restituisca per tutte le operazioni il seguente messaggio di conferma:  
    Operazione completata.
  
In caso di errori durante l'esecuzione dello script, risolvere il problema ed eseguire di nuovo lo script.
  
[](#mainsection)[Inizio pagina](#mainsection)
