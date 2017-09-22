---
TOCTitle: Modelli di criteri per i diritti
Title: Modelli di criteri per i diritti
ms:assetid: 'eee931c8-7c98-48e9-9e2c-d0b7bd4f2b96'
ms:contentKeyID: 18824829
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747732(v=WS.10)'
---

Modelli di criteri per i diritti
================================

I modelli di criteri per i diritti descrivono un insieme standard di utenti, diritti e condizioni applicabili al contenuto protetto con RMS. Quando un utente applica un modello di criteri per i diritti a un particolare contenuto, i diritti in esso descritti vengono inclusi nella licenza di pubblicazione. 

Dal sito Web Amministrazione, è possibile creare altri modelli di criteri per i diritti, oltre a eliminare o modificare quelli esistenti. I modelli di criteri per i diritti possono includere più condizioni, ad esempio destinatari o gruppi di Active Directory specifici, il periodo di validità di una licenza d'uso per il contenuto, il periodo di tempo per cui il contenuto può essere utilizzato dopo la pubblicazione o anche valori personalizzati necessari per particolari applicazioni abilitate per RMS. Un modello può richiedere un elenco di revoche. Il modello specifica l'URL del file di elenco e il numero di giorni per cui l'elenco è valido. Quando un destinatario richiede una licenza d'uso basata sul modello, il sistema verifica l'elenco di revoche prima di permettere all'utente di utilizzare il contenuto protetto con RMS. Per ulteriori informazioni, vedere "[Revoca RMS](https://technet.microsoft.com/72689f90-f3c5-4b61-94ea-d825f3199b3b)" più avanti in questo argomento.

Alcuni esempi di diritti stabiliti nei modelli di criteri sono:

-   Il contenuto può essere visualizzato da tutti gli utenti, ma modificato solo dall'autore.
-   Il contenuto può essere visualizzato da tutti gli utenti facenti parte dell'organizzazione, ma solo per un mese dopo la pubblicazione.
-   Il contenuto può essere visualizzato da tutti gli utenti facenti parte dell'organizzazione, ma non da partner o clienti esterni.
-   Il contenuto può essere visualizzato solo da destinatari specifici.
-   Il contenuto può essere visualizzato o modificato solo da un destinatario specifico.

I modelli possono includere varie condizioni, tra cui:

-   I destinatari o i gruppi di Active Directory specifici a cui sono stati assegnati diritti per il contenuto.
-   Il periodo di validità di una licenza d'uso per il contenuto.
-   Il periodo di tempo per cui il contenuto può essere utilizzato dopo la pubblicazione.
-   Se la licenza d'uso richiede un elenco di revoche e la frequenza con cui l'elenco deve essere aggiornato.
-   Valori personalizzati necessari per particolari applicazioni abilitate per RMS.

I modelli di criteri per i diritti sono memorizzati nel database di configurazione e in una cartella condivisa. L'amministratore RMS è responsabile della distribuzione dei modelli di criteri per i diritti dalla cartella condivisa ai computer client, al fine di renderli utilizzabili da parte degli autori. Per ulteriori informazioni, vedere"Distribuzione dei modelli di criteri per i diritti" in "Gestione di un server RMS" in questa documentazione.

Nelle applicazioni abilitate per RMS, gli autori possono selezionare il modello di criteri per i diritti da applicare, nel quale normalmente viene indicato un gruppo i cui membri possono utilizzare il contenuto. Quando un destinatario richiede una licenza d'uso, il server applica il modello di criteri per i diritti dal database. Questo serve a garantire che le condizioni di una licenza d'uso riflettano sempre la versione più aggiornata del modello.
