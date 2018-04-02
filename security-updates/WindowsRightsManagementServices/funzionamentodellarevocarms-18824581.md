---
TOCTitle: Funzionamento della revoca RMS
Title: Funzionamento della revoca RMS
ms:assetid: '469e3938-a59b-4c92-9779-ead64e724d00'
ms:contentKeyID: 18824581
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720263(v=WS.10)'
---

Funzionamento della revoca RMS
==============================

Quando in una richiesta di binding è coinvolta un'entità revocata, la revoca impedisce il binding, ovvero il processo che consente a un utente di utilizzare il contenuto. La revoca viene implementata tramite elenchi di revoche distribuiti ai computer client. Questi elenchi sono file XrML firmati che specificano il contenuto, le applicazioni, gli utenti o altre entità che sono state revocate dall'entità che rilascia l'elenco.

Ogni volta che un utente cerca di utilizzare un contenuto protetto, l'applicazione abilitata per RMS associata invia al client RMS una richiesta per il diritto appropriato, sotto forma di una richiesta di binding. Se ad esempio l'utente tenta di aprire un file, l'applicazione richiede un diritto di visualizzazione che consente l'apertura del file. Se l'utente tenta di modificare il file, l'applicazione richiede un diritto di modifica.

Durante l'elaborazione della richiesta di binding, il client RMS esegue le seguenti operazioni:

1.  Valuta la licenza d'uso per verificare eventuali requisiti di elenchi di revoche.
2.  Se la licenza d'uso richiede la revoca, il componente client verifica se l'elenco di revoche specificato è presente, registrato e aggiornato in base all'intervallo di aggiornamento indicato nella licenza d'uso.
3.  Verifica che l'entità che ha firmato l'elenco di revoche sia specificata nella licenza d'uso come entità autorizzata alla revoca della licenza.
4.  Se questi controlli hanno esito positivo, il componente client determina quindi se una qualsiasi delle entità coinvolte nella richiesta di binding originale è stata revocata. In tal caso, rifiuta la richiesta di binding.

Gli elenchi di revoche possono essere distribuiti dall'amministratore ai computer client, oppure possono essere scaricati sul computer mediante un'applicazione abilitata per RMS, se richiesto dalla licenza d'uso. Quando un elenco di revoche viene utilizzato per il binding di un contenuto, viene registrato e può essere utilizzato per richieste di binding con altre licenze d'uso fino a quando l'applicazione rimane aperta. Dopo che l'applicazione è stata chiusa, la registrazione dell'elenco di revoche viene annullata.

Nella figura riportata di seguito sono illustrati il processo di binding e il funzionamento della revoca durante tale processo.

![](images/Cc720263.81aa2d70-d261-49ad-b446-96a2eddba1a5(WS.10).gif "Processo di associazione")

La revoca è facoltativa. L'amministratore di RMS può richiedere la revoca specificandola in uno o più modelli di criteri per i diritti dell'organizzazione. Quando la revoca è attivata, una licenza può eseguire il binding solo se l'elenco di revoche necessario è presente, registrato nel computer dell'utente e aggiornato in base all'intervallo di aggiornamento indicato nella licenza d'uso.

Si noti, tuttavia, che la revoca può avere effetto per una data licenza d'uso anche quando la licenza d'uso non la richiede. La revoca ha effetto ogni volta che una qualsiasi autorità emittente di qualsiasi certificato incluso nella catena di trust coinvolta in una richiesta di binding ha rilasciato un elenco di revoche registrato in un computer client. In questo scenario l'elenco di revoche viene utilizzato per elaborare le richieste di binding anche se le licenze d'uso coinvolte non richiedono la revoca. Ciò è vero fino a quando viene chiusa l'applicazione abilitata per RMS; infatti, questa operazione annulla la registrazione dell'elenco di revoche.

Ad esempio, qualora un utente cerchi di utilizzare parte di un contenuto la cui licenza d'uso, emessa dall'entità A, richiede l'elenco di revoche emesso dall'entità A, l'applicazione abilitata per RMS può ottenere e registrare l'elenco di revoche dall'URL indicato nella licenza d'uso. Durante l'elaborazione della richiesta di binding, il client RMS controlla la presenza di eventuali revoche nell'elenco di revoche.

Lasciando aperta l'applicazione abilitata per RMS, l'utente può quindi cercare di utilizzare una seconda parte di contenuto la cui licenza d'uso è stata emessa dall'entità A. Nonostante la licenza d'uso non comprenda alcuna condizione di revoca, l'elenco di revoche dell'entità A risulta attualmente registrato sul computer dell'utente. In questa situazione il componente client esamina l'elenco di revoche prima dell'elaborazione della richiesta di binding.

L'utente tenta quindi di utilizzare un contenuto la cui licenza d'uso è stata rilasciata dall'entità C. La licenza d'uso non include una condizione di revoca. Poiché l'unico elenco di revoche registrato nel computer client è quello rilasciato dall'entità A che non è inclusa nella catena di trust della licenza d'uso, non esistono revoche applicabili al binding.

Infine, l'utente chiude l'applicazione abilitata per RMS e in seguito riapre la seconda parte di contenuto che non comprende la condizione di revoca. Poiché la registrazione dell'elenco di revoche emesso dall'entità A non è stata annullata alla chiusura dell'applicazione, il client RMS non lo esamina per elaborare la richiesta di binding.
