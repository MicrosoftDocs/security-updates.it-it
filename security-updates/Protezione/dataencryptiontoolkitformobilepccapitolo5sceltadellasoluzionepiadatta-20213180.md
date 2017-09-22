---
TOCTitle: 'Data Encryption Toolkit for Mobile PC: Capitolo 5: scelta della soluzione più adatta'
Title: 'Data Encryption Toolkit for Mobile PC: Capitolo 5: scelta della soluzione più adatta'
ms:assetid: 'b77d6369-10e9-4e66-8c67-c9f8cb073ced'
ms:contentKeyID: 20213180
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162816(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC - Analisi della protezione
================================================================

### Capitolo 5: scelta della soluzione più adatta

Pubblicato: 4 aprile 2007

Per scegliere la combinazione appropriata di tecnologie di crittografia, è necessario comprendere i rischi correlati ai dati che richiedono protezione. È quindi possibile assegnare un valore a tali dati (includendo sia i costi diretti che indiretti) e scegliere una soluzione che fornisca il migliore ritorno sugli investimenti e fornendo al contempo un livello di protezione appropriato.

La seguente tabella Riepilogo di attenuazione dei rischi contiene i rischi relativi ai dati e indica se esiste una tecnologia o una combinazione di tecnologie di crittografia in grado di attenuare ciascuno di tali rischi. I rischi che possono essere attenuati con opzioni specifiche sono indicati con la lettera **Y**. I trattini **-** indicano i rischi per cui l'opzione specifica fornisce un'attenuazione ridotta o inesistente.

**Tabella 5.1. Riepilogo di attenuazione dei rischi**

![](images/Cc162816.865b473f-87a8-459c-80f3-79361863d073(it-it,TechNet.10).gif)
##### In questa pagina

[](#ecaa)[Utilizzo della tabella di riepilogo di attenuazione dei rischi](#ecaa)
[](#ebaa)[Conclusioni](#ebaa)

### Utilizzo della tabella di riepilogo di attenuazione dei rischi

La tabella può essere usata per selezionare le configurazioni e le tecnologie appropriate da implementare per raggiungere il livello di protezione richiesto dalla propria organizzazione. Poiché le tecnologie di codifica sono anche determinate dalla configurazione e dai criteri del sistema operativo, la tabella e rischi in essa riportati possono essere usati anche per comprendere l'impatto di altri criteri di sicurezza sulla soluzione di crittografia.

Ad esempio, una osservazione dedotta dalla tabella consiste nel fatto che quasi tutte le organizzazioni opzionali devono configurare la funzionalità di "ripristino da standby" per raggiungere un livello di protezione adeguato con una delle tecnologie Microsoft descritte in questa guida. L'impostazione del sistema visualizzata nell'interfaccia utente come **Chiedi la password al termine della modalità standby** può essere configurata sia mediante i Criteri di gruppo sia eseguendo gli script di modifica delle impostazioni del Registro di sistema.

#### Aggiunta di protezione in ambienti a basso rischio

Alcune organizzazioni hanno requisiti di sicurezza relativamente modesti, ma desiderano comunque la garanzia aggiuntiva che i dati dei PC portatili siano crittografati. Per tali organizzazioni, BitLocker con un TPM e codice PIN offre una protezione avanzata con un minimo sovraccarico di operazioni (oltre al requisito di garantire che i dati protetti siano ripristinabili dagli utenti autorizzati). Se l'organizzazione non è in grado di implementare BitLocker, EFS previene il rischio di accesso ai dati da parte di utenti non autorizzati sia su Microsoft Windows® XP che su Windows Vista™. L'esecuzione di EFS su Windows Vista consente inoltre di attenuare il rischio di perdita di dati dal file di paging del sistema. Tuttavia, sono richieste altre attenuazioni di rischi per proteggere il sistema da altri attacchi, tra cui gli attacchi offline contro il sistema operativo e i tentativi di furto delle chiavi.

#### Protezione delle informazioni personali (PII)

Se l'organizzazione richiede la protezione dei dati personali (PII) sui laptop dei dipendenti da minacce esterne e la valutazione dei rischi indica che la protezione da attacchi di media difficoltà è adeguata, è possibile scegliere di implementare BitLocker con un TPM e un codice PIN. Con questa soluzione, il rischio principale da intrusi che richiede una prevenzione aggiuntiva si presenta quando il computer viene lasciato in modalità sospensione o standby non protetta, il che può essere risolto mediante i Criteri di gruppo o gli script di modifica delle impostazioni del Registro di sistema.

Per gli ambienti in cui è necessario proteggere i dati personali ma non si può usare BitLocker con un TPM, è opportuno prendere in considerazione l'uso di EFS in combinazione con lo strumento Microsoft Encrypting File System Assistant (EFS Assistant). Questa opzione garantisce la protezione da numerosi attacchi di bassa difficoltà; per una protezione supplementare, è possibile richiedere l'uso di EFS con smart card per aggiungere un fattore di autenticazione.

Tuttavia, quando si implementa EFS con l'archiviazione chiavi software, tenere presente che la sicurezza dei dati protetti tramite EFS dipende dalla capacità di accesso dell'utente. Password di accesso facili, account di computer condivisi o altre vulnerabilità riducono la sicurezza dell'implementazione EFS ed è necessario prevenirle durante la distribuzione di EFS.

#### Protezione dei dati estremamente sensibili

Per le organizzazioni che richiedono il massimo livello di protezione contro intrusioni interne ed esterne, la soluzione che combina BitLocker ed EFS offre una protezione contro attacchi di media e alta difficoltà come illustrato nella presente guida. Ad esempio, se l'organizzazione presenta particolari restrizioni o requisiti per le dimensioni dello spazio delle chiavi, è possibile combinare la lunghezza di chiavi regolabile di EFS alle funzionalità di crittografia completa dei volumi di BitLocker per prevenire effettivamente un'ampia gamma di minacce.

[](#mainsection)[Inizio pagina](#mainsection)

### Conclusioni

Le due tecnologie descritte nella presente guida, BitLocker ed EFS, costituiscono approcci diversi ma complementari alla crittografia dei dati. EFS protegge i dati in file e cartelle su una base per utente, mentre BitLocker offre una crittografia completa dei volumi per il volume di sistema sui computer con Windows Vista. BitLocker offre la crittografia e il controllo di integrità pre-avvio e protegge il volume del sistema da un'ampia gamma di attacchi offline, ma non fornisce autenticazione utente. EFS completa BitLocker limitando l'accesso ai file crittografati agli utenti adeguatamente autenticati su un computer in esecuzione.

La presente guida *Analisi della protezione* descrive in che modo BitLocker ed EFS possono essere usati per prevenire una vasta gamma di rischi di protezione. Valutando con attenzione i rischi effettivi correlati alla propria organizzazione e le attenuazioni descritte in questa guida, è possibile scegliere una combinazione di tecnologie ed opzioni in grado di fornire la protezione necessaria ai propri dati sensibili.

**Download**

[Get the Data Encryption Toolkit for Mobile PCs (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)

**Partecipa**

[Iscriviti per partecipare al programma Data Encryption Toolkit Beta](https://connect.microsoft.com/invitationuse.aspx?programid=790&invitationid=desa-r7gd-3f73&siteid=14)

**Notifiche di aggiornamento**

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti**

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet)

[](#mainsection)[Inizio pagina](#mainsection)
