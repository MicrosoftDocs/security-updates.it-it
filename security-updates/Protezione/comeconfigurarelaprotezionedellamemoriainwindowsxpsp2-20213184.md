---
TOCTitle: Come configurare la protezione della memoria in Windows XP SP2
Title: Come configurare la protezione della memoria in Windows XP SP2
ms:assetid: '3ad3cd19-e9e3-431b-9d34-e6b294ece35d'
ms:contentKeyID: 20213184
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700810(v=TechNet.10)'
---

Come configurare la protezione della memoria in Windows XP SP2
==============================================================

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Operazioni preliminari](#eeaa)
[](#edaa)[Attivazione di Protezione esecuzione programmi per tutti i programmi del computer](#edaa)
[](#ecaa)[Attivazione dell'elenco delle eccezioni di Protezione esecuzione programmi](#ecaa)
[](#ebaa)[Configurazione delle opzioni di Protezione esecuzione programmi a livello di intero sistema](#ebaa)
[](#eaaa)[Informazioni correlate](#eaaa)

### Introduzione

Microsoft Windows XP Service Pack 2 (SP2) aiuta a proteggere il computer dall'inserimento di codice dannoso nelle aree di memoria riservate al codice non eseguibile, grazie all'implementazione di un insieme di tecnologie hardware e software chiamato Protezione esecuzione programmi. La funzionalità Protezione esecuzione programmi hardware è specifica di alcuni processori che impediscono l'esecuzione di codice nelle regioni di memoria contrassegnate per l'archiviazione dei dati. Questa funzionalità è conosciuta anche come NX (No eXecute) o Execution Protection. Windows XP SP2 include anche la funzionalità Protezione esecuzione programmi a livello di software, specifica per ridurre lo sfruttamento dei meccanismi di gestione delle eccezioni in Windows.

Diversamente dai normali programmi antivirus, le tecnologie Protezione esecuzione programmi hardware e software non sono progettate per impedire l'installazione di programmi dannosi sul computer. Il loro scopo è piuttosto quello di monitorare i programmi installati per verificare che stiano utilizzando in modo corretto la memoria del sistema. Per monitorare i programmi, Protezione esecuzione programmi hardware tiene traccia delle posizioni di memoria dichiarate "non-eseguibili". Per impedire l'installazione di codice dannoso, se un programma cerca di eseguire codice dalla memoria dichiarata "non-eseguibile", Windows chiude il programma. La chiusura del programma avviene indipendemente dal fatto che il codice sia dannoso o meno.

**Nota:** la funzionalità Protezione esecuzione programmi software è integrata in Windows XP SP2 ed è attivata per impostazione predefinita, indipendentemente dalle capacità Protezione esecuzione programmi hardware del processore. Per impostazione predefinita, la funzionalità Protezione esecuzione programmi software riguarda i servizi e i componenti del sistema operativo di base.

La configurazione predefinita di Protezione esecuzione programmi è progettata per proteggere il computer senza impattare troppo sulla compatibilità tra le applicazioni. Tuttavia, con alcune configurazioni di Protezione esecuzione programmi, è possibile che alcuni programmi non vengano eseguiti correttamente. Per configurare Protezione esecuzione programmi sul computer, è possibile eseguire le attività descritte in questo documento:

-   Attivare Protezione esecuzione programmi per tutti i programmi del computer

-   Aggiungere programmi all'elenco delle eccezioni di Protezione esecuzione programmi

-   Disattivare Protezione esecuzione programmi a livello di intero computer

    **IMPORTANTE:** le istruzioni contenute in questo documento sono state sviluppate a partire dal menu Start che viene visualizzato per impostazione predefinita quando si installa il sistema operativo. Se il menu Start è stato modificato, la procedura potrebbe essere leggermente diversa.

Per le definizioni dei termini relativi alla protezione, fare riferimento alle seguenti risorse:

-   "[Microsoft Security Glossary](http://go.microsoft.com/fwlink/?linkid=35468)" sul sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=35468

Per ulteriori informazioni su Protezione esecuzione programmi, fare riferimento alle seguenti risorse:

-   [Microsoft Knowledge Base, articolo 875352](http://go.microsoft.com/fwlink/?linkid=35494) sul sito Web Supporto tecnico Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35494

[](#mainsection)[Inizio pagina](#mainsection)

### Operazioni preliminari

Questo documento fornisce le linee guida che consentono di configurare Protezione esecuzione programmi su Windows XP SP2.

**Nota:** la funzionalità Protezione esecuzione programmi hardware è attivata per impostazione predefinita sui computer Microsoft Windows XP 64-Bit Edition dotati di processori compatibili con Protezione esecuzione programmi. Le applicazioni a 64 bit non potranno essere eseguite dalle aree "non-eseguibili" della memoria. La funzionalità Protezione esecuzione programmi hardware non può essere disattivata.

La funzionalità Protezione esecuzione programmi software nelle applicazioni Windows XP SP2 e 32-Bit in esecuzione su qualsiasi tipo di processore può essere configurata per l'uso delle aree "eseguibili" o "non-eseguibili" della memoria.

[](#mainsection)[Inizio pagina](#mainsection)

### Attivazione di Protezione esecuzione programmi per tutti i programmi del computer

La configurazione predefinita della funzionalità Protezione esecuzione programmi hardware e software protegge i servizi e i componenti di base di Windows con un impatto minimo sulla compatibilità tra le applicazioni, tuttavia è possibile scegliere di configurare Protezione esecuzione programmi per proteggere tutte le applicazioni e tutti i programmi presenti nel computer. Se si configura Protezione esecuzione programmi in modo da proteggere tutte le applicazioni e tutti i programmi del computer si ottiene un aumento del livello di protezione ma anche un aumento dei possibili problemi di compatibilità tra le applicazioni. Se si configura Protezione esecuzione programmi in modo da proteggere tutte le applicazioni e tutti i programmi del computer, è possibile esentare singole applicazioni a 32 bit dall'applicazione della funzionalità Protezione esecuzione programmi software, nel caso in cui siano presenti problemi di compatibilità relativi a tali applicazioni. Non è possibile disattivare la funzionalità Protezione esecuzione programmi hardware o esentare le applicazioni a 64 bit in esecuzione su sistemi Windows XP 64-Bit dotati di processori compatibili con Protezione esecuzione programmi.

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere al computer utilizzando un account con diritti di amministratore locale.

##### Configurazione di Protezione esecuzione programmi per proteggere tutte le applicazioni

**Per attivare Protezione esecuzione programmi per tutte le applicazioni**

1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.

2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.

3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.

4.  Fare clic sulla scheda **Avanzate**.

    ![](images/Cc700810.DEPcnf01(it-it,TechNet.10).gif)

    **Figura 1   Scheda Proprietà del sistema - Avanzate**

5.  Nell'area **Prestazioni**, fare clic su **Impostazioni**.

    ![](images/Cc700810.DEPcnf02(it-it,TechNet.10).gif)

    **Figura 2   Opzioni prestazioni**

6.  Fare clic sulla scheda **Protezione** **esecuzione** **programmi**.

    ![](images/Cc700810.DEPcnf03(it-it,TechNet.10).gif)

    **Figura 3   Scheda Protezione esecuzione programmi**

7.  Selezionare **Attiva Protezione esecuzione programmi per tutti i programmi e i servizi tranne quelli selezionati**.

8.  Fare clic su **Applica**, quindi scegliere **OK**. Viene visualizzata una finestra di dialogo che informa che è necessario riavviare il computer per rendere effettiva l'impostazione. Fare clic su **OK**.

#### Verifica dell'applicazione delle impostazioni di Protezione esecuzione programmi per tutti i programmi

**Per verificare che le impostazioni di Protezione esecuzione programmi siano applicate**

1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.

2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.

3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.

4.  Fare clic sulla scheda **Avanzate**.

5.  Nell'area **Prestazioni**, fare clic su **Impostazioni**, quindi scegliere **Protezione** **esecuzione** **programmi**.

6.  Verificare che **Attiva Protezione esecuzione programmi per tutti i programmi e i servizi tranne quelli selezionati** sia selezionato, quindi fare clic su **OK** per chiudere **Impostazioni prestazioni**.

7.  Fare clic su **OK** per chiudere **Proprietà del** **sistema**, quindi chiudere **Prestazioni** **e** **manutenzione**.

[](#mainsection)[Inizio pagina](#mainsection)

### Attivazione dell'elenco delle eccezioni di Protezione esecuzione programmi

Se Protezione esecuzione programmi causa dei problemi relativi alle applicazioni, viene visualizzata una finestra di dialogo che informa di tale situazione.

![](images/Cc700810.DEPcnf04(it-it,TechNet.10).gif)

**Figura 4   Finestra di dialogo che viene visualizzata se il tentativo di esecuzione di un'applicazione crea un problema con Protezione esecuzione programmi**

Nei casi in cui Protezione esecuzione programmi è causa del malfunzionamento di alcune applicazioni, Microsoft consiglia vivamente di contattare il fornitore dell'applicazione per sapere se è disponibile un aggiornamento compatibile con Protezione esecuzione programmi. L'installazione di un aggiornamento è la soluzione migliore per i problemi di compatibilità tra le applicazioni e Protezione esecuzione programmi.

Se non è disponibile un aggiornamento per l'applicazione, eseguire la procedura sotto illustrata per accedere all'elenco delle eccezioni e modificarlo. L'elenco delle eccezioni è l'elenco delle applicazioni escluse da Protezione esecuzione programmi.

**Nota:** l'elenco delle eccezioni di Protezione esecuzione programmi è disponibile solo se la configurazione di Protezione esecuzione programmi è impostata sulla protezione di tutti i programmi e di tutti i servizi. Se si configura il computer per proteggere solo i servizi e i componenti di base di Windows, l'elenco delle eccezioni non è disponibile.

#### Requisiti per l'esecuzione di questa attività

-   Credenziali: è necessario accedere al computer utilizzando un account con diritti di amministratore locale.

##### Attivazione dell'elenco delle eccezioni di Protezione esecuzione programmi

**Per attivare l'elenco delle eccezioni di Protezione esecuzione programmi**

1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.

2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.

3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.

4.  Fare clic sulla scheda **Avanzate**.

    ![](images/Cc700810.DEPcnf05(it-it,TechNet.10).gif)

    **Figura 5   Scheda Proprietà del sistema - Avanzate**

5.  Nell'area **Prestazioni**, fare clic su **Impostazioni**.

    ![](images/Cc700810.DEPcnf06(it-it,TechNet.10).gif)

    **Figura 6   Opzioni prestazioni**

6.  Fare clic sulla scheda **Protezione** **esecuzione** **programmi**.

    ![](images/Cc700810.DEPcnf07(it-it,TechNet.10).gif)

    **Figura 7   Scheda Protezione esecuzione programmi**

7.  Fare clic su **Aggiungi**.

8.  Individuare e selezionare l'eseguibile dell'applicazione che non funziona, quindi fare clic su **Apri**.

9.  Nella finestra di dialogo di avviso, fare clic su **OK**. A questo punto, il programma selezionato viene visualizzato nell'area programmi di Protezione esecuzione programmi.

10. Fare clic su **Applica**, quindi scegliere **OK**. Viene visualizzata una finestra di dialogo che informa che è necessario riavviare il computer per rendere effettiva l'impostazione. Fare clic su **OK**.

#### Verifica dell'applicazione delle impostazioni dell'elenco delle eccezioni di Protezione esecuzione programmi

**Per verificare che le impostazioni di protezione della memoria siano applicate**

1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.

2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.

3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.

4.  Fare clic sulla scheda **Avanzate**.

5.  Nell'area **Prestazioni**, fare clic su **Impostazioni**, quindi scegliere **Protezione** **esecuzione** **programmi**.

6.  Verificare che l'elenco delle eccezioni contenga i programmi desiderati, quindi fare clic su **OK** per chiudere **Impostazioni** **prestazioni**.

7.  Fare clic su **OK** per chiudere **Proprietà del** **sistema**, quindi chiudere **Prestazioni** **e** **manutenzione**.

[](#mainsection)[Inizio pagina](#mainsection)

### Configurazione delle opzioni di Protezione esecuzione programmi a livello di intero sistema

Per apportare modifiche a Protezione esecuzione programmi a livello di intero sistema, è necessario modificare un'opzione del file di configurazione boot.ini dell'installazione Windows attualmente in esecuzione. L'opzione del file boot.ini è la seguente:

-   **/noexecute =*Livello\_criterio***

Nella tabella 1 sono elencate le opzioni per Livello\_criterio.

**Tabella 1 Opzioni per il livello di criterio del file boot.ini di Protezione esecuzione programmi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Livello di criterio</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>OptIn</strong>
(configurazione predefinita)</td>
<td style="border:1px solid black;">La funzionalità Protezione esecuzione programmi è applicata solo ai servizi e ai componenti di sistema di Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>OptOut</strong></td>
<td style="border:1px solid black;">La funzionalità Protezione esecuzione programmi è attivata per tutti i processi. Gli amministratori possono creare manualmente un elenco di applicazioni specifiche esentate dall'applicazione della funzionalità Protezione esecuzione programmi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>AlwaysOn</strong></td>
<td style="border:1px solid black;">Protezione esecuzione programmi è attivata per tutti i processi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>AlwaysOff</strong></td>
<td style="border:1px solid black;">Protezione esecuzione programmi non è attivata per nessun processo</td>
</tr>
</tbody>
</table>
  
**IMPORTANTE:** dopo avere apportato modifiche al file boot.ini, è necessario riavviare il computer.
  
**AVVISO:** Microsoft consiglia di NON disattivare globalmente la funzionalità Protezione esecuzione programmi software. In caso contrario, il computer sarebbe meno protetto. La funzionalità Protezione esecuzione programmi hardware non può essere disattivata manualmente.
  
#### Requisiti per l'esecuzione di questa attività
  
-   Credenziali: è necessario accedere al computer utilizzando un account con diritti di amministratore locale.
  
##### Disattivazione di Protezione esecuzione programmi a livello di intero sistema utilizzando boot.ini  
  
**Per disattivare Protezione esecuzione programmi utilizzando boot.ini**
  
1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.
  
2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.
  
3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.
  
4.  Fare clic sulla scheda **Avanzate** e, nell'area **Avvio e ripristino**, selezionare **Impostazioni**.   
  
    ![](images/Cc700810.DEPcnf08(it-it,TechNet.10).gif)
  
    **Figura 8   Impostazioni di Avvio e ripristino**
  
5.  Nell'area **Avvio** **sistema**, fare clic su **Modifica**.
  
    ![](images/Cc700810.DEPcnf09(it-it,TechNet.10).gif)
  
    **Figura 9   File boot.ini visualizzato nel Blocco note**
  
6.  Nel **Blocco note**, fare clic su **Modifica**, quindi scegliere **Trova**.
  
7.  Nel **campo** **Trova**, digitare **/noexecute** e fare clic su **Trova** **successivo**.
  
8.  Nella finestra di dialogo **Trova**, fare clic su **Annulla**.
  
9.  Sostituire il Livello\_criterio specificato (ad esempio, "**OptOut**") con "**AlwaysOff**" (senza le virgolette).
  
    **AVVISO:** assicurarsi che il testo immesso sia specificato correttamente.
  
    **Nota:** a questo punto, l'opzione del file boot.ini dovrebbe essere la seguente:
  
    **/noexecute=AlwaysOff**
  
10. Nel **Blocco note**, fare clic su **File**, quindi scegliere **Salva**.
  
11. Fare clic su **OK** per chiudere **Avvio** **e** **ripristino**.
  
12. Fare clic su **OK** per chiudere **Proprietà del** **sistema**, quindi riavviare il computer.
  
#### Verifica della disattivazione di Protezione esecuzione programmi
  
**Per verificare che le impostazioni di protezione della memoria siano applicate**
  
1.  Fare clic su **Start**, quindi su **Pannello di**  **controllo**.
  
2.  Sotto **Scegliere** **una** **categoria**, fare clic su **Prestazioni** **e** **manutenzione**.
  
3.  Sotto **o un'icona del Pannello di controllo**, fare clic su **Sistema**.
  
4.  Fare clic sulla scheda **Avanzate**.
  
5.  Nell'area **Prestazioni**, fare clic su **Impostazioni**, quindi scegliere **Protezione** **esecuzione** **programmi**.
  
6.  Verificare che le impostazioni di Protezione esecuzione programmi non siano disponibili, quindi fare clic su **OK** per chiudere **Impostazioni** **prestazioni**.
  
7.  Fare clic su **OK** per chiudere **Proprietà del** **sistema**, quindi chiudere **Prestazioni** **e** **manutenzione**.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Informazioni correlate
  
Per ulteriori informazioni sulla protezione della memoria di Windows XP SP2, fare riferimento alle seguenti risorse:
  
-   "[Changes to Functionality in Microsoft Windows XP Service Pack 2 - Part 3: Memory Protection Technologies](http://technet.microsoft.com/en-us/library/bb457155.aspx)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35495
  
Per ulteriori informazioni sulla protezione di Windows XP SP2, fare riferimento alle seguenti risorse:
  
-   "[Windows XP Security Guide v2 updated for Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35309)" sul sito Web dell'area di download Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35309
  
-   "[Windows XP Security Guide Appendix A: Additional Guidance for Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?linkid=35465)" sul sito Web Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=35465
  
Per le definizioni dei termini relativi alla protezione, fare riferimento alle seguenti risorse:
  
-   "[Microsoft Security Glossary](http://go.microsoft.com/fwlink/?linkid=35468)" sul sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35468
  
[](#mainsection)[Inizio pagina](#mainsection)
